# TEKORA Technical Decision Register

**Status:** RECOMMENDATIONS FOR OWNER APPROVAL — not silently approved architecture.  
**Last reviewed:** 26 November 2026.  
**Rule:** A recommendation becomes binding only when its decision record is marked APPROVED with approver and date.

## 1. Why this register exists

The platform blueprint defines product intent and cross-category contracts. This register converts unresolved engineering choices into explicit decisions so OpenCode does not invent a stack, deployable topology, provider or operational commitment.

Do not treat a candidate technology as a dependency until its decision is approved. OpenCode may prepare comparison evidence, compatibility tests and a migration-safe plan before approval.

## 2. Recommended initial technical direction

| Area | Recommended baseline | Why | Approval / validation still required |
|---|---|---|---|
| Application topology | Modular monolith, one deployable backend initially | Keeps transactional boundaries and operations manageable while preserving bounded contexts | Module boundaries, scaling and team ownership |
| Web application | Next.js + React + TypeScript | Strong full-stack web ecosystem, SSR/CSR choices, routing and broad UI tooling | Current stable versions, deployment target, rendering needs, package manager |
| Backend | Java LTS + Spring Boot + Maven | Mature typed backend, security, transactions, integrations and testing; aligns with existing engineering familiarity | Exact supported Java/Spring versions, module strategy, build conventions |
| System of record | PostgreSQL | Relational integrity, transactions, indexing and mature migration tooling | Hosting, version, backup/restore, region and operational owner |
| Cache/coordination | Redis, only where justified | Cache, short-lived coordination and rate-limit primitives | Exact use cases, persistence expectations and provider |
| Async messaging | RabbitMQ when asynchronous workflows justify it | Durable work queues and decoupling for provider callbacks/provisioning | Queue topology, delivery guarantees, operational cost and recovery |
| API | REST/JSON with OpenAPI | Accessible integration surface and generated client potential | Versioning, auth profiles, error schemas and compatibility policy |
| Events | Versioned event envelope + transactional outbox/inbox | Avoids database/event dual-write inconsistency and duplicate side effects | Event broker, schema registry approach and retention |
| Object storage | S3-compatible abstraction | Portable object storage for exports, artifacts and media | Provider, region, lifecycle, encryption and egress economics |
| Identity | OIDC/OAuth2-compatible identity with MFA | Standards-based identity and delegated access | Build-vs-buy, local identity needs, session and recovery policy |
| Frontend styling | Design tokens + accessible component primitives | Shared system across 22 categories, consistent accessibility | Final component library, styling framework and typography |
| Browser E2E | Playwright | Cross-browser workflow verification | CI browser matrix and artifact retention |
| Backend tests | JUnit + Spring test support + Testcontainers | Domain, integration and real dependency behavior | Exact versions and CI resource budget |
| Frontend tests | Vitest + Testing Library; Playwright E2E | Component behavior and browser-level workflows | Tool compatibility with selected Next.js version |
| Local dependencies | Docker Compose for disposable local services | Reproducible onboarding and isolation | Container engine support and image pinning |
| CI | GitHub Actions | Native repository integration | Required checks, secrets and runner budget |
| Observability | OpenTelemetry-compatible traces/metrics/logs | Vendor-neutral instrumentation | Backend/exporter, retention, PII policy and cost |
| Infrastructure | Infrastructure-as-code only after provider/topology approval | Repeatable environments and auditable changes | Cloud/provider, IaC tool, accounts and cost controls |

This is a coherent recommended baseline, not a claim that the stack is installed, selected by the owner or validated against every provider.

## 3. Architecture constraints

1. Start as a modular monolith with explicit bounded contexts.
2. Keep domain logic independent from web controllers, persistence implementation and provider SDKs.
3. Use module-owned tables and migrations; cross-module writes must pass through an explicit contract/application service.
4. Avoid circular module dependencies. Define an allowed dependency direction and enforce it with tests/build rules.
5. Use PostgreSQL transactions for local consistency; use outbox/inbox patterns for cross-boundary asynchronous work.
6. Model external operations as stateful workflows. A timeout after a request may have succeeded is UNKNOWN until reconciled.
7. Make commands idempotent where retries are possible. Reject reuse of an idempotency key with a different request payload.
8. Separate order, provisioning, payment attempt, control number, invoice, settlement, subscription and entitlement states.
9. Enforce tenant, organization, project, resource ownership and permission checks server-side on every request.
10. Keep provider-specific logic behind adapters and capability contracts. Do not leak provider IDs/statuses as the platform's public domain model.
11. Do not introduce microservices, Kubernetes, service mesh, CQRS infrastructure or event sourcing by fashion. Require measurable need and a decision record.
12. Keep secrets outside source control and application logs.

