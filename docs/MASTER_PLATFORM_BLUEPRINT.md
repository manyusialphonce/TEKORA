# TEKORA — Master Platform Blueprint

**Working brand:** TEKORA  
**Tagline:** Technology, Connected.  
**Document role:** Authoritative product-definition and engineering-intent baseline  
**Project stage:** Discovery and documentation; no implementation claimed  
**Status convention:** Proposed/working items remain distinguishable from confirmed decisions and verified facts.

---

## 1. Executive vision

TEKORA is a unified technology services platform intended to connect technology services, infrastructure, digital products, developer capabilities, customer operations and managed services through one coherent ecosystem.

The platform should allow individuals, businesses, institutions and developers to discover, evaluate, purchase, configure, integrate, operate, monitor, pay for and manage technology services. It should also give internal teams a secure operational environment to sell, deliver, provision, support, maintain and govern those services.

TEKORA is not simply:
- a company brochure;
- a hosting storefront;
- a directory that redirects customers to unrelated third-party systems;
- a single-provider control panel;
- a promise that every listed service is owned or directly operated by TEKORA.

It is a **unified customer experience and service control plane** across company-delivered, managed, integrated, resold and partner-delivered capabilities. The delivery model for each offer must be explicit and truthful.

## 2. Brand and project boundaries

### 2.1 Working identity
- Name: **TEKORA**.
- Tagline: **Technology, Connected.**
- The name was selected as the strongest working option for pronunciation in Swahili and English, memorability, distinctiveness, premium character and breadth across technology services.
- Other considered names included KIVORA, TAVORA, NUVORA and ZENVORA.
- NEXORA is a separate existing user project and must not be reused.
- Domain, trademark, BRELA/company-name, social-handle, linguistic and market-conflict validation is **PENDING**. Do not state the brand is registered, legally clear or available.

### 2.2 Discovery boundary
Current work is to define and design the platform. Company ownership, legal structure, equity, commercial ownership and related governance questions are deferred until after the platform definition. Do not force those discussions into this stage.

A separate Wi-Fi management system was discussed independently; it is not automatically part of TEKORA. Integration or inclusion requires explicit approval.

## 3. Product surfaces and actors

### 3.1 Public website and service marketplace
Public-facing service discovery and trust layer:
- company/platform overview and value proposition;
- searchable, filterable service catalog and categories;
- service detail pages with delivery model, regions, dependencies, plans, pricing, limits, SLA/availability disclosures and prerequisites;
- comparison and configuration journeys;
- documentation, developer resources, status information, support and contact;
- account creation and conversion paths;
- clear distinction between available, preview, waitlist, partner-delivered, sandbox-only and unavailable services.

### 3.2 Customer portal
Authenticated customer experience:
- personal and organization accounts, teams, roles and workspaces;
- projects and environments;
- service discovery, quote/order, checkout and payment;
- subscriptions, invoices, receipts, control numbers and transaction history;
- provisioning and service lifecycle;
- resources, infrastructure map, configuration and credentials;
- usage, quotas, limits, billing, cost and alerts;
- API keys, integrations, webhooks and developer workspace;
- support tickets, service health, notifications and audit activity;
- renew, scale, suspend, cancel, restore and transfer workflows where supported.

### 3.3 Unified Developer Hub
An integrated developer environment described in Section 10: API catalog, documentation, sandbox, request testing, SDKs, webhook tooling, credentials, usage and test-to-live progression.

### 3.4 Internal Operations Platform
Controlled staff-facing workspaces:
- identity, roles, staff access and audit;
- CRM, leads, sales, quotes, contracts and customer onboarding;
- catalog, product, plan and pricing governance;
- orders, fulfilment, provisioning and service lifecycle;
- provider/partner operations and integrations;
- finance, billing, payment reconciliation and refunds;
- support, incidents, SLAs and escalations;
- engineering, change, release, infrastructure and asset management;
- security, compliance evidence, risk and incident response;
- reporting, analytics, approvals and policy administration.

### 3.5 Actor groups
Customers/individuals; organizations and organization administrators; developers; resellers/partners; support agents; sales/customer-success staff; finance staff; service operators; engineers/SRE; security/compliance staff; catalog/pricing administrators; privileged platform administrators. Exact roles and permission matrices are **PENDING requirements engineering**.

## 4. Delivery and service ownership models

Every catalog item and order must identify its delivery model:
1. **Owned/operated:** TEKORA directly operates the relevant service capability.
2. **Managed:** TEKORA manages a customer's service or infrastructure, potentially on external infrastructure.
3. **Integrated:** TEKORA provides a unified interface/workflow while an external provider performs part of the service.
4. **Resold:** TEKORA sells an authorized third-party service under agreed commercial terms.
5. **Partner-delivered:** an approved partner performs the service or a material portion.

Do not infer direct ownership, accreditation, SLA, region, capability or support entitlement from a catalog listing. Provider agreements, credentials, approvals, geographic coverage, rate limits, outage behavior, support boundaries, data handling and commercial constraints must be explicit.

A hybrid model is a working direction, not a final commercial/legal decision.

## 5. Service catalog — 22 draft categories

The following catalog is a broad discovery baseline. It is not yet a verified final catalog, a promise of availability, or proof of operational capability. Requirements engineering must decompose each service into product, plan, workflows, acceptance criteria, dependencies, risks and delivery model.

### 01. Domains, DNS & Internet Services
- Domain search, registration, transfer, renewal, contact management, locks, privacy, forwarding, lifecycle, expiry, recovery and portfolio management.
- DNS zone and record management; CRUD; bulk operations; templates; history/versioning; rollback; BIND import/export; propagation checks.
- Advanced DNS: GeoDNS, weighted, latency-based, failover, health checks, multi-provider and private DNS where providers support them.
- DNSSEC and domain security; certificate/SSL/TLS inventory, provisioning integrations, renewal and expiry monitoring.
- Brand protection, typosquatting, phishing, abuse and domain reputation monitoring.
- DNS monitoring, drift detection, diagnostics, IP/ASN, reverse DNS, reputation, CIDR, BGP and network intelligence integrations.
- CDN/edge integration; APIs, webhooks, SDKs, CLI and Terraform workflows.
- Domain lifecycle/recovery center; migration assistant with preflight and rollback; DNS templates and one-click integrations; approval workflows; multi-provider DNS management; portfolio risk dashboard.
- Email DNS security assistant for SPF, DKIM, DMARC, MTA-STS and TLS-RPT.
- RDAP-first domain lookup with fallback where appropriate.
- Tanzania `.tz` registration pathway only through authorized registrar/registry relationships and verified current TCRA/registry rules.
- Constraints: do not claim registrar or certificate authority status without accreditation/authorization. DNS failover is not necessarily instant; TTL, resolver caching and provider behavior matter. TLD lifecycle and recovery policies vary.

### 02. Web Hosting, Application Hosting & Compute
Shared/reseller hosting; VPS; dedicated servers; application hosting for WordPress/CMS, PHP, Java, Node.js, Python, .NET and static applications; resource allocation; staging/cloning; backups; SSH/SFTP; cron; logs; scaling; migration; recovery; deployment and runtime configuration.

### 03. Cloud Infrastructure & Virtualization
Virtual machines, bare metal, virtual networks, storage, snapshots, load balancers, high availability, autoscaling, multi-cloud resource views, provisioning, topology, configuration drift, cost and capacity management. Provider-specific limits and regions must be visible.

### 04. Containers, Kubernetes & Runtime
Docker workloads; image registries; managed/self-managed Kubernetes; clusters and node pools; Helm; ingress; secrets integration; autoscaling; container security scanning; GitOps; workload observability; backup and recovery. Kubernetes is not mandatory where simpler runtime is sufficient.

### 05. Networking & Connectivity
Virtual networks, VLANs, subnets, IPAM, public/private IPs, VPN, SD-WAN, routing, load balancing, bandwidth and QoS, Wi-Fi, private connectivity, BGP, network topology, diagnostics and monitoring. Do not merge an independent Wi-Fi management project without approval.

### 06. Database Services
Managed SQL/NoSQL; PostgreSQL, MySQL, MariaDB, SQL Server and other justified engines; Redis as cache/data service where appropriate; provisioning; backup; replication; failover; migration; query/performance monitoring; access/security; point-in-time recovery. Engine availability depends on providers and operational support.

### 07. Storage, Backup & Disaster Recovery
Object, block and file storage; S3-compatible APIs; snapshots; backup policies; retention; replication; restore; RTO/RPO objectives; immutable backups; ransomware-resilient design; restore testing and disaster-recovery planning. A backup is not verified until restore tests succeed.

### 08. Email Infrastructure
Business mailboxes, domains, aliases, groups, SMTP/IMAP/POP, transactional and bulk email APIs, delivery analytics, SPF/DKIM/DMARC/MTA-STS/TLS-RPT, spam/malware protection, migration, archive, sender reputation, bounce and suppression management, consent and deliverability diagnostics.

### 09. SMS, Voice & Omnichannel Communication
SMS/OTP, voice, virtual numbers, IVR, WhatsApp Business integrations, push notifications, unified APIs, templates, analytics, sender identity, consent, delivery receipts and provider fallback where contractually and technically supported.

### 10. Payment Infrastructure, Billing & Fintech Integrations
Payment gateway integrations; mobile money, bank and card channels; invoices, receipts, subscriptions and recurring billing where supported; metering; refunds/reversals; reconciliation; webhooks; audit and provider integrations.
**Control Number Management is a distinct first-class capability**, not just a payment field:
- create/assign and uniquely map a control number to customer, organization, invoice, order or subscription;
- lifecycle statuses, validity/expiry, renewal, cancellation and replacement;
- duplicate prevention and idempotent processing;
- paid, unpaid, pending, expired, cancelled, partially paid, overpaid, underpaid and unmatched states where provider/business rules permit;
- reconciliation of control-number records against provider/bank statements and received transactions;
- audit trail for generation, assignment, status changes, callbacks, manual review and reconciliation;
- provider-side verification, authenticated callbacks and signed webhooks; screenshots are never proof of payment;
- handle delayed callbacks, duplicate notifications, reversals, refunds, timeouts and provider outages.
Do not assume TEKORA is a licensed payment processor, bank, custodian or financial institution. Verify provider contracts, regulatory permissions, geography and Tanzania requirements before live money movement.

### 11. Developer Tools & API Infrastructure
API gateway/management; searchable API catalog and portal; authentication; scopes; rate limits; quotas; webhooks; API monetization; SDKs and documentation; event brokers; isolated sandbox; version lifecycle; schema registry; contract tests; API analytics and developer onboarding.

### 12. Software Development, DevOps & Deployment
GitHub/GitLab integrations; CI/CD; build/deploy pipelines; runners; environments; infrastructure as code; QA automation; artifact management; releases; rollback; preview deployments; SBOM and supply-chain security. Integrations require scoped access and explicit consent.

### 13. Cybersecurity & Information Security
Website, API, network, server, cloud and container security; IAM; WAF/DDoS integrations; vulnerability management; authorized penetration testing; malware/threat detection; SIEM integrations; incident response; forensics; privacy and governance. Security testing requires written authorization and scope. Tooling does not imply certification.

### 14. Monitoring, Observability & SRE
Infrastructure/APM; logs, metrics and traces; uptime and synthetic monitoring; database/network/container observability; alerts and incidents; status pages; SLI/SLO/SLA tracking; cost and capacity; AI-assisted diagnostics; dependency maps; error budgets and on-call workflows.

### 15. AI, ML & Automation Infrastructure
Model gateway; LLM and multimodal provider integrations; model/provider comparison; GPU/CPU compute; training/fine-tuning; model registry/evaluation/inference; embeddings/vector databases/RAG; agents; workflow/no-code automation; guardrails/security; monitoring/cost; human approval; prompt/version management. AI must respect permissions, data boundaries and evidence.

### 16. Media, Video & Realtime Infrastructure
Image/audio/video storage and transformation; transcoding; VOD/live streaming; HLS/DASH; WebRTC; conferencing and virtual classrooms; WebSockets; presence; private media; CDN; analytics; recording policies; subtitles and transcription. Respect consent, privacy, retention and regional restrictions.

### 17. Data Engineering & Analytics
Ingestion; ETL/ELT/CDC; pipelines; warehouse/lake; orchestration; BI/reporting; data quality; lineage/governance; streaming/batch; data science; data contracts; schema evolution and pipeline observability.

### 18. Business Applications & Digital Productivity
ERP, CRM, HRM, project management, collaboration, documents, workflow, engagement, e-commerce, application marketplace, managed updates, cross-application identity/synchronization/reporting. Avoid implying every application is internally built.

### 19. IT Consulting, Managed IT & Professional Services
Technology strategy; software engineering; managed IT/helpdesk; cloud/network/database/DevOps services; training; audits; SLA/contracts; quotations; schedules; work logs; delivery evidence and customer acceptance.

### 20. IoT, Smart Systems & Connected Infrastructure
Device provisioning/identity; MQTT/connectivity; telemetry; smart building/industrial/fleet solutions; automation; firmware/OTA; digital twins; simulators; device certificates; fleet monitoring and cost. Security lifecycle and device ownership must be explicit.

### 21. Digital Trust, Compliance & Identity
IAM, SSO, MFA, OAuth/OIDC/SAML; identity verification integrations; PKI; digital signatures; consent/privacy; compliance evidence; vendor risk; identity lifecycle; access certification and data-subject requests. Do not claim formal certification or regulated identity authority without evidence.

### 22. Licensing, Software Distribution & Digital Products
License creation/activation/validation; downloads/private repositories; Docker/Maven/npm/Python/NuGet registries; software marketplace; publisher management; updates; SBOM/signing; offline activation policies; license seats; vendor onboarding and entitlement management.

## 6. Shared platform engines

