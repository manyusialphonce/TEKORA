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