## 4. Recommended bounded-context decomposition

| Context | Owns | Must not own |
|---|---|---|
| Identity & Access | Principals, sessions, MFA, roles, permissions, policy evaluation | Product billing or provider credentials |
| Customer & Organization | Organizations, memberships, invitations, verification | Platform-wide identity credentials |
| Projects & Environments | Project ownership, environment boundaries, project-level policies | Provider implementation |
| Catalog & Pricing | Products, offers, SKUs, price versions, eligibility | Payment settlement |
| Orders | Customer intent, quote snapshots, order lifecycle | Provider-specific provisioning internals |
| Provisioning | Desired/observed resource state, workflows, reconciliation | Payment ledger |
| Provider Integrations | Provider accounts/adapters/capabilities/webhook intake | Customer authorization policy |
| Resources & Assets | Platform resource identity and ownership | Provider secret material |
| Billing & Finance | Invoices, credits, receivables, accounting/reconciliation records | Raw payment credentials |
| Payments | Payment attempts, provider transactions, refunds | Entitlement policy |
| Control Numbers | Issuance, expiry, payer reference, reconciliation | Treating issued number as proof of payment |
| Subscriptions & Entitlements | Access rights, renewal, grace and revocation | Payment provider state |
| Metering & Usage | Raw usage facts, rating inputs, corrections | Silent changes to published prices |
| Notifications | Templates, channel delivery and preference enforcement | Business workflow authority |
| Support & Incidents | Cases, incidents, status communications and escalation | Secret or unrestricted tenant access |
| Workflow & Approvals | Approval policy, dual control and operator actions | Bypassing domain invariants |
| Developer Hub | API applications, keys, webhooks, docs and sandbox | Unscoped platform administration |
| Audit & Compliance | Immutable audit records, evidence, retention and legal holds | Business data mutation outside controlled workflows |
| Analytics | Derived read models and reporting | Source-of-truth mutation |

A context may initially be a package/module rather than a separately deployed service.

## 5. Mandatory cross-cutting engineering standards

### 5.1 API
- Prefix: `/api/v1` for the initial public version.
- JSON UTF-8; timestamps in UTC ISO-8601.
- Monetary values are decimal strings plus ISO currency code; never floating-point money.
- Cursor pagination for potentially large collections.
- RFC 9457 Problem Details-compatible errors.
- Validate input at trust boundaries and return stable machine-readable error codes.
- Server-side authorization; never rely on hidden UI controls.
- Idempotency keys for externally visible create/charge/provision commands.
- Explicit request IDs, correlation IDs and trace context.
- Document rate limits, retry guidance and deprecation windows.

### 5.2 Webhooks
- Verify signatures against the raw request body.
- Validate timestamp/replay window where supported.
- Persist delivery identity and deduplicate before side effects.
- Handle duplicate and out-of-order events.
- Return provider-appropriate acknowledgements quickly; process long-running work asynchronously.
- Keep an UNKNOWN/reconciliation path when provider outcome is ambiguous.
- Never log signing secrets or full sensitive payloads.

### 5.3 Database and migrations
- Version every schema change through a migration tool selected by the approved stack.
- Prefer expand → migrate → contract for changes that span deploys.
- Use foreign keys and uniqueness constraints for integrity where practical.
- Define tenant-scoped uniqueness explicitly.
- Add indexes based on query patterns and measured plans.
- Document rollback feasibility; do not claim a destructive migration is reversible if data loss cannot be undone.
- Test migration from an empty database and from the previous supported schema.

### 5.4 Security and privacy
- Threat-model authentication, authorization, tenant isolation, provider callbacks, uploads, SSRF, secrets, admin actions and public endpoints.
- Use least privilege, secure defaults, MFA for privileged roles and audited elevation.
- Prevent IDOR/BOLA and cross-tenant enumeration.
- Apply CSRF/CORS/CSP/secure cookie/session protections according to deployment model.
- Classify data, minimize collection, define purpose, retention, export/deletion, residency and subprocessors.
- Encrypt in transit and at rest using supported controls; manage key rotation.
- Security testing must remain inside an explicitly authorized scope.