Define bounded contexts, ownership, APIs/events and data responsibility for:
1. Customer & Organization.
2. Product & Service Catalog.
3. Pricing & Offers.
4. Order Management.
5. Provisioning & Automation.
6. Provider Integration.
7. Billing & Financial.
8. Usage & Metering.
9. Subscription & Entitlement.
10. Support & Service Desk.
11. Monitoring & Observability.
12. Security & Compliance.
13. Notification.
14. Workflow & Approval.
15. Partner & Reseller.
16. Analytics & Intelligence.
17. Resource & Asset Registry.
18. Policy & Governance.

Shared engines must avoid duplicated domain logic across 22 categories. Define ownership and data boundaries before implementation.

## 7. Platform differentiators and cross-service capabilities

- **Unified Control Plane:** one coherent place to see and manage services, resources, subscriptions, orders, usage, health and lifecycle.
- **Infrastructure Visual Map:** resource topology, dependencies, regions/providers, status and relationships, based on verified inventory.
- **AI Infrastructure Assistant:** explain and recommend from authorized logs, metrics, traces and configuration; show evidence and respect access controls; never invent telemetry.
- **Intelligent Cost Optimization:** usage/cost visibility, forecasts and recommendations; disclose estimate assumptions and provider billing differences.
- **Multi-cloud and multi-provider operations:** normalized experience with explicit provider-specific capabilities and limitations.
- **Visual Automation Studio:** governed workflows, triggers, approvals, retries, audit and human-in-the-loop.
- **White-label/reseller ecosystem:** partner workspaces, delegated scopes, pricing and customer boundaries.
- **Third-party marketplace:** vetted providers, service descriptions, delivery responsibility, contracts and support boundaries.
- **Intelligent provisioning:** orchestration with idempotency, rollback/compensation and visible progress.
- **Unified billing and usage:** consistent customer experience while retaining provider-specific source evidence.

These are intended differentiators, not claims of existing implementation.

## 8. Customer journeys and lifecycle

### 8.1 Core service journey
Account → organization/workspace/project → discover service → compare plan/configuration → quote/order → payment or approved credit/billing → invoice/receipt → provisioning/provider integration → configuration/credentials → dashboard/monitoring → usage/cost → scale/renew/suspend/cancel/restore → support and audit.

### 8.2 Failure-aware lifecycle
Represent draft, awaiting approval, awaiting payment, payment pending, provisioning, active, degraded, suspended, failed, expired, cancellation pending, cancelled, recovery and archived states as appropriate. Do not use one generic status for all categories. Make responsible provider, next action, expected waiting and support path clear.

### 8.3 Organization and project model
Support personal and organization accounts, multiple memberships, role scopes, workspaces, projects and environments. Enforce tenant/org/project/resource ownership at every API and data access boundary. Detailed role matrix and hierarchy remain for requirements engineering.

## 9. Developer Hub specification

### 9.1 API catalog
Search/filter APIs by product, provider, category, version, authentication, region, sandbox/live support and lifecycle status. Include verified capability and prerequisite metadata.

### 9.2 Isolated sandbox
Separate sandbox credentials, data, endpoints and quotas from live environments. Clearly label simulated provider behavior. Never allow sandbox artifacts to cause real financial or production side effects.

### 9.3 API request workspace
Methods, URLs, headers, query/path parameters, body, auth, response, latency, history, collections, environment variables, scripts/assertions, schema validation and import/export. Protect secrets in saved collections and logs.

### 9.4 Documentation and SDKs
Interactive, versioned API docs; quickstarts; guides; code samples; changelogs; error references; webhook examples; SDKs for Java, PHP, Node.js, Python, .NET, Kotlin, Swift and other justified languages. Generate from verified schemas where possible.

### 9.5 Integrations and operations
Project integrations, sandbox/live separation, scoped credentials, rotation/revocation, webhooks, delivery attempts, signature verification, inspection and replay, provider health, usage, errors, quotas and billing. Fallback routing only where provider contracts and technical capabilities permit.

### 9.6 Mock/simulation engine
Clearly label simulated flows for payment initiated/success/failure/pending/reversed/timeout, duplicate events, invalid/expired control number, webhook delivery and provider errors. Simulations must be deterministic, isolated and auditable.

### 9.7 AI developer assistant
Ground responses in approved documentation, schemas, examples and verified provider capability. Cite source/version, say when information is missing, avoid leaking secrets or other tenants' data, and require confirmation for consequential actions.

### 9.8 Test-to-live journey
Create project → choose stack and integrations → issue sandbox credentials → test APIs and mocks → inspect webhooks → use docs/SDKs → validate security and usage → configure provider credentials/approvals → request live access → explicit review/approval → live enablement. Do not imply a sandbox automatically guarantees live access.

## 10. Internal operations requirements

- **Identity and staff access:** role separation, least privilege, MFA for privileged users, scoped access, joiner/mover/leaver, audit.
- **CRM and sales:** lead/customer records, opportunities, quotations, follow-ups, contracts and onboarding.
- **Catalog and pricing:** approvals, versioning, eligibility, regions, terms, taxes/fees and effective dates.
- **Orders and provisioning:** queues, dependencies, retries, idempotency, compensation, manual intervention and customer status.
- **Provider operations:** credentials in secrets manager, provider contracts/capabilities, health, quotas, costs and incidents.
- **Finance:** invoices, receipts, collections, refunds/reversals, reconciliation, ledger/audit and approvals.
- **Support:** tickets, priority, SLA, escalation, knowledge base, customer communication and resolution evidence.
- **Engineering/infra:** resource registry, topology, changes, deployments, incidents, capacity, backup and recovery.
- **Security/governance:** vulnerabilities, access review, audit, risk, policy, retention, incident response and compliance evidence.
- **Partners:** onboarding, due diligence, delegated access, resale agreements, revenue/pricing rules and customer ownership boundaries.
- **Analytics:** service adoption, reliability, costs, margins where authorized, support performance and operational trends.

## 11. UI/UX and visual design system

Premium UX is a foundational product requirement, not a final polish exercise. It must be professional, polished, modern, welcoming, intuitive, consistent and efficient, reducing friction and helping users enjoy using the platform.

### 11.1 Research and benchmarking
Research actual relevant patterns from:
- Stripe — payments, billing, subscriptions, developer workflows.
- Vercel — developer, project, environment and deployment workflows.
- Cloudflare — DNS, network, security and infrastructure control.
- DigitalOcean — cloud infrastructure and resource management.
- Supabase — developer onboarding and integrated DX.
- Twilio — communication APIs, logs and usage.
- Linear — information hierarchy, navigation and focused UX.

For each feature, inspect real pages/workflows and evaluate information architecture, navigation, visual hierarchy, typography, content density, interaction, form/table behavior, loading/empty/error/success states, responsiveness, accessibility, performance and recovery. Document source, date, observed pattern, suitability, adopted/adapted/rejected choice and rationale. Reference sites are inspiration, not requirements authority. Do not copy proprietary source, artwork or identity.

### 11.2 Global design system
One coherent platform design system across all 22 categories; category accents may distinguish services but must not create disconnected applications. Define:
- brand identity, palette, semantic colors and service accents;
- design tokens for spacing, sizing, radius, elevation, borders, typography and motion;
- global shell, navigation, breadcrumbs, search, notifications, account/workspace switcher;
- responsive layouts and reusable components;
- forms, validation, tables, filters, charts, cards, status indicators, dialogs, command/search patterns;
- onboarding, help, empty/loading/error/success states and recovery;
- light, dark and system themes; optional accent/density/dashboard customization where appropriate.

### 11.3 Provisional visual direction
Starting palette only; contrast and visual tests are required before final approval:
- Primary blue: `#315EFB`
- Teal: `#14B8A6`
- Deep navy: `#101828`
- Background: `#F7F8FC`
- Surface: `#FFFFFF`
- Border: `#E6EAF0`

Provisional service accents:
- payments `#0F9F83`;
- cloud `#3478F6`;
- developer/API `#7158E8`;
- AI `#8957D5`;
- cybersecurity `#D97706`;
- communications `#0EA5E9`;
- data `#0D9488`;
- media `#D9468F`;
- IoT `#CA8A04`;
- business apps `#3B69C9`;
- licensing `#64748B`.

Do not use color alone to convey status or chart meaning. Validate contrast in both themes.

### 11.4 Typography — mandatory research
Do not default to generic/common fonts merely because they are popular. Research and deliberately select a distinctive, premium, highly legible typography system. Evaluate separate roles for:
- display/headings;
- body/long-form content;
- UI labels and controls;
- numbers, metrics and tabular data;
- code and technical content.

Assess readability, visual character, Swahili and special-character coverage, responsive rendering, accessibility, weight availability, performance, licensing, fallback behavior and consistency. Test actual screens, forms, dense tables, charts, mobile layouts and long content. Document exact families, weights, roles and rationale. Typography selection remains a research/approval deliverable, not a guessed fixed choice.

### 11.5 Accessibility and responsive behavior
Target WCAG-aligned accessible patterns: semantic structure, keyboard operation, visible focus, contrast, labels/errors, screen-reader support, adequate touch targets, reduced motion, zoom/reflow, chart alternatives and non-color status cues. Test mobile, tablet and desktop. UX review is required per major workflow and module.

## 12. Architecture and engineering direction

These are selected working defaults for planning, not verified installed dependencies or final architecture. Validate supported releases, compatibility, cost, skills, deployment constraints and operational burden in Phase 04.

| Concern | Working direction |
|---|---|
| Web | Next.js, React, TypeScript |
| Styling | Tailwind CSS + custom design system |
| Component foundation | Evaluate and customize shadcn/ui |
| Backend | Java 21+ + Spring Boot |
| Security | Spring Security; OAuth 2.0/OIDC as appropriate |
| Persistence | Spring Data JPA/Hibernate |
| Primary database | PostgreSQL |
| Cache | Redis |
| Messaging | RabbitMQ |
| Migrations | Flyway |
| API | REST + OpenAPI; WebSockets where justified |
| Gateway | Evaluate Spring Cloud Gateway |
| Object storage | S3-compatible abstraction |
| Infrastructure | Docker, Terraform, Ansible; Kubernetes only when justified |
| Observability | OpenTelemetry, Prometheus, Grafana, centralized structured logs/alerts |
| Testing | JUnit 5, Testcontainers, Vitest, Playwright, API/integration/E2E/security/performance |
| CI/CD | GitHub Actions |

### 12.1 Architecture principles
- Start with a modular monolith and explicit bounded contexts.
- Define module ownership, domain models, contracts, events, dependencies and data boundaries.
- Extract services only with evidence from scale, isolation, reliability, team ownership or operational need.
- Avoid distributed complexity, duplicate sources of truth and premature infrastructure.
- PostgreSQL is the primary system of record; Redis is cache; RabbitMQ is asynchronous messaging.
- Use idempotency, retries with bounded policies, timeouts, circuit breakers where justified, compensation and observable workflows.
- Provider adapters must expose normalized common behavior while preserving provider-specific capabilities and errors.

### 12.2 Initial domain/module candidates
Customer/Organization/Identity; Catalog/Pricing; Orders; Billing/Payments/Control Numbers; Provisioning; Provider Integrations; Resources/Assets; Usage/Entitlements; Support; Notifications; Workflow/Approvals; Observability; Security/Policy; Developer Hub; Partner/Reseller; Internal Operations; Analytics. Final module boundaries are **PENDING Phase 04**.

## 13. Security, privacy, trust and compliance

Threat-model public website, portal, tenant isolation, APIs, credentials, provisioning, internal admin, payments, webhooks, AI, partner access, infrastructure and supply chain.

Required design concerns:
- least privilege, deny-by-default and separation of duties;
- RBAC and contextual/attribute/resource authorization where needed;
- tenant, organization, project and resource ownership checks at every service/data boundary;
- MFA and stronger controls for privileged operations;
- secure session/token lifecycle, rotation, revocation and secret storage;
- encryption in transit and at rest where applicable;
- audit trails for privileged, financial, provisioning and configuration actions;
- input validation, output encoding, CSRF/CORS controls, rate limits and abuse protection;
- dependency scanning, SBOM, signed artifacts and supply-chain integrity;
- secure webhook signatures, replay protection and idempotency;
- privacy by design, data minimization, retention and deletion workflows;
- backup isolation, restore drills, incident response and disaster recovery;
- AI guardrails, prompt/data isolation, evidence grounding and human approval for consequential actions.

Security testing requires written authorization and scope. Do not run brute force, DoS or unauthorized tests. Compliance tooling and evidence collection do not equal formal certification. Do not claim regulatory approval, registrar/CA accreditation or payment licensing without proof.

## 14. Integration and provider strategy

Provider integration must be adapter-based, capability-aware and observable. Maintain provider registry metadata: supported products, regions, features, API versions, auth method, rate limits, quotas, pricing model, contract status, SLA, support path, data residency, webhook behavior, sandbox/live availability and limitations.

Requirements:
- provider-specific credential vault and least-privilege scopes;
- connection test and health status;
- normalized API with transparent capability differences;
- retries, timeouts, idempotency, backoff and circuit breaking where appropriate;
- webhook validation, deduplication, replay controls and event history;
- provider outage and degraded-mode handling;
- cost/usage reconciliation and provider billing evidence;
- customer disclosure of third-party responsibility and support boundary;
- no fake fallback when provider does not support it.

Potential provider integrations are research candidates, not confirmed partnerships or guaranteed availability. Each requires evaluation, contract, credentials, approval and regional/legal validation.

## 15. Reliability, operations and service quality

Design for:
- health and dependency checks;
- logs, metrics, traces and audit;
- SLO/SLI and SLA definitions only when measurable and contractually supported;
- incident, maintenance and status communication;
- capacity, quota, cost and rate-limit visibility;
- backup/restore and tested RTO/RPO;
- deployment safety, rollback and change approvals;
- provider outage handling and customer communication;
- data export, account closure and service cancellation;
- operational runbooks and escalation paths.

Never claim uptime, performance, availability or recovery capability without measurement and evidence.

## 16. Pricing, billing and commercial workflows

Support catalog pricing and plans with currency, billing interval, usage units, quotas, included resources, overage, taxes/fees, discounts, eligibility, region, renewal and cancellation terms. Tanzania is an initial market context, so TZS and local payment methods are important candidates, but exact providers, fees, legal treatment and availability must be verified. Support multi-currency only where justified and compliant.

Pricing engine must be versioned and auditable; quotes and orders must preserve the price/terms agreed at purchase. Billing, payment status, control-number state, subscription entitlement and provisioning state are related but separate domains.

## 17. Requirements engineering and traceability

Create stable requirement IDs in Phase 02 and preserve them across:
discovery → catalog → user/business requirements → functional/non-functional requirements → architecture/design → implementation tasks → tests → evidence → release.

Each requirement needs source, rationale, actor, priority, dependencies, acceptance criteria, risks, status, verification method and evidence. Avoid treating broad feature names as testable requirements. Maintain decision, assumption, dependency, risk and open-question registers.

## 18. Roadmap and phase governance

Only one phase is active at a time. Controlled parallel execution is allowed only within the active phase after dependencies, contracts, ownership and integration plan are clear. A new phase requires explicit user approval.

| Phase | Name | Primary outcome |
|---|---|---|
| 00 | Discovery & Project Definition | Verified context, vision, stakeholders, boundaries, assumptions, decisions and discovery plan |
| 01 | Master Service Catalog & Gap Analysis | Validated service taxonomy, subservices, delivery models, provider/market gaps |
| 02 | Requirements Engineering | Traceable business, functional, non-functional and acceptance requirements |
| 03 | UI/UX Research & Design | Benchmarks, user journeys, information architecture, design system, prototypes and usability evidence |
| 04 | Technical Architecture & Engineering Design | Validated architecture, modules, data, APIs, integrations, security and deployment design |
| 05 | Platform Foundation | Approved repository/application foundations, CI, identity, observability and environments |
| 06 | Core Service Development | Dependency-aware implementation of shared engines and prioritized service domains |
| 07 | Unified Developer Hub | API catalog, sandbox, test workspace, docs, SDKs, webhooks and developer workflow |
| 08 | Internal Operations Platform | Staff workflows, CRM, finance, provisioning, support and governance |
| 09 | Integration & End-to-End Validation | Verified customer and operator journeys across integrations |
| 10 | Security, Performance & Reliability Hardening | Independent security, load, resilience, accessibility and recovery evidence |
| 11 | Production Readiness & Controlled Launch | Operational readiness, approvals, runbooks, support, monitoring and limited launch |
| 12 | Continuous Improvement & Expansion | Feedback-driven roadmap and governed service expansion |

Phase 06 must be split into sub-phases according to dependency order, not treated as one parallel mega-task. Define interfaces and contracts first.

## 19. Documentation and evidence governance

Four core repository documents:
1. `docs/MASTER_PLATFORM_BLUEPRINT.md` — this authoritative product and engineering-intent source.
2. `AGENTS.md` — concise mandatory execution policy.
3. `README.md` — verified repository status, setup and operating instructions.
4. `MASTER_IMPLEMENTATION_PROMPT.md` — complete reusable OpenCode kickoff prompt.

Operational documentation:
- `docs/reports/` — report for every completed phase/sub-phase.
- Module README files when module-specific behavior/setup/API/configuration changes.
- Additional architecture/decision records may be created only when needed within approved scope; do not proliferate competing master documents.

Every phase report includes scope, requirement IDs, acceptance criteria, audit findings, plan, changed files, DB/API/config/integration effects, exact commands/results, evidence/gaps, security/performance/accessibility/reliability, docs updates, statuses, blockers/risks, commits and exit-gate recommendation.

No feature is complete without accurate documentation. A report does not prove functionality; source code does not prove functionality; tests alone do not prove production readiness.

Definitions:
- README = actual verified current state.
- Blueprint = intended/approved product scope and progress.
- Phase report = work performed and evidence.
- AGENTS = rules for how work is performed.

## 20. Status model

Use: **DONE, PARTIAL, BLOCKED, MISSING, BROKEN, NEEDS VERIFICATION, PROPOSED, PENDING**.

The current 22-category catalog is **PROPOSED / working discovery baseline**. Brand legal availability is **PENDING**. Stack and architecture are **PROPOSED working defaults pending Phase 04 validation**. No implementation or integrations are claimed.

## 21. Open decisions and validation register

At minimum, Phase 00–04 must resolve or explicitly defer:
- target customer segments, priority personas and initial use cases;
- service prioritization and launch catalog vs long-term catalog;
- service delivery/ownership model per product;
- geography, regions, data residency and local legal obligations;
- provider candidates, contracts, credentials, pricing and capabilities;
- exact domain registrar and .tz authorization pathway;
- payment provider and control-number API contracts, reconciliation and regulatory treatment;
- pricing, taxation, invoicing, currencies and commercial terms;
- organization/tenant hierarchy and detailed permission model;
- product boundaries and module ownership;
- architecture, hosting, deployment, environments, disaster recovery and cost;
- typography selection and approved design tokens;
- accessibility target and testing method;
- support model, SLAs, incident process and operational capacity;
- security/privacy policies, retention and compliance scope;
- domain/trademark/BRELA/brand checks;
- launch scope, acceptance gates and success measures.

Do not silently resolve legal, financial, commercial or provider questions by assumption. Where the user delegates technical choice, select the best evidence-based default and document the rationale and reversibility.

## 22. Current project baseline

- Project name: TEKORA (working).
- Tagline: Technology, Connected. (working).
- Stage: discovery and documentation.
- Repository: `manyusialphonce/TEKORA`, initially empty before docs preparation.
- No application code, schema, deployment, production integration, tests or live service is asserted.
- No service in the draft catalog is automatically considered available.
- No external benchmark research, legal clearance, provider agreement or regulatory approval is claimed merely by inclusion in this Blueprint.

## 23. Immediate next step

Perform Phase 00 discovery and project-definition reconciliation. Inventory the original discussions and decisions, verify current repository/tool context, identify missing requirements and ambiguities, create a traceable decision/assumption/risk/open-question register, and propose Phase 00 acceptance criteria. Do not start Phase 01 or implementation until the user explicitly approves.


## 24. Original-idea reconciliation and completeness requirements

This section preserves the originating product intent and the constraints raised during the planning discussions. It supplements—not replaces—the detailed catalog and requirements above. If a later phase discovers a conflict, record it in the decision register and obtain approval; do not silently discard an earlier user requirement.

### 24.1 Originating service proposition

The initial proposition was a company-operated platform through which the company can provide, sell, provision, configure, operate and support technology services. The first explicit examples were:
- web and application hosting;
- web/software development services;
- server and website essentials;
- payment gateway integration/provisioning;
- business and transactional email;
- SMS services;
- other useful web, infrastructure and digital technology services discovered during analysis.

These examples are foundational, not the limit of the platform. They must remain discoverable in the 22-category catalog and be mapped to actual products, plans, delivery methods and operational requirements during later phases. The platform must be more than a brochure, a list of links, a conventional hosting storefront or a thin redirect to unrelated provider dashboards.

### 24.2 Company-operated platform versus service delivery model

The company is the operator of the TEKORA platform and the customer-facing service experience. This does not mean every underlying network, data centre, registrar, payment rail, email/SMS route, cloud, AI model or other infrastructure must be owned by the company. For each catalogue item, explicitly classify the delivery model:
- company-built/company-operated;
- company-owned infrastructure or software;
- company-managed third-party infrastructure/service;
- integrated external provider;
- authorized reseller/white-label;
- partner-delivered professional service;
- hybrid or customer-provided infrastructure.

For each offer, disclose who actually operates the underlying service, the provider dependency, support boundary, data location where known, service limitations, contract/SLA responsibility, billing responsibility, and what happens when the provider is unavailable. Do not present an integration as an owned service or a planned capability as currently available.

### 24.3 Breadth, completeness and launch prioritization

The user explicitly requested exhaustive analysis across all 22 service categories and asked that advanced services remain in the overall catalog rather than being omitted simply because they may not launch in the first release. Therefore:
- preserve all 22 categories and their subfeatures in the long-term product discovery scope;
- assess every category, not only hosting, domains, email, SMS and payments;
- distinguish the full platform vision from the initial launch/MVP;
- prioritize launch items using customer value, demand, feasibility, delivery readiness, provider access, legal/regulatory exposure, operating cost, support burden, security risk and differentiation;
- defer a service only through an explicit status and rationale; do not silently delete it;
- a category may contain multiple independently launchable products, plans and delivery modes.

The goal is a professional, differentiated, broadly useful technology-services platform with real operational value. Breadth must not become an unsupported promise: service availability is enabled only after delivery capability, provider authorization, security, support, pricing and operational readiness are verified.

### 24.4 Audience and use-case discovery

Candidate audience groups to validate—not assume as finalized market segmentation—include individuals, developers, freelancers, startups, SMEs, established businesses, agencies, IT teams, enterprises, institutions, resellers/technology partners and organizations needing managed technology services. Phase 00/01 must identify priority personas, jobs-to-be-done, purchasing authority, technical skill, support expectations and the first high-value use cases.

At minimum, investigate:
- a customer discovering and comparing a service, requesting a quote or purchasing a plan;
- a developer creating a project, obtaining sandbox credentials, testing an API and configuring webhooks;
- an organization administering members, workspaces, projects, services, roles and invoices;
- an operator provisioning and supporting a customer service across internal and external providers;
- finance staff reconciling invoices, payments, control numbers, refunds and exceptions;
- infrastructure/security staff monitoring resources, incidents, risk, capacity and provider health;
- a reseller/partner onboarding, managing delegated customers and understanding commercial boundaries.

These are discovery scenarios, not a claim that every workflow or persona has already been approved.

### 24.5 Minimum cross-catalog service lifecycle

For every service/product, analyse the complete lifecycle, as applicable:
1. discover, search, compare and understand prerequisites;
2. select product, plan, region, configuration and add-ons;
3. obtain a quote or place an order;
4. authenticate, authorize and satisfy eligibility/KYC/provider requirements where applicable;
5. pay or use an approved invoicing/credit arrangement;
6. create invoice/receipt and reconcile financial state;
7. provision through an owned system, provider adapter or controlled manual workflow;
8. configure resources, domain, credentials, integrations and security;
9. deliver onboarding, documentation and operational guidance;
10. expose status, usage, quotas, health, logs and support;
11. change plan, scale, renew, suspend, resume or cancel;
12. handle failure, timeout, provider outage, refund, reversal, migration, export and closure.

Not every service has identical steps. Define service-specific state machines, prerequisites, entitlements, approvals, idempotency, compensation and customer-visible statuses. Do not equate order paid, payment confirmed, provisioning complete and service operational; they are separate states.

### 24.6 Payment and Tanzania control-number requirements

Control-number management is a first-class capability within the payment/billing domain, not merely a text field on an invoice. Preserve a distinct control-number lifecycle and its relationship to (but separation from) invoice, order, customer, organization, subscription and payment transactions. Analyse generation/request, assignment, uniqueness, provider reference, amount and currency, issue time, expiry, renewal/replacement, cancellation, status query, payment matching, duplicate notifications, partial/under/overpayment where supported, unmatched/late payment, reversal/refund, reconciliation, exception queues, audit history and customer/staff notifications.

The platform must verify payment using authenticated provider callbacks and/or provider-side status queries with signature validation, idempotency and replay protection. Screenshots, uploaded receipts or customer assertions alone must never mark a payment as confirmed. Provider capabilities, government/bank collection rules, fees, settlement, refund rules and legal/regulatory treatment must be verified for Tanzania before live operation. Sandbox simulations must be isolated and conspicuously labelled as simulated. Never assume TEKORA is a licensed payment processor, bank, custodian or collection authority.

### 24.7 Research and design execution constraints

OpenCode is the primary implementation agent and owns repository implementation within the explicitly authorized scope. It must know and document the frontend, backend, database and supporting technologies selected after validation. v0, Figma and reference platforms are research/prototyping aids; they must not silently become competing repository implementers.

For each major service family and workflow, research relevant real products and document the observation date/source, user journey, information hierarchy, navigation, content density, forms/tables, interaction states, typography, responsive behaviour, accessibility, performance, error recovery, adopted/adapted/rejected patterns and rationale. The named benchmark set is Stripe, Vercel, Cloudflare, DigitalOcean, Supabase, Twilio and Linear. Research must be genuine; do not claim a benchmark was inspected without evidence. Produce an original TEKORA design.

Typography is a mandatory research decision: evaluate distinct premium, highly legible font families and weights for headings, body, UI labels, numbers/data and code/technical content. Test Swahili, English, special characters, dense data, mobile and responsive rendering, accessibility, performance, licensing and fallback. Do not choose a generic default merely for convenience.

### 24.8 Discovery-before-specification rule

The user's requested order was to understand the platform, explore the service landscape and provide an overview/recommendations before locking detailed requirements or writing implementation code. Preserve that sequence:
- Phase 00: reconcile original idea, context, actors, outcomes, constraints and assumptions;
- Phase 01: analyse all 22 categories, subservices, alternatives, market/provider gaps and delivery feasibility;
- Phase 02: convert validated findings into traceable, testable requirements;
- Phase 03: research and design user experiences;
- Phase 04: validate technical architecture, including the exact frontend, backend, database and integration stack;
- implementation only after the relevant design and phase approvals.

Do not treat the current draft catalog or proposed technology stack as proof that discovery, requirements, architecture or implementation is complete.

### 24.9 Explicit exclusions and deferred matters