### 5.5 Frontend
- Use shared design tokens and accessible primitives; do not create 22 inconsistent UI systems.
- Keep business rules on the server.
- Model loading, empty, success, partial, pending, unknown, error, offline and recovery states.
- Meet WCAG 2.2 AA as a target, with manual review for keyboard, screen reader, zoom/reflow and contrast.
- Support responsive mobile/tablet/desktop and reduced motion.
- Avoid fake testimonials, provider logos, uptime/SLA claims and fabricated analytics.

## 6. Decision records

Use the following template for every decision:

- ID:
- Title:
- Status: PROPOSED / APPROVED / REJECTED / SUPERSEDED
- Date and approver:
- Context/problem:
- Options considered:
- Evidence and links:
- Decision:
- Consequences/trade-offs:
- Security/privacy implications:
- Cost/operations implications:
- Revisit trigger:
- Related requirement IDs:
- Supersedes/superseded by:

## 7. Initial decision backlog

| ID | Decision | Recommended direction | State |
|---|---|---|---|
| DEC-TECH-001 | Application topology | Modular monolith | PROPOSED |
| DEC-TECH-002 | Frontend framework | Next.js + React + TypeScript | PROPOSED |
| DEC-TECH-003 | Backend framework | Java LTS + Spring Boot + Maven | PROPOSED |
| DEC-TECH-004 | Primary database | PostgreSQL | PROPOSED |
| DEC-TECH-005 | Cache/coordination | Redis only for proven use cases | PROPOSED |
| DEC-TECH-006 | Async messaging | RabbitMQ when needed | PROPOSED |
| DEC-TECH-007 | API style | REST + OpenAPI | PROPOSED |
| DEC-TECH-008 | Event consistency | Outbox/inbox + versioned events | PROPOSED |
| DEC-TECH-009 | Local environment | Docker Compose for disposable dependencies | PROPOSED |
| DEC-TECH-010 | CI | GitHub Actions | PROPOSED |
| DEC-TECH-011 | E2E browser tests | Playwright | PROPOSED |
| DEC-TECH-012 | Observability | OpenTelemetry-compatible instrumentation | PROPOSED |
| DEC-TECH-013 | Cloud/hosting provider | Compare based on region, legal terms, cost and exit | PENDING |
| DEC-TECH-014 | Identity provider/build-vs-buy | OIDC-compatible; complete threat and cost review | PENDING |
| DEC-TECH-015 | DNS/domain provider | Verified ownership, API, region and contractual route | BLOCKED |
| DEC-TECH-016 | Payment/control-number provider | Legal and technical due diligence before live | BLOCKED |
| DEC-TECH-017 | Final typography and design tokens | Complete font licensing/glyph/contrast tests | PENDING |
| DEC-TECH-018 | Production topology and DR | Cost/capacity/restore evidence before approval | PENDING |

## 8. OpenCode decision behavior

OpenCode may:
- Compare options and document evidence.
- Recommend exact versions after checking official release/support documentation.
- Build isolated proof-of-concept tests when explicitly within an approved preparation phase.
- Record assumptions and trade-offs.

OpenCode may not:
- Mark proposed decisions approved on behalf of the owner.
- Choose a paid provider or incur spend.
- create cloud resources, domains, production DNS or payment accounts.
- change the product scope or remove one of the 22 categories.
- split the modular monolith into microservices without an approved decision.
- silently substitute an unavailable provider or technology.

## 9. Approval record

No technical decision in this document is APPROVED merely by being written here. Before Phase 05 Platform Foundation, the owner must approve the minimum stack decisions and the deployment/security boundaries. The owner may approve the recommended baseline as a set or request evidence-backed alternatives.

 
## 10. Pricing strategy decision

The mandatory 22-category pricing and freemium strategy is defined in `docs/PRODUCT_CATALOGUE_SKU_PRICING_FRAMEWORK.md`. Its initial market-positioning hypothesis is a 3–8% undercut only for comparable standard offers where fully loaded cost, provider terms, taxes, support and minimum contribution margin permit it. This is not a global discount or approved price list.

**Required architecture:** versioned price books and immutable price snapshots; benchmark/provider cost evidence; FX snapshots; SKU-level margin policies; free-tier/trial/credit entitlements; usage budgets and spend caps; price approvals; price-change notices; promotions; and separate billing components for provider pass-through, TEKORA fees, taxes and payment/payout fees.

**Decision status:** pricing capability requirements are mandatory for design. All TEKORA retail prices, discounts, margins, free quotas and payment fees remain unapproved until market, supplier, finance and legal validation.