- Company ownership structure, shareholding and broader company-ownership discussion are deferred until after the platform itself has been defined; do not derail product discovery with them.
- A separate Wi-Fi management system is outside TEKORA unless the user explicitly approves a future integration or scope change.
- No requirement to own all infrastructure; choose delivery per service based on value, control, cost, capability, compliance and provider terms.
- Do not force all 22 categories into the first release, but do not erase advanced categories from the full catalogue.
- Do not invent provider partnerships, registrar accreditation, payment licensing, regulatory approval, certifications, service availability, benchmarks or implementation evidence.

### 24.10 Reconciliation status

The currently published documents cover the principal platform vision, three experience surfaces, 22 draft categories, shared engines, Developer Hub, internal operations, customer lifecycle, payment/control-number separation, UX and typography, architecture direction, security, integrations, roadmap and documentation governance. This reconciliation section makes the originating service proposition, company-as-platform-operator distinction, all-catalog-versus-launch distinction, candidate audiences, end-to-end lifecycle, Tanzania control-number safeguards, research-tool ownership and discovery order explicit.

This is a document-level reconciliation based on the available planning context; it is not a verbatim transcript of every historical message and does not prove that every future requirement has been discovered. Items marked candidate, proposed, pending or requiring validation must retain those statuses until evidence or explicit user approval changes them.
## 25. Full original planning requirements — platform-wide capabilities and operating model

This section adds requirements recovered from the earliest TEKORA planning context. Read it with the 22-category catalog and shared-engine sections.

### 25.1 Product philosophy and breadth
The user requested a complete, professional and differentiated technology ecosystem for Manyusi Technologies, not a simple service-listing site. Do not overlook a useful technology capability if it can be delivered securely and efficiently. This is a discovery/completeness rule, not a demand to launch everything immediately.
For every candidate capability, document customer problem/value, actor/workflow, native management versus external integration, delivery model, dependencies, core/advanced/optional classification, feasibility, provider/geography constraints, cost-to-serve, support/security/legal risks, priority, acceptance criteria and evidence. Defer by status and rationale; never silently omit advanced capabilities.

### 25.2 Unified control plane and dependency graph
Connect identity, organizations, projects, entitlements, catalog, bundles, orders, provisioning, provider integrations, billing, usage, monitoring, support, security, audit and notifications. Model dependencies between services such as domains/DNS, compute, network, databases, storage, email, certificates, secrets, backups, monitoring and deployment. Define prerequisite checks, compatibility, provisioning order, ownership boundaries, failure propagation and teardown/compensation. Do not build isolated category storefronts.
Investigate a unified control plane/dashboard and permission-aware visual infrastructure/resource map showing verified customer resources, environments, dependencies, provider boundaries, health and operational status. Never fabricate topology.

### 25.3 Customer, organization and developer workspace
Discover one identity/account with organization/workspace membership; organization/project/environment hierarchy including development, staging and production; resource ownership/delegation; invitations and membership lifecycle; RBAC/IAM; MFA/SSO options; scoped API keys/secrets, rotation and revocation; audit; and unified views of services, orders, resources, subscriptions, invoices, payment/control-number status, usage, quotas, alerts, support, documents and change history. Final tenancy, role matrix, permissions and account recovery remain explicit design decisions before implementation.

### 25.4 Developer and integration experience
Developer Hub includes API marketplace/catalog, project-scoped credentials, isolated sandbox, request/response test workspace, headers/parameters/body/auth, environment variables, collections/history, SDKs, versioned interactive docs, examples, webhook endpoint configuration, signing secrets, event delivery history, safe retry/replay, idempotency guidance, quotas/rate limits, usage/error analytics and test-to-live workflow. Investigate one-click deployment/integration templates only where provider-supported; disclose required permissions/secrets, resource creation, costs, rollback and cleanup. AI developer assistance must be grounded in approved API specs/schemas/docs and must not invent behavior.

### 25.5 Provisioning and resource lifecycle
The originating operating concept included automated provisioning after verified payment. Define per-product workflow: validate eligibility/order/pricing snapshot/payment or approved credit/manual-invoice path; idempotently grant entitlement; create/request resource; configure OS/runtime/network/firewall/access; apply secrets safely; enable included monitoring/backup/security; verify health; deliver credentials securely; notify customer/staff and audit. Keep order, payment, control-number, entitlement, provisioning and operational service states separate. Model queueing, retries, timeout, duplicate events, compensation, operator intervention, rollback and provider outages. Never rely on screenshots or unverified callbacks and never expose secrets in logs/notifications.
Resource inventory must track owner, provider, region, configuration, dependencies, health, quota, cost, changes, scaling, renewal, suspension, migration, backup/restore and approved deletion evidence.

### 25.6 Provider abstraction, multi-provider and portability
Remain independent of a single provider where practical through adapters and stable internal contracts while retaining provider-specific differences. Multi-provider/failover is conditional on technical capability, contract permission and testing. Record capability matrices. Never imply identical APIs, credentials, prices, regions, SLAs, latency, data location or failover. Failover/migration must account for consistency, replication, DNS TTL/propagation, RTO/RPO, cost, consent, rollback, export/import validation, downtime and source-data deletion.

### 25.7 Internal company operations
Discover staff workspaces and least-privilege roles for sales/leads/onboarding/account management; CRM/customer success; quotations/contracts/approvals/renewals; order and service-delivery coordination; finance (invoices, payments, control numbers, credits, refunds, reversals, settlement and reconciliation); provisioning; engineering/releases/change/incident management; infrastructure/network/cloud/capacity/provider health; cybersecurity/access reviews/risk/audit; helpdesk/ticket routing/priorities/escalation/SLA timers/knowledge base; partner/reseller onboarding and delegated administration; and professional-services project delivery (scope, milestones, assigned staff, work logs, deliverables, customer acceptance and closure).
Separate duties for sensitive finance/security/infrastructure actions. Provide approval workflows, accountable assignment, escalation and auditable events. Staff must not automatically receive unrestricted access to customer secrets or content.

### 25.8 Commercial and billing lifecycle
Analyse catalog pricing, quotes, contract terms, orders, tax/fees, invoices, receipts, payment, control numbers, subscriptions/entitlements, metering/overage, credits, refunds/reversals, reconciliation, renewals, suspension and cancellation. Consider fixed recurring, usage-based, one-time, add-on, bundle and professional-service quote models where relevant. Version pricing and preserve accepted quote/order price snapshots. Validate Tanzania tax/provider fees and commercial rules; do not invent them.

### 25.9 Tanzania and localization
Tanzania is the initial context. Research TZS, local payment/bank/mobile-money options, control-number/reference-payment pathways, invoices/receipts, privacy, tax, domain registry and .tz registrar rules, and applicable provider/regulatory obligations. Candidate ecosystem names mentioned in planning include M-Pesa, Airtel Money, Mixx, HaloPesa, T-Pesa, CRDB and NMB; these are research candidates, not confirmed integrations or partnerships. Discover Swahili/English localization, dates/time zones, phone formats and multilingual typography.

### 25.10 Candidate differentiators
Validate these candidates rather than treating them as guaranteed MVP: unified control plane; visual infrastructure map; AI infrastructure assistant grounded in authorized logs/metrics; intelligent cost optimization; multi-cloud/provider flexibility; visual automation studio; reseller/white-label ecosystem and third-party marketplace; one-click deployment templates; automated provisioning and lifecycle operations. AI must be permission-scoped and evidence-grounded; consequential actions require human approval. Cost advice must disclose assumptions and trade-offs. No destructive automatic action without authorization.

### 25.11 Implementation entry gate
Before implementation, each accepted capability must have stable requirement ID/source/decision status, actor/value, functional and non-functional requirements, data classification/tenant scope, API/UI/provider contracts, dependencies/state transitions/failure compensation, security/privacy risks, measurable acceptance criteria, test/evidence method, documentation location, priority/phase and explicit approval. Kickoff requires an approved MVP boundary plus preserved long-term roadmap, validated stack/architecture, approved UX/design system, provider capability matrix, permission model, payment/control-number contracts, deployment/environment plan, threat model, test strategy and phase exit gates. Missing evidence remains NEEDS VERIFICATION or BLOCKED.

### 25.12 Provenance
This is a structured reconstruction of additional requirements available from the earliest planning context, not a verbatim export of every message. Keep explicit user requirements separate from assistant proposals and unresolved validation; never promote a proposal to an approved decision without user acceptance.
## 26. Implementation-ready specification for all 22 service categories

This section upgrades the catalog from a feature inventory into an engineering specification baseline. It supplements Sections 1–25. It does not assert that any product, provider, integration, certification, commercial agreement or capability is already available. Every category must be decomposed into approved product offers and traceable requirements before implementation.

### 26.0 Mandatory specification contract for every category

For every category and each product within it, discovery and requirements MUST complete this record. Unknowns are explicitly marked TBD / NEEDS VERIFICATION / BLOCKED with an owner and resolution phase; implementation agents must never guess:
1. Purpose, customer problem/outcome, target actor, measurable value, use cases and exclusions.
2. Product decomposition: product families, SKUs/offers, plans, add-ons, bundles, optional/advanced features and sandbox/demo boundaries.
3. Delivery model: owned, managed, integrated, authorized reseller, partner-delivered or customer-provided; actual operator, support boundary and provider/contract dependencies.
4. Eligibility/prerequisites: region, identity/KYC where applicable, ownership proof, technical dependencies, quota/capacity, provider account, permissions and approvals.
5. Configuration schema: selectable fields, types, defaults, validation, constraints, secret classification, immutable/mutable fields and plan limits.
6. Lifecycle state machine: statuses, actors, guards, transitions, timeouts, retry and customer-visible progress.
7. Customer workflows: discovery, comparison, configuration, quote/order, checkout, onboarding, dashboard, change/scale, usage, support, renew, migrate, export, cancel and recover.
8. Staff workflows: approval, fulfilment, provider operations, exceptions, finance reconciliation, incident response and audit.
9. Data model: entities, identifiers, relationships, tenant/org/project/resource ownership, source of truth, classification, retention, export and deletion.
10. API/event contracts: operations, auth/scopes, idempotency, pagination, errors, limits, versioning, webhooks, signatures, retries, ordering and replay.
11. Provisioning: adapters/workers, orchestration, secret injection, retries/backoff, idempotency, compensation/saga, rollback, reconciliation and teardown.
12. Security/abuse: threat model, least privilege, tenant isolation, encryption, secrets, audit, rate/abuse controls, fraud, approvals and separation of duties.
13. Reliability/operations: evidence-backed SLI/SLO/SLA, health checks, monitoring, alerting, runbooks, incident escalation, backup/restore, RTO/RPO and capacity.
14. Commercial model: pricing metric, limits, recurring/one-time/usage charges, quote rules, price snapshots, refunds, cancellation, proration and reconciliation.
15. UX/accessibility/localization: responsive states, accessible controls, keyboard/focus, Swahili/English, time zones, currency and provider disclosures.
16. Testing/acceptance: unit, integration, contract, provider sandbox, E2E, security, performance, resilience, accessibility, migration/restore and negative tests.
17. Documentation/support: customer docs, operator runbooks, API reference, troubleshooting, limitations, support ownership and change log.
18. Traceability: stable ID in the TEK-CAT-XX-### format, source/decision status, priority, phase, dependencies, acceptance evidence and approval.

Use shared engines for customer, pricing, order, billing, entitlement, provisioning, provider, notification, audit and support. Category-specific domain rules remain in their bounded context. Do not create a microservice solely because a category exists.

### 26.1 Category 01 — Domains, DNS & Internet Services
**Product families:** domain search/availability; registration, transfer and renewal; portfolio/contact management; DNS hosting; advanced traffic steering; DNS security; certificate lifecycle integrations; domain/IP/network intelligence; CDN/edge; migration and recovery.
**Functional scope:** RDAP-first lookup with fallback and source/time disclosure; availability confidence; TLD eligibility and premium/reserved handling; registration, transfer-in/out, renewal and TLD-specific grace/redemption/pending-delete lifecycle; registrant contacts, verification, privacy/proxy where permitted, locks, nameservers and auth/EPP codes; DNS zones/records, bulk import/export, templates, validation, version/diff/rollback, TTL and propagation diagnostics; DNSSEC; GeoDNS, weighted, latency and failover policies with health checks; reverse DNS/IP/ASN/CIDR/BGP integrations; certificate inventory, CSR/validation/issuance/renewal/revocation through authorized CAs; CDN configuration; abuse/phishing/typosquat/expiry monitoring; SPF/DKIM/DMARC/MTA-STS/TLS-RPT checks; migration preflight, cutover, rollback and verification.
**Controls/workflows:** prove domain ownership before sensitive changes; step-up auth/approval for transfer, registrant, nameserver and DNSSEC changes; protect auth codes/private keys; detect conflicting records; stage/diff bulk changes; audit and notify verified contacts. TLD rules differ. .tz offers require verified registrar authorization and current registry/TCRA rules. Never claim registrar/CA status without evidence. Failover is subject to TTL, caching and provider behavior.
**Data/integrations:** domain, TLD policy, registrar account, registrant, transfer, zone, record, DNSSEC metadata, certificate, IP allocation, provider account, change set and audit. Integrate registrar/registry, RDAP, DNS providers, authorized CAs, CDN and IP/ASN/BGP sources.
**Acceptance:** TLD lifecycle matches provider rules; unauthorized changes fail; DNS import/export round-trips; rollback is tested; expiry alerts work; security findings cite evidence; provider outage is visible; .tz sales remain disabled until authorization is verified.

### 26.2 Category 02 — Web Hosting, Application Hosting & Compute
**Product families:** shared/reseller hosting; managed WordPress/CMS; static hosting; PHP/Node/Java/Python/.NET runtime; VPS; dedicated/bare metal; managed application hosting; staging and migration.
**Functional scope:** plan/region/OS/runtime catalogue; CPU/RAM/storage/bandwidth/process/inode/database/mail limits; domain/SSL attachment; site/app creation; Git/artifact deployment; build/start commands; env vars and secret references; database/cache attachment; SSH/SFTP/console; safe file manager if offered; cron; logs/metrics/health; staging/clone/restore; backups/snapshots; resize/upgrade/downgrade; IP/firewall; DNS integration; deployment history/rollback; malware and abuse controls.
**Provisioning:** validate plan capacity; reserve quota; create isolated account/VM/runtime; configure network/firewall/OS/runtime; attach storage/domain/certificate; inject secrets; create database/backup/monitoring; run readiness probes; deliver scoped access; reconcile actual provider resources with desired state. No default root credential exposure; use scoped, rotatable access.
**Operations:** capacity/noisy-neighbour controls; throttling; abuse suspension; patching/maintenance; migration; restore drills; provider outage/degraded state; export and secure deletion. Disclose TEKORA versus customer responsibility.
**Acceptance:** tenant isolation; plan limits; deploy/rollback; scoped SSH/secrets; proven backup restore; metering reconciliation; capacity-aware resize; idempotent suspend/resume/cancel; secret redaction.

### 26.3 Category 03 — Cloud Infrastructure & Virtualization
**Product families:** VMs, bare metal, virtual networks, block/object storage, snapshots/images, load balancers, public IPs, private networks and autoscaling.
**Functional scope:** region/zone/flavour/image catalogue; create/resize/reboot/stop/start/rebuild/delete; SSH keys and cloud-init; network/subnet/router/security groups; public/floating IP; volumes/snapshots; image templates; load-balancer listeners/pools/health probes; firewall/routing; quota/capacity; tags; topology; drift; cost/usage; IaC/API integration and change preview.
**Controls:** project ownership; approvals for destructive actions; quota reservation; policies for public exposure/open ports/unencrypted disks; immutable audit; snapshot consistency caveats; prevent accidental deletion of attached/critical resources; disclose region/data residency/provider constraints. Normalization must retain provider-specific fields.
**Acceptance:** provider state reconciliation; duplicate requests do not create duplicate resources; cross-project access denied; estimates disclose assumptions; network changes audited; snapshot/restore and deletion safeguards tested; outages do not show false healthy state.

### 26.4 Category 04 — Containers, Kubernetes & Runtime
**Product families:** image registry; container application runtime; managed/self-managed Kubernetes; clusters/node pools; Helm; ingress/service mesh integrations; GitOps and workload observability.
**Functional scope:** repositories/tags/immutable digests/retention/scanning; cluster create/upgrade/scale/delete; node pools/autoscaling; namespace/project mapping; workload/deployment/statefulset/job/cronjob; config and secret references; service/ingress/load balancer; storage/PVC; Helm install/upgrade/rollback; GitOps reconciliation; admission policies; logs/metrics/traces; cluster backup/restore; version compatibility/deprecation.
**Controls:** cluster RBAC and namespace isolation; image provenance/signing; admission policies; secret encryption; network policies; resource quotas; privileged workload restrictions; patching; upgrade preflight/rollback. Kubernetes is not default for simple workloads when a smaller runtime is safer or cheaper.
**Acceptance:** cross-namespace access denied; image digest/scan traces to deployment; failed rollout rollback; upgrade compatibility checked; quotas enforced; restore demonstrated; health not inferred only from desired replica count.

### 26.5 Category 05 — Networking & Connectivity
**Product families:** virtual networks, VLAN/subnets, IPAM, public/private IP, VPN, routing, load balancing, bandwidth/QoS, private links, SD-WAN/BGP integrations; managed Wi-Fi only if separately approved.
**Functional scope:** address allocation/conflict detection; CIDR/IP calculator and inventory; route tables/gateways/NAT; firewall/security policies; VPN peer/site configuration, tunnel health and key rotation; DNS; load-balancer listeners/pools; bandwidth plans/usage; topology; latency/loss/throughput monitoring; change windows and rollback; BGP/ASN visibility where supported.
**Controls:** least-privilege network roles; approval for public exposure/routes/firewall-wide rules; validation/dry-run; VPN secret protection; audit; DDoS/abuse escalation; customer-owned boundaries. Do not merge the separate Wi-Fi project.
**Acceptance:** IP conflicts prevented; unauthorized route/firewall changes denied; VPN secrets not logged; rollback tested; tunnel failures detected; topology identifies source/time; Wi-Fi remains excluded absent approval.

### 26.6 Category 06 — Database Services
**Product families:** managed PostgreSQL, MySQL, MariaDB, SQL Server and justified NoSQL engines; Redis/cache; migration and performance services.
**Functional scope:** engine/version/region/instance/storage catalogue; create cluster/database/users/roles; private/public connectivity; allowlists/TLS; parameter groups; backup/retention/PITR; replicas/read endpoints; HA/failover; engine upgrades/maintenance; query/connection/storage metrics; slow query insights; migration/import/export; pooling; encryption/key management; restore to new instance and PITR validation.
**Controls:** designated system of record; Redis is not silently substituted for durable storage; tenant isolation; least privilege; encrypted storage/connections; secret rotation; audit; network isolation; patching; backup immutability where supported; production change approval. No public database port by default.
**Acceptance:** restore/PITR data verified; role boundaries tested; backup age/retention visible; failover/RPO measured; migration preflight and recovery plan; telemetry does not leak secrets or customer data.

### 26.7 Category 07 — Storage, Backup & Disaster Recovery
**Product families:** object/block/file storage; S3-compatible storage; snapshots; backup management; replication; archive; DR planning and restore testing.
**Functional scope:** buckets/volumes/shares; access policies; lifecycle/tiering; versioning; object lock/immutability where supported; encryption/key ownership; multipart transfer; quotas; replication; snapshots; backup schedules/retention/legal hold; file/object/volume/database/application restore; cross-region copies; recovery plans; RTO/RPO; backup verification; export and deletion.
**Controls:** private-by-default buckets; public exposure warning/approval; separate backup administration; ransomware-resilient credentials; immutable copies where supported; encryption; retention/deletion safeguards. Backup success is not proof of recoverability.
**Acceptance:** restore drill evidence; checksum/integrity checks; retention/deletion correctness; measured RTO/RPO; replication lag and provider limits visible.

### 26.8 Category 08 — Email Infrastructure
**Product families:** business mailboxes; domains/aliases/groups; transactional API; consent-based bulk email; SMTP relay; archive/migration; deliverability/security.
**Functional scope:** domain verification; mailbox lifecycle/quota; aliases/groups/forwarding; migration; IMAP/POP/SMTP; API/SMTP credentials; templates/events; sender verification; SPF/DKIM/DMARC/MTA-STS/TLS-RPT diagnostics; bounce/complaint/suppression/unsubscribe; delivery analytics; reputation guidance; spam/malware filtering; archive/retention only where lawful and contracted.
**Controls:** lawful basis/consent for bulk email; suppression and unsubscribe; sender verification; rate/abuse limits; credential rotation; privacy/retention; anti-spoofing; no open relay; mailbox access audit and tenant isolation.
**Acceptance:** unauthorized sender rejected; DNS checks evidence-based; bounce/complaint updates suppression; unsubscribe respected; secrets redacted; migration reconciled; no unsupported deliverability guarantees.

### 26.9 Category 09 — SMS, Voice & Omnichannel Communication
**Product families:** SMS/OTP; transactional messaging; voice; virtual numbers; IVR; approved WhatsApp/other channels; push; unified API.
**Functional scope:** provider/channel capability catalogue; sender ID/number provisioning; localized templates; recipient normalization; consent/opt-out; message/call creation; delivery receipts/status; OTP generation/verification/expiry/rate limits; voice routing/IVR/recording controls; scheduling where lawful; webhook events; usage/cost metering; provider health/fallback where supported; analytics/suppression.
**Controls:** protect OTPs/phone numbers; prevent enumeration, SMS pumping and toll fraud; rate-limit by actor/IP/device/tenant/destination; consent/opt-out; approved sender IDs; recording consent/legal validation; fallback only when channel semantics and contracts allow.
**Acceptance:** idempotent duplicate handling; OTP expiry/replay protection; opt-out enforcement; accepted versus delivered states distinguished; outage/fallback visible; usage reconciled; sensitive message content minimized in logs.

### 26.10 Category 10 — Payment Infrastructure, Billing & Fintech Integrations
**Product families:** payment provider integrations/orchestration; authorized mobile money/bank/card acceptance; invoices/receipts; subscriptions; usage billing; refunds/reversals; control-number/reference payments; reconciliation.
**Functional scope:** country/currency/channel capability matrix; checkout/payment intent; invoice/receipt lifecycle; provider status query; authenticated webhook intake; signature/idempotency/replay/event ordering; refunds/reversals/disputes where supported; settlement/fees; statement reconciliation; subscriptions/retries/proration; metered usage; credits/adjustments; control number create/assign/verify/expire/renew/replace/cancel; unique mapping to customer/org/order/invoice/subscription; partial/under/overpayment and unmatched/late transaction handling where supported; exception queues/audit.
**Controls:** no raw card storage unless separately approved compliant architecture; prefer hosted/tokenized flows; sandbox/live isolation; no live movement before legal/provider approval; screenshots are not proof; trusted signed callback or provider query; dual control for refunds/manual adjustments; reconcile gross/fees/net/currency. No unsupported claim that TEKORA is a bank, custodian, licensed processor or government collection agent.
**Acceptance:** duplicate callback cannot double-credit; forged/replayed callbacks rejected; payment confirmed only with trusted evidence; control-number, payment and invoice lifecycles separate; reconciliation exceptions visible; settlement balances; sandbox cannot cause live effects; late callbacks recover safely. Validate Tanzania tax/fees/payment/control-number rules and provider contracts.

### 26.11 Category 11 — Developer Tools & API Infrastructure
**Product families:** API gateway/management; catalog/marketplace; developer portal; auth/token services; webhook infrastructure; event broker; schema registry; SDK/docs; API monetization/analytics.
**Functional scope:** API product/version lifecycle; OpenAPI/schema validation; routing; OAuth/OIDC/API key/mTLS where appropriate; scopes; quotas/rate/burst/concurrency limits; version/deprecation; developer apps/projects; credential issue/rotate/revoke; sandbox fixtures; webhook subscriptions/signing/retry/dead-letter/replay; event logs; SDK generation/release; usage/error/latency analytics; contract tests/changelog.
**Controls:** secret storage/one-time display; scope isolation; gateway abuse protection; request size/timeouts; PII redaction; webhook SSRF and destination verification; signature timestamp/replay window; tenant quotas; compatibility gates. Catalog listing does not mean API is live.
**Acceptance:** published API matches deployed contract; revoked key fails; limits deterministic; webhook signatures/retries work; sandbox isolated; breaking changes follow version policy; SDK samples compile against documented API.

### 26.12 Category 12 — Software Development, DevOps & Deployment
**Product families:** source control integrations; CI/CD; build runners; environments; artifact management; IaC; release/change management; preview deployments/rollback.
**Functional scope:** repository connection with minimal scopes; webhook verification; build/test/package pipelines; isolated runners; environment promotion; protected branches/approvals; artifact retention/signing; rolling/blue-green/canary deployment where supported; secrets injection; health checks; rollback; preview environments; IaC plan/apply approvals; release notes; SBOM/dependency scanning; audit/cost.
**Controls:** ephemeral isolated runners; untrusted PRs cannot access production secrets; branch/environment protection; signed artifacts/provenance; secret masking; pinned dependencies; production/destructive IaC approval; least-privilege tokens; build network restrictions.
**Acceptance:** untrusted code cannot access protected secrets; artifact provenance traceable; failed deployment recovers safely; approvals enforced; webhook authenticity verified; runner cleanup prevents leakage; deployment state reconciles with target.

### 26.13 Category 13 — Cybersecurity & Information Security
**Product families:** posture assessment; vulnerability scanning; authorized penetration testing; WAF/DDoS and endpoint integrations; cloud/container posture; SIEM; incident response; advisory/managed security.
**Functional scope:** asset/scope inventory; written authorization/rules of engagement; safe scan scheduling/rate limits; finding severity/evidence/remediation; false-positive review; retest; attack-surface inventory; configuration baselines; threat intel; SIEM correlation; incident timeline/evidence/containment approval; risk register; advisory and evidence mapping.
**Controls:** no test without explicit authorization and scope; no destructive tests unless separately authorized; isolate customer data; secure evidence/chain of custody; disclosure/retention policy; emergency stop; separate tester/approver; no certification claims from tools.
**Acceptance:** scope enforced technically; findings reproducible and timestamped; false-positive review; closure requires retest; authorization audited; evidence access controlled; no out-of-scope target touched.

### 26.14 Category 14 — Monitoring, Observability & SRE
**Product families:** uptime/synthetic monitoring; infra/app metrics; logs/traces/APM; database/network/container monitoring; alerting/on-call; status pages; SLO/error-budget/capacity analytics.
**Functional scope:** agents/exporters/API ingestion; metrics/logs/traces; tenant labels/isolation; dashboards; regional synthetic probes; alert rules/dedup/group/routing/escalation/silence; incident lifecycle; status components/maintenance; SLI/SLO/error budgets; dependency maps; retention/sampling; anomaly/AI diagnostics; runbooks/postmortems.
**Controls:** minimize data and scrub PII/secrets; authenticated ingestion; cardinality/cost limits; access-controlled dashboards; alert fatigue controls; retention; separate public status from internal incident notes.
**Acceptance:** alert fires in defined test window; duplicate alerts group; SLO matches source data; tenant isolation; secrets scrubbed; regional failures identify source/time; status updates audited.

### 26.15 Category 15 — AI, ML & Automation Infrastructure
**Product families:** model/provider gateway; hosted inference; GPU/CPU compute; training/fine-tuning; model registry/evaluation; embeddings/vector/RAG; agent/workflow automation; AI governance/observability.
**Functional scope:** model/provider capability catalogue; credential management; routing/fallback with compatibility disclosure; prompt/model versions; inference endpoints; token/compute usage; quotas/budgets; latency/error/cost metrics; embedding/index lifecycle; dataset/model lineage; evaluation suites; guardrails; permission-aware retrieval; agent tool registry; approvals; feedback; deprecation/rollback.
**Controls:** tenant/data isolation; prompt injection/exfiltration threat model; no training on customer data without explicit policy/consent; PII minimization; provider retention disclosure; output validation; tool allowlists; least privilege; human approval for consequential actions; budget limits; distinguish generated output from evidence.
**Acceptance:** model route/version traceable; quotas enforced; RAG respects source permissions; tool actions authorized; evaluations precede release; fallback limitations disclosed; no cross-tenant data leakage.

### 26.16 Category 16 — Media, Video & Realtime Infrastructure
**Product families:** media storage/transformation; image processing; audio/video transcoding; VOD/live; CDN; WebRTC rooms; conferencing/classrooms; realtime messaging/presence; transcription/subtitles.
**Functional scope:** resumable upload; metadata/processing jobs; codecs/resolution profiles; thumbnails/transforms; HLS/DASH packaging; CDN origin; signed playback URLs/tokens; WebRTC signaling/ICE/TURN/SFU integration; rooms/participants/roles/presence/chat; recording consent/start/stop/retention; transcription/subtitles; playback QoE/bandwidth monitoring.
**Controls:** ownership/usage rights; recording/transcription consent; private-by-default media; signed expiring access; moderation/reporting where applicable; retention/deletion; regional processing disclosure; secure realtime tokens.
**Acceptance:** unauthorized playback denied; upload/transcode recoverable; manifests/renditions validated; participant permissions enforced; consent/retention enforced; QoE separates client/network/provider failure.

### 26.17 Category 17 — Data Engineering & Analytics
**Product families:** ingestion/connectors; ETL/ELT/CDC; stream processing; warehouse/lake; orchestration; data quality/lineage; BI/reporting/data science.
**Functional scope:** source connection and credential vault; schema discovery; batch/stream ingestion; CDC offsets/checkpoints; transformation versions; orchestration dependencies; retries/backfills; data contracts/schema evolution; quality rules; lineage/catalog; warehouse/lake; access-controlled datasets; dashboards/reports/exports; freshness/quality/cost observability.
**Controls:** classification/purpose limitation; least-privilege source access; encryption; PII masking/tokenization; lineage/audit; retention/deletion propagation; row/column access where supported; secret redaction; residency/cross-border transfer validation.
**Acceptance:** replay/backfill idempotent or reconciled; breaking schema detected; freshness/quality alerts; lineage source-to-output; permissions enforced; deletion/retention verified.

### 26.18 Category 18 — Business Applications & Digital Productivity
**Product families:** ERP/finance integrations; CRM; HRM; project/task management; collaboration/documents; workflow/forms; e-commerce; app marketplace; managed app lifecycle.
**Functional scope:** app catalogue/publisher verification; tenant provisioning; roles/SSO; configuration; user/license assignment; data import/export; integrations/sync; workflow; audit; managed updates/version compatibility; backups; seat billing; health/support; marketplace review/approval/deprecation.
**Controls:** vendor due diligence; permission/data-sharing disclosure; tenant isolation; least privilege; SSO lifecycle; token rotation; export at termination; update rollback; privacy/retention; distinguish TEKORA-built from third-party apps.
**Acceptance:** installation discloses permissions/cost; offboarding revokes access; sync failures visible/recoverable; tenant export works; versions traceable; support boundaries explicit.

### 26.19 Category 19 — IT Consulting, Managed IT & Professional Services
**Product families:** discovery/consulting; software engineering; cloud/network/database/DevOps implementation; managed IT/helpdesk; audits/training; migration/support retainers.
**Functional scope:** lead/opportunity; discovery/requirements; scope of work; quote/contract; SOW assumptions/exclusions/change requests; staff assignment; schedule/milestones; time/work logs; deliverables/evidence; acceptance/sign-off; support retainer/SLA; approved expenses; milestone invoicing; handover/knowledge transfer/closure.
**Controls:** written authorization for access/security work; data handling agreement; temporary least-privilege access; change approval; timesheet integrity; IP/licensing terms; confidentiality; project separation and evidence retention.
**Acceptance:** no work before approved scope; milestones/change requests audited; customer acceptance evidence; time/billing reconcile; access revoked at closure; handover docs complete.

### 26.20 Category 20 — IoT, Smart Systems & Connected Infrastructure
**Product families:** device registry/provisioning; MQTT/connectivity; telemetry; fleet management; smart building/industrial/fleet; digital twins; automation; firmware/OTA.
**Functional scope:** secure device onboarding/identity; certificates/keys; device shadow/twin; MQTT topics/ACLs; telemetry schemas; command/control acknowledgement; fleet grouping; connectivity status; firmware versions/staged rollout; OTA signing/rollback; rules/automation; simulator; device health/battery/network; inventory/decommissioning.
**Controls:** unique device identity; secure boot/firmware verification where supported; credential rotation/revocation; topic isolation; command authorization; replay protection; canary OTA/rollback; ownership/consent; protect location/industrial data.
**Acceptance:** unauthorized devices cannot publish/subscribe/command; OTA signatures verified; failed rollout recovers; decommission revokes credentials; stale telemetry visible; simulator labelled and isolated.

### 26.21 Category 21 — Digital Trust, Compliance & Identity
**Product families:** IAM/SSO/MFA; OAuth/OIDC/SAML federation; identity verification integrations; PKI/certificate lifecycle; digital signatures; consent/privacy; compliance evidence/vendor risk.
**Functional scope:** identity lifecycle; federation/trust configuration; MFA enrollment/recovery; session/device management; access requests/approvals; role reviews; service accounts; SCIM where supported; signing/verification; key/certificate lifecycle; consent capture/withdrawal; data-subject requests; policy/evidence mapping; vendor risk; audit exports.
**Controls:** phishing-resistant MFA where supported; secure recovery; session revocation; least privilege; key custody boundaries; signature/trusted timestamp evidence; consent purpose/version; data minimization; legal basis/retention; no unsupported assurance/certification claims.
**Acceptance:** revoked identity loses access per policy; MFA recovery resists takeover; federation maps least privilege; signatures validate against trust material; consent withdrawal propagates; evidence traces to source/date.

### 26.22 Category 22 — Licensing, Software Distribution & Digital Products
**Product families:** software marketplace; license issue/activation/validation; seat/subscription entitlement; private downloads; package/container registries; publisher onboarding; software updates.
**Functional scope:** publisher/artifact onboarding; malware/vulnerability/signature/SBOM checks; release/version/channel; license types (named user, seat, device, subscription, perpetual, trial, offline where permitted); activation/deactivation/transfer; grace/offline validation; entitlement/usage; download authorization; package repositories/access tokens; update notices; rollback/revocation; refund/cancellation and publisher settlement where applicable.
**Controls:** artifact provenance/signing; anti-abuse without invasive fingerprinting; token protection; publisher rights/distribution authorization; vulnerability response/takedown; supply-chain policy; offline revocation limitations; export/privacy.
**Acceptance:** tampered/unsigned artifacts rejected per policy; seats cannot exceed entitlement unless approved; offline revocation limits disclosed; package access scoped; version/publisher traceable; refunds reconcile with entitlement.

### 26.23 Cross-category integration and dependency contracts
Model dependencies explicitly: identity/org/project/IAM; catalog/pricing/quote/order/payment/billing/subscription/entitlement; provisioning/workflow/provider adapters/resource registry; DNS/domains/certificates/network/compute/containers/databases/storage/email/communications/media/observability/security; secrets/KMS/audit/notification/support/policy; source-evidenced usage/metering/cost/analytics; approved API/SDK/webhook/sandbox contracts. For each dependency define owner, contract/version, provisioning order, readiness condition, failure behavior, retry, compensation, deletion order and test evidence. Avoid circular dependencies and duplicate sources of truth.

### 26.24 Category implementation package and exit gate
Before a category enters implementation its package must include: approved scope and product/SKU breakdown; requirements register with IDs and provenance; customer/staff journeys; state machine; configuration schema and entitlement matrix; data model/tenant boundaries; API/event/provider contracts; provider capability/region/contract matrix; UX flows and responsive states; threat model/abuse cases; pricing/billing/metering; runbooks/support model; test plan and measurable acceptance; customer and operator docs; dependency map; rollout/rollback/migration/deletion plan; explicit approvals and unresolved-risk register.
A category is DONE only when implementation, tests, provider/sandbox evidence, security review, operational readiness, documentation and user acceptance gates pass. UI existence or HTTP 200 is not proof. Use DONE / PARTIAL / BLOCKED / MISSING / BROKEN / NEEDS VERIFICATION.
## 27. Second-pass category depth audit and product engineering requirements

### 27.1 Why this second pass is mandatory

Section 26 provides an implementation-oriented baseline, but its category entries are not yet detailed product specifications for every possible offer. They intentionally do not invent vendor-specific APIs, final prices, legal authority, provider coverage, exact SLAs or implementation decisions. Before a category is authorized for build, the team must perform the deeper product engineering analysis below. Do not interpret inclusion in the catalog as a promise that every capability launches in the first release.

### 27.2 Required product decomposition for every category

Each category must be decomposed into independently understandable product capabilities and customer-facing offers. For every candidate product, record:
- Product name and stable product ID; category/subcategory; short customer-facing description; target customer segment and primary use case.
- Core capability, optional capabilities, add-ons, exclusions, prerequisites and dependencies.
- Delivery type: TEKORA-owned software/service; TEKORA-operated infrastructure; third-party integrated service; authorized reseller; partner-delivered service; customer-managed resource. Record the legal/commercial evidence required for each.
- Service boundary and responsibility matrix: what TEKORA operates, what the upstream provider operates, what the customer configures, who handles support and who owns incident communication.
- Availability model: countries/regions, currencies, languages, supported customer types, provider coverage, restrictions and explicit unsupported cases.
- Plan/SKU design: billing unit, included allowance, overage, quotas, burst limits, upgrade/downgrade behavior, trial/sandbox eligibility, renewal and cancellation.
- Provisioning method: automated API, event-driven workflow, infrastructure-as-code, operator-assisted, provider portal/manual or customer self-service; label manual operations honestly.
- Customer lifecycle and operator lifecycle, including states, transition guards, retries, timeouts, compensation, recovery and irreversible actions.
- Required data, source of truth, ownership, retention, deletion/export, residency and audit evidence.
- Dependencies and failure propagation; degraded mode, retry, manual intervention and customer communication.
- Security classification, permission model, threat scenarios, abuse controls, compliance dependencies and approval requirements.
- Test evidence, measurable acceptance criteria, support documentation, runbooks, known limitations and change/deprecation policy.

### 27.3 Category-specific deeper product decomposition

These are candidate product workstreams to investigate and validate, not commitments that all will be launched or that every upstream provider supports them.

#### Category 01 — Domains, DNS & Internet Services
- Domain portfolio: search, watchlists, availability checks, registration, transfer, renewal, ownership/contact verification, registrant change, lock, privacy eligibility, expiry recovery and multi-domain bulk operations.
- DNS control: zones, records, templates, bulk changes, import/export, record validation, propagation checks, version history, approval, staged changes and rollback.
- Advanced DNS: DNSSEC, GeoDNS, weighted/latency routing, health-based failover, private DNS and multi-provider management where supported.
- Internet identity and security: RDAP lookup, WHOIS fallback where lawful, reverse DNS, IP/ASN/CIDR inventory, reputation, DNS security posture and email-domain authentication diagnostics.
- Certificate and edge lifecycle: certificate discovery, issuance/renewal integrations, expiry alerts, CDN/edge onboarding and origin protection.
- Migration and protection: registrar/DNS migration, preflight checks, TTL planning, cutover, post-cutover checks, rollback plan, typosquat/brand-abuse watch and domain recovery workflows.
- Resolve product boundaries: domain registrar versus reseller/referral; DNS operator versus DNS control-plane integrator; certificate authority versus ACME/CA integration; IP intelligence source versus authoritative allocation data.

#### Category 02 — Web Hosting, Application Hosting & Compute
- Hosting offers: shared, reseller, managed CMS, static site, application runtime, VPS, dedicated/bare-metal and managed application deployment.
- Runtime lifecycle: supported language/runtime versions, buildpacks or images, build/start commands, environment configuration, process model, health checks, logs, shell access and scheduled jobs.
- Website lifecycle: domain binding, TLS, redirects, staging, clone, deployment, backup, restore, migration, traffic management and content/runtime updates.
- Compute lifecycle: image catalogue, instance sizing, storage/network attachment, resize, reboot, rebuild, snapshot, firewall, rescue/recovery and decommission.
- Resource governance: CPU/RAM/I/O/process/inode/storage/bandwidth/database limits, burst policy, noisy-neighbour isolation, suspension and abuse review.
- Clarify what is a hosting plan versus a managed service, what control panel or runtime is used, and which customer actions are self-service versus operator-only.

#### Category 03 — Cloud Infrastructure & Virtualization
- Compute products: virtual machines, bare metal, GPU instances if actually available, images, instance groups and autoscaling.
- Network products: VPC/project networks, subnet, route, gateway, NAT, public IP, security group and load balancer.
- Storage products: block volumes, snapshots, images and object-storage integration, with clear ownership and backup boundaries.
- Infrastructure operations: provisioning, resize, stop/start, rebuild, migration, HA topology, maintenance, quota and resource inventory.
- Governance: policy templates, region restrictions, tagging, cost allocation, drift detection, change plans and approval for destructive/public resources.
- Distinguish cloud broker/control plane from infrastructure operator; disclose upstream region, availability, data residency and egress pricing.

#### Category 04 — Containers, Kubernetes & Runtime
- Registry: private/public repository, image push/pull, tags/digests, retention, access token, signing, scanning and replication.
- Application runtime: container app, job, scheduled job, environment, scaling, health, logs, rollout and rollback without requiring a full cluster for simple workloads.
- Kubernetes: managed cluster, node pool, namespace, workload, service, ingress, storage, autoscaling, upgrade and backup/restore.
- Delivery: Helm chart, GitOps source, deployment approval, progressive rollout and drift reconciliation.
- Governance: RBAC, network policy, resource quota, admission policy, image provenance, secret handling, cluster version lifecycle and cost visibility.
- Define the boundary between platform-as-a-service container runtime and customer-managed Kubernetes control.

#### Category 05 — Networking & Connectivity
- Network inventory and IPAM: address pools, subnet/CIDR planning, allocation, reservations, conflict detection, DNS/reverse DNS links and audit.
- Connectivity: site-to-site and client VPN, private links, peering, VLAN, virtual network, routing, NAT and gateway products.
- Traffic management: load balancing, health probes, bandwidth/QoS, traffic shaping and DDoS/provider integrations.
- Network operations: topology, config backup, change approval, reachability tests, latency/loss/throughput, tunnel lifecycle and incident diagnostics.
- Wireless/SD-WAN scope must be separately approved and must not silently absorb the independent Wi-Fi management project.
- Define which network equipment and connectivity services TEKORA owns, remotely manages, resells or merely monitors.

#### Category 06 — Database Services
- Managed database products by engine, version, region, topology and support tier; avoid promising engines not validated with a provider.
- Provisioning: instance/cluster, database, user, role, network access, TLS, parameter configuration and connection information.
- Availability: replicas, read endpoints, failover, maintenance, upgrade, scaling, connection pooling and planned migration.
- Data protection: automated backups, PITR, snapshots, export/import, restore drills, retention and deletion.
- Operations: query insights, slow-query diagnostics, connection/storage monitoring, capacity warnings and support escalation.
- Separate database hosting from database administration/consulting; define customer responsibility for schema, queries, patching and data correctness.

#### Category 07 — Storage, Backup & Disaster Recovery
- Storage products: object, block, file, archive, S3-compatible access, lifecycle tiers and transfer tools.
- Protection policies: schedule, frequency, retention, immutability, encryption, replication, legal hold and deletion.
- Recovery products: file/object restore, volume restore, database restore, application recovery, cross-region recovery and full environment recovery.
- DR planning: dependency map, runbook, recovery sequence, RTO/RPO target, test schedule, evidence and exception reporting.
- Storage operations: capacity, egress, API/request costs, replication lag, integrity checks and access review.
- Distinguish backup storage from independently recoverable backup service; define whether restore assistance is included or billable.

#### Category 08 — Email Infrastructure
- Mail hosting: domain onboarding, mailbox, alias, distribution group, forwarding, quota, migration and lifecycle administration.
- Transactional delivery: API/SMTP, templates, sender identity, event delivery, bounce, complaint, suppression and analytics.
- Campaign delivery: list consent, segmentation, scheduling, unsubscribe, suppression and policy enforcement, subject to applicable law and provider terms.
- Email security: SPF, DKIM, DMARC, MTA-STS, TLS-RPT, inbound filtering, anti-spoofing and domain posture monitoring.
- Deliverability operations: reputation signals, queue health, throttling, bounce classification, warm-up guidance and provider escalation.
- Define retention, archive, mailbox backup, discovery and customer access boundaries; never imply guaranteed inbox placement.

#### Category 09 — SMS, Voice & Omnichannel Communication
- Messaging: SMS, OTP, transactional, bulk/campaign, templates, sender IDs, delivery receipts and scheduled delivery.
- Voice: inbound/outbound calls, virtual numbers, IVR, routing, call status, recordings and call analytics where provider and law permit.
- Digital channels: WhatsApp Business and push or other channels only after provider approval, template and policy validation.
- Platform features: unified API, provider selection, routing, fallback, retries, idempotency, webhook events, suppression and usage reporting.
- Fraud and compliance: OTP abuse, SMS pumping, toll fraud, consent, opt-out, sender registration, destination restrictions and rate controls.
- Disclose that channel availability, sender identity, delivery receipts and fallback behavior differ by provider and country.

#### Category 10 — Payment Infrastructure, Billing & Fintech Integrations
- Payment acceptance: provider/channel/currency catalogue, hosted checkout, payment intent, status verification, refunds and reversals.
- Billing: quote, order, invoice, tax/fee treatment, receipt, credit note, subscription, renewal, proration, dunning, usage billing and account balance ledger.
- Control numbers: allocation, unique reference mapping, validity period, expiry, renewal, cancellation, payment matching, duplicate detection, partial/under/overpayment and unmatched reconciliation where the collection provider supports it.
- Finance operations: settlement imports, gross/fee/net reconciliation, provider reports, bank statement matching, exception queues, adjustment approvals and audit.
- Provider integration: capability matrix, sandbox/live separation, credentials, signed webhook verification, polling fallback, idempotency and outage handling.
- Distinguish payment state, invoice state, order state, subscription state, control-number state and settlement state. Never collapse them into one status.
- Tanzania-specific legal, tax, mobile-money, bank and control-number pathways require current verification with relevant authorities/providers before commercial launch. No claim of licensed payment processing, custody or government collection authority without proof.

#### Category 11 — Developer Tools & API Infrastructure
- API product lifecycle: draft, review, publish, version, deprecate, retire and access policy.
- Developer workspace: organizations, projects, apps, environments, credentials, scopes, quotas, usage and billing.
- API operations: gateway routing, auth, rate limits, request validation, observability, error contracts and version compatibility.
- Webhooks/events: subscriptions, signing, delivery attempts, retries, dead-letter, replay, filtering and test console.
- Developer tooling: API explorer, collections, environment variables, CLI, SDKs, sample apps, changelog, status and migration guides.
- Sandbox: isolated credentials/data, seeded scenarios, simulated responses clearly labelled, reset and deterministic test fixtures.
- AI assistant: retrieval from approved API docs/schema only, citations to source versions, no invented endpoints and safe handling of user secrets.

#### Category 12 — Software Development, DevOps & Deployment
- Source integrations: repository authorization, installation scope, webhook events, branch and environment protection.
- Build system: pipelines, runners, caches, artifacts, test reports, dependency scanning and build provenance.
- Deployment: preview, development, staging, production, rollout strategies, health gates, rollback and release history.
- Infrastructure delivery: IaC plan/apply, state protection, policy checks, drift, approval and secret injection.
- Supply chain: SBOM, signed artifacts, dependency/license scanning, provenance and vulnerability response.
- Operations: runner capacity/isolation, build minutes, deployment audit, failed pipeline diagnostics, cost and quota.
- Clarify whether TEKORA hosts runners/build infrastructure or orchestrates third-party CI/CD providers.

#### Category 13 — Cybersecurity & Information Security
- Assessment services: asset discovery, configuration review, vulnerability scanning, web/API/cloud/container testing and security posture reports.
- Authorized testing: scope approval, rules of engagement, test windows, safe limits, emergency stop, evidence and retest.
- Protection integrations: WAF, DDoS, endpoint, identity, SIEM and cloud security posture where provider-supported.
- Managed security operations: alert triage, incident case, containment recommendation/approval, evidence chain, recovery coordination and post-incident review.
- Governance: risk register, policies, security awareness, vendor risk, audit evidence and remediation tracking.
- Distinguish advisory, assessment, managed detection and response, tool integration and formal certification; never imply one is another.

#### Category 14 — Monitoring, Observability & SRE
- Telemetry products: metrics, logs, traces, profiles, synthetic checks, uptime and real-user monitoring where privacy permits.
- Monitoring lifecycle: agent onboarding, integration health, alert policy, routing, escalation, silence, maintenance and decommission.
- Incident operations: detection, acknowledgement, assignment, timeline, customer communication, status page, resolution and postmortem.
- Reliability: SLIs, SLOs, error budgets, availability windows, capacity forecasting and dependency mapping.
- Cost/data governance: retention tiers, sampling, cardinality controls, ingestion quotas, PII scrubbing and tenant isolation.
- Differentiate observed provider availability from contractual SLA and from TEKORA's own service commitment.

#### Category 15 — AI, ML & Automation Infrastructure
- Model access: provider/model catalogue, capability metadata, regional availability, context limits, modality, pricing and retention terms.
- Inference: API gateway, keys, routing, quota, streaming, retries, fallback compatibility and usage metering.
- Knowledge systems: embedding models, vector indexes, document ingestion, chunking, retrieval permissions, freshness and deletion propagation.
- Model lifecycle: datasets, training/fine-tuning jobs, model registry, evaluation, deployment, monitoring and rollback.
- Agent/workflow platform: tool registry, permissions, approval steps, execution logs, retries, budgets and human handoff.
- Governance: prompt/model versioning, safety evaluation, data leakage, prompt injection, provider retention, provenance and user disclosure.
- Do not imply model output is guaranteed accurate; provide source grounding and confidence/limitations where appropriate.

#### Category 16 — Media, Video & Realtime Infrastructure
- Media management: upload, resumable transfer, metadata, processing queue, transformations, transcoding and asset lifecycle.
- Delivery: VOD/live, HLS/DASH, origin, CDN, signed playback, access policy and QoE analytics.
- Realtime: WebRTC signaling, STUN/TURN/SFU provider, room lifecycle, participants, permissions, presence and chat.
- Recording and intelligence: recording consent, storage, retention, transcription, captions, search and export.
- Operations: bandwidth/egress, transcoding queue, regional performance, concurrency, recording failure and recovery.
- Define which features are TEKORA-operated versus provider-backed; recording defaults and retention must be explicit.

#### Category 17 — Data Engineering & Analytics
- Data movement: connectors, ingestion, batch, stream, CDC, schedules, checkpoints and backfills.
- Transformation: SQL/code transformations, versioning, dependency graph, tests, data contracts and schema evolution.
- Storage/compute: warehouse/lake/lakehouse options, partitioning, retention and cost controls.
- Governance: catalogue, lineage, classification, masking, access, consent/purpose, retention and deletion propagation.
- Quality/operations: freshness, completeness, validity, anomaly, pipeline failures, replay and incident ownership.
- Analytics: governed datasets, dashboards, exports, semantic metrics and role-based reporting.
- Define source-of-truth and freshness for every metric; distinguish observed facts from derived estimates.

#### Category 18 — Business Applications & Digital Productivity
- Application catalogue: TEKORA-built apps, third-party SaaS, managed open-source deployments and partner offers clearly distinguished.
- Business domains: CRM, ERP/finance, HRM, project/work management, collaboration, document management, forms/workflows and e-commerce.
- Tenant lifecycle: trial, provision, configuration, user/seat assignment, integration, update, backup, migration and offboarding.
- Marketplace governance: publisher verification, permissions disclosure, pricing, reviews, update policy, vulnerability response and retirement.
- Cross-app experience: SSO, organization directory, integration catalogue, sync monitoring, shared audit and reporting.
- Define data ownership/export and support responsibility when third-party apps are involved.

#### Category 19 — IT Consulting, Managed IT & Professional Services
- Commercial funnel: lead, discovery, qualification, scope, proposal, quotation, contract, purchase order and kickoff.
- Delivery: project plan, milestones, staffing, timesheets, risks, dependencies, change requests, deliverables and acceptance.
- Managed service: service catalogue, onboarding, asset inventory, support hours, severity, SLA evidence, escalation and monthly review.
- Technical engagement: access authorization, change window, backup, implementation, testing, handover and rollback.
- Finance: milestone/retainer billing, approved expenses, time reconciliation, renewals and contract closure.
- Define IP ownership, confidentiality, subcontracting, warranties, exclusions and customer responsibilities in approved contracts.

#### Category 20 — IoT, Smart Systems & Connected Infrastructure
- Device lifecycle: manufacture/claim/onboard, identity, certificate, provisioning, ownership transfer, maintenance and decommission.
- Connectivity and messaging: MQTT/broker, topic ACL, cellular/Wi-Fi/LPWAN integrations, offline buffering and command acknowledgement.
- Device management: fleet inventory, configuration, telemetry, health, firmware, staged OTA, rollback and remote diagnostics.
- Applications: smart building, industrial monitoring, fleet/asset tracking and automation, each with separate safety and domain analysis.
- Digital twin/rules: state model, telemetry mapping, alerts, automation, simulator and audit.
- Safety: command allowlists, fail-safe states, human override, secure update, physical impact assessment and incident procedure.
- Avoid implying functional safety certification or guaranteed connectivity without evidence.

#### Category 21 — Digital Trust, Compliance & Identity
- Identity: workforce/customer IAM, SSO federation, MFA, lifecycle, access requests, privileged access and service identities.
- Verification: provider-integrated identity/business checks with assurance level, source, jurisdiction and limitations visible.
- Trust infrastructure: PKI, certificate lifecycle, key management integrations, signing and verification.
- Privacy: consent records, preference management, data-subject requests, retention, export and deletion workflows.
- Governance: access reviews, policy mapping, evidence collection, vendor risk, audit trails and control ownership.
- Separate identity proofing, authentication, authorization, electronic signature and legal trust services; they are not interchangeable.

#### Category 22 — Licensing, Software Distribution & Digital Products
- Publisher lifecycle: application onboarding, ownership rights, security review, release approval, support details and retirement.
- Distribution: private/public downloads, package registries, version channels, access tokens, mirrors and release notes.
- Licensing: trial, subscription, perpetual, named user, seat, device, floating/concurrent and offline entitlement only where legally and technically supported.
- Activation lifecycle: issue, activate, deactivate, transfer, renew, grace, revoke, offline validation and recovery.
- Supply chain: SBOM, dependency/license policy, artifact signing, provenance, malware scanning, vulnerability notification and takedown.
- Commercial: pricing, seat changes, renewals, refunds, publisher settlement and entitlement reconciliation.
- Define offline revocation limitations, customer privacy and anti-tamper boundaries clearly.

### 27.4 Cross-category product and platform consistency checks

Before approving any category specification, verify the following platform-wide contracts:
- One customer/org/project/resource ownership model, with explicit personal versus organization ownership and delegated administration.
- One identity and authorization model, with role/permission scopes, resource ownership checks, service identities, session security and audit.
- One product catalogue and offer model, separating technical product capability from commercial SKU, plan, region and provider availability.
- One order and provisioning orchestration model, with idempotency, state transitions, compensation, manual exception handling and reconciliation.
- Separate but linked order, payment, invoice, subscription, entitlement, usage, control-number and settlement records.
- One provider adapter contract that records capabilities, regions, currencies, rate limits, authentication, sandbox/live status, webhook support, outages and contract dependencies without flattening provider-specific behavior.
- One secrets and key-management policy; no credentials in logs, docs, source control, analytics or support tickets.
- One notification/event model with consent, preferences, delivery status, retries, suppression and audit.
- One support/incident model linking customer, service, resource, provider, severity, timeline, communication and resolution evidence.
- One metering contract that records source, unit, interval, aggregation, correction, late data, estimate versus actual, price version and dispute process.
- One audit/event retention policy and export process appropriate to data class and legal requirements.
- Consistent localization for Swahili and English, TZS and other supported currencies, Africa/Dar es Salaam timezone defaults where appropriate, and explicit UTC storage for timestamps.
- No public product page may imply availability, SLA, certification, reseller status or regional support that has not been verified.

### 27.5 Mandatory failure and edge-case analysis

Every product must analyse at least: duplicate requests; delayed/out-of-order events; provider timeout after successful upstream action; provider outage; rate limiting; expired/rotated credentials; partial provisioning; resource already exists; quota/capacity exhaustion; customer cancellation during provisioning; payment success with delayed webhook; payment reversal after entitlement activation; renewal failure; plan downgrade with excess usage; data export/deletion; migration interruption; backup corruption; restore failure; security incident; tenant boundary violation; manual operator correction; and provider contract termination. Add domain-specific cases beyond this baseline.

### 27.6 Product prioritization and release classification

Every candidate product is classified as:
- **Core platform capability:** necessary shared capability for multiple categories.
- **MVP candidate:** essential to validate the platform's first coherent customer journey; must have rationale and measurable outcome.
- **Launch expansion:** valuable but not required for first controlled release.
- **Advanced/enterprise:** requires more complex scale, compliance, integration or operating model.
- **Partner-dependent:** cannot launch until provider authorization, contract, technical access and support path are confirmed.
- **Deferred/unsupported:** intentionally excluded for now with rationale, customer impact and reconsideration trigger.

Prioritization must consider customer value, demand evidence, strategic fit, technical complexity, operational burden, gross margin/cost exposure, provider dependency, legal/regulatory risk, security impact, time-to-validate and cross-category leverage. Do not prioritize only by implementation ease or feature count. Keep the complete long-term catalogue visible while clearly communicating what is actually available.

### 27.7 Evidence and completion standard

Each category must maintain a traceability matrix linking user-originated idea, approved requirement, product/SKU, workflow, UI screen, API/event, data entity, permission, provider dependency, test case, documentation and acceptance evidence. Proposed enhancements must be labelled as proposals; externally dependent facts must cite current authoritative provider/regulator documentation during the relevant phase. A document update alone does not complete research or implementation. Mark each line item DONE only with inspectable evidence; otherwise use PARTIAL, BLOCKED, MISSING, BROKEN or NEEDS VERIFICATION.

### 27.8 Second-pass audit outcome

**Status: PARTIAL — deeper category product discovery required.** All 22 categories have a structured baseline in Section 26 and deeper candidate decomposition in Section 27. However, the final SKU catalogue, country/provider capability matrix, legal validation, detailed state machines, API contracts, data schemas, price books, SLA commitments and measurable per-product acceptance criteria remain discovery deliverables. This is intentional: they must be verified and approved rather than fabricated. No implementation phase is authorized by this section.

---

## 28. All-category product discovery deep dive and global design-system specification

The following companion specifications are mandatory extensions to this Blueprint:

- [Category Deep Dive — All 22 Services](CATEGORY_DEEP_DIVE_22_SERVICES.md): decomposes each service category into product families, customer journeys, lifecycle, technical/commercial contracts, data, security, operational failure modes and acceptance evidence. It preserves partner/legal/provider uncertainty and records remaining discovery deliverables.
- [Global Design System — Color, Typography & UX](DESIGN_SYSTEM_COLOR_TYPOGRAPHY_UX.md): defines the proposed visual direction, global color tokens, 22 restrained service accents, theme behavior, typography candidates and specimen strings, information architecture for all four surfaces, interaction/component rules, accessibility/performance requirements and design approval gates.

### 28.1 Binding design principles

The public marketplace, customer portal, developer hub and internal operations must share one coherent design language and component foundation. Category identity is expressed through restrained accents and content-specific workflows, never through 22 disconnected mini-apps. Color, typography, accessibility, responsive behavior, interaction states, information architecture and performance are requirements from the beginning.

### 28.2 Color and typography status

The companion design specification records a proposed cobalt/teal and neutral palette, semantic status tokens, category accents, and Light/Dark/System themes. These are **PROPOSED**, not contrast-certified. The candidate type system (Manrope, Source Sans 3 and IBM Plex Mono, with Geist alternatives for evaluation) is **PROPOSED**, not selected. Contrast matrices, font specimens, Swahili/Latin Extended glyph tests, licensing, payload measurements and responsive rendering must be completed before design approval.

### 28.3 Accessibility and UX acceptance

Target WCAG 2.2 AA. Verify text/non-text contrast, keyboard operation, visible focus, semantic structure, assistive technology announcements, zoom/reflow, reduced motion, touch targets, accessible charts and mobile/tablet/desktop journeys. Automated scans are supplementary and do not constitute proof of conformance. Each key flow requires usability evidence and explicit empty/loading/error/pending/success/recovery states.

### 28.4 Product discovery status

The all-category deep dive is a stronger candidate-product baseline, not a final catalogue. Demand validation, provider/region/contracts, Tanzania legal/tax validation, SKU/price/cost/margin, state diagrams, API/event contracts, data/retention schemas, service ownership, support/SLA capacity, acceptance tests and runbooks remain open.

**Overall status remains PARTIAL.** No application implementation or production capability is implied. Continue discovery phases and require explicit user approval before implementation.


---

## 29. Provider, country and integration due diligence

Companion register: [Provider, Country & Integration Due Diligence](PROVIDER_COUNTRY_INTEGRATION_DUE_DILIGENCE.md).

This register records public evidence and explicitly separates it from provider approval. TCRA public guidance states .tz registration is performed through accredited registrars; TEKORA must establish accreditation or a lawful partner/reseller path before making .tz registration claims. BoT/OAG materials identify the national payment-system regulatory framework, including updated published legislation/regulations; the precise TEKORA role must be legally classified. PDPA and PDPC materials require a data-protection compliance workstream. Twilio's published Tanzania SMS guidelines indicate sender-ID registration constraints and no two-way SMS support on that route. All provider offers remain candidates pending contract, region, cost, support, security and legal diligence.

## 30. Product catalogue, SKU and pricing framework

Companion register: [Product Catalogue, SKU & Pricing Framework](PRODUCT_CATALOGUE_SKU_PRICING_FRAMEWORK.md).

The catalogue hierarchy, versioned SKU fields, metering schema, billing models and price governance are specified. Candidate MVP packages are hypotheses, not an approved launch catalogue. No public prices or margins are approved. Pricing must account for provider costs, FX, tax, support, infrastructure, refunds, fraud, partner share and operational overhead. A quote must preserve a versioned price snapshot.

## 31. Architecture, API, event and data contracts

Companion register: [Architecture, API, Event & Data Contracts](ARCHITECTURE_API_EVENT_DATA_CONTRACTS.md).

A modular-monolith baseline, bounded contexts, API conventions, event envelope, data governance and candidate state machines are documented. These are design proposals pending formal Architecture phase approval. Order, invoice, payment attempt, control number, subscription, entitlement, usage and settlement remain distinct aggregates. Upstream timeouts create UNKNOWN/reconciliation states, not assumed failures.

## 32. Color, typography and UX validation

Companion register: [Color, Typography & UX Validation](COLOR_TYPOGRAPHY_UX_VALIDATION.md).

A preliminary WCAG contrast calculation found several proposed light-theme text pairings pass; #14B8A6 against white is 2.49:1 and fails both normal and large-text thresholds. Use it only as a non-essential decorative accent on white until a valid pairing is specified. Full theme matrix, focus/border/chart checks, font licensing/specimen/performance and usability evidence remain outstanding. The prototype screen set and design approval checklist are mandatory.

**Section 29–32 status: PARTIAL.** These deliverables improve discovery maturity but do not constitute legal advice, provider approval, final pricing, production API implementation, completed UX research or implementation authorization.


---

## 33. Comprehensive discovery addendum and traceability baseline

The additive [Comprehensive Discovery Addendum](COMPREHENSIVE_DISCOVERY_ADDENDUM.md) extends, and does not replace, any previous Blueprint section or companion document. It must be read together with Sections 1–32 and all linked documents.

### 33.1 Shared platform requirement IDs

The addendum establishes PLT-001–PLT-024 for shared platform requirements, including the four platform surfaces, catalogue/SKU separation, tenant and resource ownership, delivery-model transparency, provider abstraction, independent financial and fulfilment lifecycles, idempotency, UNKNOWN/reconciliation, versioned pricing, metering provenance, Tanzania localization, privacy governance, secrets, staff approvals, notifications, support/incident linking, WCAG 2.2 AA, global design system, publication evidence, recovery states, data lifecycle, health separation, audit and release rollback.

### 33.2 All-category traceability

CAT-01–CAT-22 establish stable parent IDs for every existing category. Child requirements must be assigned using the documented functional, non-functional, operations, security, commercial/legal and acceptance ID conventions. Each child must trace to origin, actor, product/SKU, workflow, UI, API/event, entity, permission, provider/region, data governance, security, observability, tests, acceptance evidence, owner, status and change history.

These IDs add traceability; they do not change the category definitions or reduce the long-term catalogue.

### 33.3 Workflows, state machines and data contracts

The addendum provides independent candidate lifecycles for order, provisioning, payment attempt, control number, invoice, subscription, entitlement, usage, settlement, provider resource and support incident; cross-category workflows WF-01–WF-18; transition invariants; shared API/event conventions; and a logical entity inventory. These are proposed design baselines pending domain review and Phase 04 approval. In particular, a control number being issued is not evidence of payment, entitlement is not a payment record, and upstream timeout must not be treated as definite failure.

### 33.4 Provider evidence and Tanzania gates

Provider evidence maturity is classified E0–E5, from unresearched through public documentation, technical validation, commercial validation, legal validation and operational approval. Candidate providers remain unapproved until evidence is recorded. The Tanzania-specific gates cover .tz registrar/partner eligibility, payment-system legal classification, PDPA/PDPC duties, authorized cybersecurity testing, communications sender identity and consent, tax/e-invoicing advice, and consumer/commercial terms. This is not legal advice or proof of provider authorization.

### 33.5 UX, MVP, test and risk baselines

The addendum adds shared navigation, screen IDs and acceptance expectations for public, customer, developer, operations and global settings/error states; evidence-based MVP scoring and decision records; 35 mandatory test scenario IDs; 26 initial risks; and 14 open decision IDs. These are discovery controls, not proof that prototypes, tests, risk treatments or MVP decisions have been completed.

### 33.6 Preservation and status

All prior requirements, 22 category definitions, proposals, decisions, limitations and unresolved items remain in force. The addendum is additive and versioned. Do not delete a requirement because it is not selected for MVP. Do not mark work DONE without inspectable evidence.

**Status: PARTIAL / PROPOSED.** Parent IDs and discovery baselines are added; child-level traceability, provider E2–E5 evidence, legal classification, approved SKU/MVP decisions, final ERD/OpenAPI/AsyncAPI, prototypes, usability evidence, executable tests and formal phase approvals remain outstanding. Application implementation remains NOT STARTED and NOT AUTHORIZED.


---

## 33. Developer Free Domain & Preview Environment Program

The additive specification in `docs/DEVELOPER_FREE_DOMAIN_PROGRAM.md` records the user-requested free-domain capability for junior developers, students, freelancers and project builders. Preserve this as a first-class cross-category product spanning Domains/DNS (CAT-01), Hosting/Compute (CAT-02), Developer Tools/API (CAT-11), DevOps/Deployment (CAT-12), Cybersecurity (CAT-13), Observability (CAT-14) and Developer Hub/Business Applications as applicable. It defines free managed subdomains, DNS/TLS lifecycle, optional deployment targets, eligibility, abuse/takedown/appeal, tenant isolation, expiry/quarantine, API/events, cost controls, UX and acceptance tests.

**Important distinction:** free hostname/subdomain does not mean free registrable domain, hosting, compute, database, email, bandwidth or SLA. Example suffixes are illustrative only. Do not promise a suffix until TEKORA ownership/control and provider/registry terms are verified. Prefer a dedicated registrable domain for untrusted preview content to isolate it from account/staff origins; security review must approve the final trust boundary. Wildcard DNS must be paired with an active-hostname allowlist and must not route arbitrary unallocated names.

Proposed traceability additions: PLT-025; CAT-01-FN-001; CAT-01-SEC-001; CAT-02-FN-001; CAT-11-FN-001; CAT-12-FN-001; CAT-13-SEC-001; CAT-14-OPS-001; CAT-18-COM-001. These are PROPOSED and require child decomposition, cost/provider/legal validation, MVP scoring and approval. The full specification is mandatory reading before implementing this capability. No implementation or launch is claimed.
