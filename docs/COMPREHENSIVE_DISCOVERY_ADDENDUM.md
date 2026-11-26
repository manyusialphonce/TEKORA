# TEKORA — Comprehensive Discovery Addendum

**Status:** PARTIAL / PROPOSED. This is an additive discovery artifact. It does not replace, shorten, supersede or delete any existing requirement, category, decision, companion document or Blueprint section. All 22 categories remain in long-term scope. Exclusion from a future MVP does not remove a requirement from the platform vision.

## 1. Non-negotiable preservation and governance

1. Preserve the original user-originated scope and wording in the existing documents and change history.
2. Add new requirements with stable IDs; never recycle IDs or silently delete rejected/deferred items.
3. Distinguish USER-ORIGINATED, APPROVED DECISION, ASSISTANT PROPOSAL, EXTERNAL OBLIGATION and NEEDS VALIDATION.
4. Keep the current phase-based governance: one authorized phase at a time; parallelize only independent tasks inside that phase.
5. No application implementation, provider activation, live payment, production deployment, paid resource creation or external publication is authorized by this document.
6. Every completion claim requires evidence. A document being written is not proof of a working feature.
7. Maintain the statuses DONE, PARTIAL, BLOCKED, MISSING, BROKEN, NEEDS VERIFICATION, PROPOSED and PENDING.

## 2. Shared platform requirement register

The following stable parent IDs establish cross-platform traceability. Child requirements must be added under these IDs after detailed discovery.

| ID | Requirement | Required acceptance evidence | Status |
|---|---|---|---|
| PLT-001 | One coherent platform across public marketplace, customer portal, developer hub and internal operations. | Approved IA, route map, role-based E2E journeys. | PARTIAL |
| PLT-002 | Product capability, product version, commercial offer, SKU, provider offer and price book remain separate concepts. | Catalogue schema and quote snapshot tests. | PROPOSED |
| PLT-003 | Customer, organization, workspace, project, environment and resource ownership are explicit. | ERD, authorization matrix, tenant-isolation tests. | PROPOSED |
| PLT-004 | Owned, managed, integrated, resold and partner-delivered services are clearly distinguished. | Delivery model metadata, contract evidence and product-page review. | PARTIAL |
| PLT-005 | Provider-specific capabilities, regions, currencies, quotas, authentication, rate limits, outages and sandbox/live states are retained. | Provider capability records and adapter contract tests. | PARTIAL |
| PLT-006 | Orders, provisioning, payment attempts, control numbers, invoices, subscriptions, entitlements, usage and settlements have independent lifecycles. | State diagrams, schema constraints and reconciliation tests. | PROPOSED |
| PLT-007 | Idempotency, deduplication, replay protection and reconciliation are standard for external operations. | Duplicate, replay and concurrency tests. | PROPOSED |
| PLT-008 | Unknown upstream outcomes are represented as UNKNOWN and reconciled before retry. | Timeout-after-success fault-injection test. | PROPOSED |
| PLT-009 | Prices are versioned; quotes preserve immutable price and terms snapshots. | Quote/invoice reproducibility tests. | PROPOSED |
| PLT-010 | Metering supports late, duplicate, corrected, estimated and actual usage with provenance. | Replay, correction and rating tests. | PROPOSED |
| PLT-011 | Tanzania-first localization supports Swahili/English, TZS, explicit timezone display and UTC storage. | Locale, formatting and content tests. | PARTIAL |
| PLT-012 | Personal data has documented purpose, lawful basis, classification, retention, region, recipients and deletion/export handling. | Data inventory, legal/privacy review and DSAR tests. | NEEDS VERIFICATION |
| PLT-013 | Secrets use approved secret management and never appear in source, logs, analytics or support tools. | Secret scans, masking tests and rotation drill. | PROPOSED |
| PLT-014 | Staff access uses least privilege, separation of duties, approval and audit. | Permission tests and audit evidence. | PROPOSED |
| PLT-015 | Notifications support channel preferences, consent, templates, delivery state, retries and suppression. | Channel delivery and preference tests. | PROPOSED |
| PLT-016 | Support/incident records link customers, services, resources, providers, severity, timeline and resolution. | Incident workflow and customer communication tests. | PROPOSED |
| PLT-017 | WCAG 2.2 AA is the accessibility target across themes and breakpoints. | Automated and manual accessibility evidence. | PARTIAL |
| PLT-018 | One global design system governs all surfaces; category accents are secondary. | Design tokens, shared components and visual regression. | PARTIAL |
| PLT-019 | Public claims about availability, SLA, certification, coverage and provider authorization require current evidence. | Publication approval and evidence register. | PROPOSED |
| PLT-020 | Every customer action exposes pending, success, failure, unknown, retry and recovery states. | UX state inventory and E2E tests. | PROPOSED |
| PLT-021 | Data export, deletion, legal hold and backup expiry are explicitly governed. | Lifecycle tests and approved retention schedule. | PROPOSED |
| PLT-022 | TEKORA platform health is distinguished from upstream provider health and contractual SLA. | Health/status model and runbooks. | PROPOSED |
| PLT-023 | Audit records include actor, tenant, action, target, time, reason, correlation and outcome without secrets. | Audit schema and integrity/access tests. | PROPOSED |
| PLT-024 | Every release has migration compatibility, feature control, rollback/recovery and change evidence. | Release checklist and rollback rehearsal. | PROPOSED |

## 3. All 22 category parent requirements

Each parent must be decomposed into product/SKU-level child requirements, workflows, screens, APIs/events, entities, permissions, provider dependencies, tests and acceptance evidence.

| Category | Stable parent ID | Mandatory discovery and acceptance coverage |
|---|---|---|
| Domains, DNS & Internet Services | CAT-01 | Domain eligibility, registration/transfer/renewal, registrant verification, DNS zones/records, DNSSEC, nameserver changes, expiry/grace/redemption, privacy where supported, propagation, abuse/disputes and accredited registrar/partner route. |
| Web Hosting, Application Hosting & Compute | CAT-02 | Runtime compatibility, plans/quotas, deploy/build/release, environment variables/secrets, scaling, logs, backups, domains/TLS, suspension, migration, deletion and cost. |
| Cloud Infrastructure & Virtualization | CAT-03 | Regions/zones, VM/network/volume/image lifecycle, quotas, keys, firewall, snapshots, resize, availability, IaC, billing and destructive-operation approval. |
| Containers, Kubernetes & Runtime | CAT-04 | Registry, image provenance, clusters/namespaces/workloads, secrets, ingress, autoscaling, policy, upgrades, quota, backup/restore and tenant isolation. |
| Networking & Connectivity | CAT-05 | VPC/subnet/routes/IP/VPN/firewall/load balancer/DNS, topology, connectivity tests, approvals, propagation and rollback. |
| Database Services | CAT-06 | Engine/version/region/HA, lifecycle, network access, credentials, backup/PITR, restore drills, replicas, upgrades, encryption, monitoring and deletion. |
| Storage, Backup & Disaster Recovery | CAT-07 | Object/block/file storage, lifecycle, versioning, immutability, encryption, retention, restore verification, RPO/RTO evidence and egress. |
| Email Infrastructure | CAT-08 | Mailbox/domain/DNS, SMTP/API, authentication records, reputation, deliverability, bounce/complaint suppression, quotas, abuse and retention. |
| SMS, Voice & Omnichannel Communication | CAT-09 | Sender identity, country/network support, consent, templates, delivery receipts, retries, opt-out, message segmentation, per-segment/minute cost and provider constraints. |
| Payment Infrastructure, Billing & Fintech Integrations | CAT-10 | Orders, invoices, payment attempts, control-number issue/expiry/payment/reconciliation, refunds/reversals, subscriptions, settlement, sandbox/live, legal role and provider status. |
| Developer Tools & API Infrastructure | CAT-11 | API keys/OAuth clients, scopes, rate limits, docs, SDKs, webhooks, signing/replay, sandbox, logs, versioning, usage and credential rotation. |
| Software Development, DevOps & Deployment | CAT-12 | Git connections, builds, tests, artifacts, environment promotion, approval, rollback, secrets, SBOM/provenance, runners, quotas and orchestration. |
| Cybersecurity & Information Security | CAT-13 | Authorized scope, rules of engagement, safe assessment, findings/evidence, remediation/retest, incident response and distinction from certification. |
| Monitoring, Observability & SRE | CAT-14 | Metrics/logs/traces/synthetics, alert routing, incidents, SLI/SLO, retention/sampling, PII scrubbing, status page and provider-vs-platform availability. |
| AI, ML & Automation Infrastructure | CAT-15 | Model/provider catalogue, region/terms, inference keys/quotas, routing, streaming, usage, retrieval permissions, model evaluation, agent tool permissions, budgets and prompt-injection/data-leakage controls. |
| Media, Video & Realtime Infrastructure | CAT-16 | Upload/transcode/VOD/live/WebRTC/recording, consent, participant permissions, signed playback, retention, egress, regional performance and recovery. |
| Data Engineering & Analytics | CAT-17 | Ingestion/batch/stream/CDC, transformations, data contracts, lineage, quality, masking, retention, replay/backfill, freshness and metric provenance. |
| Business Applications & Digital Productivity | CAT-18 | App catalogue/publisher verification, provisioning, seats, SSO, integrations, updates, backup, export, offboarding and support responsibility. |
| IT Consulting, Managed IT & Professional Services | CAT-19 | Lead/discovery/quote/contract, scope, milestones, staffing, timesheets, change requests, acceptance, support hours, SLA evidence, IP/confidentiality and closure. |
| IoT, Smart Systems & Connected Infrastructure | CAT-20 | Device identity/claim/onboard, connectivity, telemetry, command authorization, OTA/rollback, offline mode, physical safety, human override and decommission. |
| Digital Trust, Compliance & Identity | CAT-21 | IAM/SSO/MFA, proofing assurance, PKI/certificates, signing, consent, DSAR, retention, audit evidence and distinction between authentication, authorization and legal trust. |
| Licensing, Software Distribution & Digital Products | CAT-22 | Publisher rights, artifact review/signing, version channels, license models, activation/transfer/renewal/revocation/offline limits, SBOM, vulnerability response, refunds and settlement. |

### Child ID convention
Use CAT-XX-FN-NNN for functional requirements, CAT-XX-NF-NNN for non-functional, CAT-XX-OPS-NNN for operations, CAT-XX-SEC-NNN for security, CAT-XX-COM-NNN for commercial/legal and CAT-XX-ACC-NNN for acceptance. IDs are assigned only when the exact statement, actor, trigger, preconditions, main flow, alternate/error paths and evidence are recorded. IDs are never recycled.

### Mandatory traceability fields
Requirement ID; exact statement; origin; rationale; actor; segment; category/product/SKU; priority/release class; preconditions; trigger; normal and alternate flows; state transitions; screen; API/event; entity/fields; authorization; provider/region; data class/purpose/retention; security/abuse controls; localization/accessibility; observability/runbook; test IDs; acceptance criteria; evidence; owner; status; dependencies; decision date and change history.

## 4. Workflow and state-machine catalogue

All workflows use the shared pattern: authenticate → authorize tenant/resource ownership → validate eligibility → enforce idempotency → persist intent → dispatch asynchronously where appropriate → record provider correlation → observe result → reconcile uncertainty → activate resource/entitlement only from verified evidence → notify → audit. External calls must not be held inside long database transactions.

### Independent state machines

- **Order:** DRAFT → VALIDATING → QUOTED → AWAITING_PAYMENT or PAYMENT_NOT_REQUIRED → CONFIRMED → FULFILMENT_PENDING → FULFILLED → CLOSED. Exceptions: REJECTED, CANCELLED, EXPIRED, ON_HOLD, MANUAL_REVIEW.
- **Provisioning:** REQUESTED → QUEUED → DISPATCHING → PROVIDER_ACCEPTED → PROVISIONING → VERIFYING → ACTIVE. Exceptions: RETRY_WAIT, PARTIALLY_PROVISIONED, UNKNOWN, FAILED, COMPENSATING, COMPENSATED, CANCEL_REQUESTED, CANCELLED, MANUAL_REVIEW.
- **Payment attempt:** CREATED → INITIATED → PENDING_PROVIDER → SUCCEEDED / FAILED / EXPIRED / CANCELLED / UNKNOWN. Refunds, reversals and chargebacks are separate linked records, not overwrites.
- **Control number:** REQUESTED → ISSUING → ISSUED → AWAITING_PAYMENT → PAID / EXPIRED / CANCELLED / UNKNOWN. Exceptions: REJECTED, RECONCILIATION_REQUIRED, MANUAL_REVIEW. Issuance never means payment received.
- **Invoice:** DRAFT → ISSUED → OPEN / PARTIALLY_PAID → PAID; alternatives VOID, OVERDUE, UNCOLLECTIBLE, DISPUTED. Credit notes/adjustments are separate immutable records.
- **Subscription:** PENDING_ACTIVATION → TRIALING / ACTIVE → PAST_DUE / GRACE_PERIOD → ACTIVE or SUSPENDED → CANCEL_AT_PERIOD_END / CANCELLATION_PENDING → CANCELLED / EXPIRED. Also PAUSED, PAYMENT_RETRY, MANUAL_REVIEW.
- **Entitlement:** PENDING → ACTIVE → GRACE → SUSPENDED → REVOKED / EXPIRED. Entitlement is an authorization grant, not a payment record.
- **Usage:** RECEIVED → VALIDATED → DEDUPLICATED → NORMALIZED → AGGREGATED → RATED → INVOICED. Corrections are linked correction/reversal records; retain raw provenance and calculation version.
- **Settlement:** EXPECTED → REPORTED → RECONCILING → MATCHED / MISMATCHED → APPROVED → SETTLED. Exceptions DELAYED, DISPUTED, REVERSED, MANUAL_ADJUSTMENT.
- **Provider resource:** REQUESTED → DISCOVERING → PROVISIONING → ACTIVE → UPDATING → DEGRADED / SUSPENDED → DELETING → DELETED. Track UNKNOWN, drift, orphan and manual intervention.
- **Incident:** OPEN → TRIAGED → ACKNOWLEDGED → INVESTIGATING → MITIGATING → MONITORING → RESOLVED → CLOSED; allow audited reopen.

### Transition invariants
1. Record actor/system, time, reason, correlation/causation, previous/next state and source evidence.
2. Validate transitions server-side using explicit transition rules.
3. Never silently rewrite terminal states; create linked operations or audited reopen transitions.
4. Use bounded retries with jitter and rate-limit awareness; reconcile non-idempotent operations before retry.
5. Cancellation is a command; a race with fulfilment may require separate compensation/refund.
6. UNKNOWN is a valid state and must be reconciled.
7. Operator overrides require least privilege, reason, evidence and dual approval when risk warrants.
8. Preserve provider raw status and normalized mapping with adapter version.
9. Customer-facing status must never claim more than the evidence proves.

### Cross-category workflow IDs
WF-01 discover/compare; WF-02 organization/workspace onboarding; WF-03 quote/purchase; WF-04 provisioning; WF-05 resource configuration; WF-06 renewal/cancellation/downgrade; WF-07 usage/billing; WF-08 refund/reversal; WF-09 support/incident; WF-10 data export/deletion; WF-11 provider onboarding/change; WF-12 API credential lifecycle; WF-13 deployment pipeline; WF-14 backup/restore; WF-15 domain lifecycle; WF-16 communication send; WF-17 device onboarding/command; WF-18 consulting engagement. Each workflow requires actor, purpose, preconditions, idempotency, normal/alternate paths, timeout, retries, cancellation, compensation, reconciliation, notifications, audit, retention, runbook and tests.

## 5. Shared data/API contract baseline

- IDs are opaque UUID/ULID; do not rely on sequential IDs for authorization.
- API timestamps are ISO 8601/RFC 3339 with offsets; persist UTC and render the user's timezone explicitly.
- Money uses decimal strings and ISO currency codes, never binary floating point. Preserve tax, rounding and price version.
- Quantities use decimal strings plus unit and precision.
- APIs use /api/v1, JSON UTF-8, cursor pagination, RFC 9457 Problem Details, explicit schemas and documented error codes.
- Mutating commands use Idempotency-Key with defined scope/TTL and stored outcome; use optimistic concurrency where required.
- Events carry event ID/type/schema version, occurred/received timestamps, producer, tenant, aggregate/version, correlation, causation, idempotency, classification and payload.
- Webhooks validate signature over raw body, timestamp tolerance, replay protection and deduplication; support delivery attempts, dead-letter/replay controls and secret rotation.
- Every request and background job enforces tenant and resource ownership.
- Logs/errors expose safe messages and correlation IDs, never secrets or stack traces.

### Logical entity inventory (not a final physical schema)

| Entity | Minimum attributes | Invariants |
|---|---|---|
| UserIdentity | id, issuer, subject, status, created_at | External identity uniqueness; identity provider manages credentials. |
| Organization | id, legal/display name, country, verification state | Tenant isolation. |
| Membership | user_id, org_id, role, status, scope | No implicit global administrator. |
| Workspace/Project/Environment | id, owner scope, parent, name, lifecycle | Parent-child ownership enforced. |
| Product/ProductVersion | id, category, capabilities, version, lifecycle | Technical definition separate from price. |
| Offer/SKU/PriceBook | sku, version, currency, unit, allowances, overage, effective dates | Historical quote reproducible. |
| Provider/ProviderAccount | legal entity, capability, region, credential reference, contract state | No plaintext credentials in business tables. |
| ProviderAdapter | provider, adapter version, operation mapping, timeout/retry policy | Provider-specific semantics retained. |
| Order/OrderLine | buyer, items, quote snapshot, status, idempotency | Immutable commercial snapshot. |
| ProvisioningOperation | order/resource, provider operation, state, attempt, correlation | Reconcile UNKNOWN before retry. |
| Resource | owner, product, provider reference, region, config version, status | Ownership and external reference integrity. |
| PaymentAttempt | invoice/order, provider, amount, currency, provider reference, status | Append attempts; never overwrite history. |
| ControlNumber | issuer, protected value, amount, expiry, status, references | Issue is not payment confirmation. |
| Invoice/CreditNote | number, line snapshots, tax, totals, status | Issued document immutable; adjustments separate. |
| Subscription/Entitlement | period, SKU version, state, grants, policy | Entitlement not synonymous with payment. |
| UsageEvent/Aggregate | source, unit, window, quantity, estimated flag, correction ref | Idempotent and auditable. |
| SettlementRecord | provider report, expected/actual amount, match state | Reconcile with ledger and provider report. |
| Notification/DeliveryAttempt | channel, template version, recipient reference, consent, state | Preferences and suppression enforced. |
| SupportCase/Incident | severity, owner, linked resource/provider, timeline | Separate customer-visible and internal notes. |
| AuditEvent | actor, action, target, reason, time, correlation, outcome | Append-only and secret-free. |
| DataSubjectRequest | requester, identity verification, scope, legal hold, deadline, outcome | Legal hold and backup expiry respected. |

### Candidate API surface (not approved OpenAPI)
POST /api/v1/quotes; POST /api/v1/orders; GET /api/v1/orders/{orderId}; POST /api/v1/orders/{orderId}/cancel; GET /api/v1/resources; POST /api/v1/provisioning-operations; GET /api/v1/provisioning-operations/{id}; POST /api/v1/payment-attempts; POST /api/v1/control-numbers; GET /api/v1/invoices; GET /api/v1/subscriptions; GET /api/v1/usage; POST /api/v1/webhooks/{providerKey}; GET /api/v1/audit-events. Exact operations, scopes, schemas, versioning and pagination require Phase 04 approval.

### Data governance
Every entity must document controller/processor, purpose, lawful basis, subject, classification, source, recipients/subprocessors, region, retention trigger, deletion, backup expiry, legal hold, export, audit and breach response. Restricted data includes credentials, keys, payment secrets, authentication factors and sensitive personal data. Store secret references, not secret values. Define encryption, rotation, access logging, backup protection and incident handling. Obtain qualified local privacy/legal review.

## 6. Provider capability and evidence matrix

Evidence maturity:
- E0: not researched.
- E1: official public docs found; no TEKORA eligibility or contract implied.
- E2: authorized sandbox/API validation with dated artifacts.
- E3: written commercial terms, resale rights, support and SLA reviewed.
- E4: qualified legal/regulatory validation.
- E5: runbooks, recovery, reconciliation, exit and operational approval tested.

| Capability | Candidate/source lead | Known public research baseline | Mandatory verification | Evidence now |
|---|---|---|---|---|
| .tz domains | TCRA accredited registrar directory / Karibu portal | TCRA guidance says .tz registration is through accredited registrars. | Current registrar, partnership, price, API, registrant/renewal/transfer lifecycle and support. | E1 guidance; TEKORA route unknown |
| Global domains/DNS | Cloudflare Registrar/API and other registrars | Public API docs exist for supported extensions. | Exact TLD support including .tz, reseller rights, region, scopes and transfer. | E1; .tz API support not assumed |
| Cloud/compute | AWS, Azure, Google Cloud, DigitalOcean, Hetzner, OVHcloud | Public product/API docs exist. | Region/latency, account eligibility, managed/resale rights, quotas, FX/tax, support, egress and SLA. | E1 candidates |
| CDN/DNS/security | Cloudflare and qualified alternatives | Public developer/API docs exist. | Plan limits, WAF/DDoS scope, region, support, data processing and resale. | E1 candidate |
| SMS/voice/WhatsApp | Twilio, local authorized aggregators/operators | Previously reviewed Twilio Tanzania guidance identified sender-ID registration and route limitations, including no two-way SMS on that route. | Recheck network coverage, sender approval, two-way support, lead time, segment price, consent and contracts. | E1 historical; revalidate |
| Email delivery | Amazon SES, Postmark, SendGrid, Mailgun | Public API/pricing docs exist. | Sender verification, region, deliverability, suppression, DPA, support, limits and abuse handling. | E1 candidates |
| Payments/control numbers | PayIt, SN Pay, banks, licensed PSPs | Public technical docs identified for PayIt and SN Pay. | Current BoT status, legal entity, merchant onboarding, control-number issuer, settlement, refunds, signed webhooks, sandbox parity, fees, DPA and SLA. | E1 docs; E2–E5 absent |
| Live/realtime media | LiveKit and cloud media providers | Public technical docs exist. | Hosting/region, TURN/SFU cost, recording storage, data processing, concurrency, consent and retention. | E1 candidate |
| AI/model APIs | Multiple model providers | Public APIs/pricing vary by provider. | Data retention/training terms, regional processing, safety, quotas, rate limits, SLA, costs and fallback compatibility. | E0/E1 per provider |
| Monitoring | OpenTelemetry-compatible platforms, Prometheus/Grafana ecosystems | Open standards and product docs exist. | Tenant isolation, retention, PII controls, support, ingestion cost and operational burden. | E1 direction |
| Storage/backup | S3-compatible providers | API-compatible options exist. | Object lock semantics, region, durability, restore speed, egress, encryption, retention and exit. | E1 candidates |
| Identity | OIDC-compatible providers | Standards and public docs exist. | Residency, MFA/recovery, federation, audit, availability, export and privacy fit. | E1 candidates |

### Provider onboarding evidence checklist
Verify legal entity and ownership; regulatory status; terms; data processing agreement; subprocessors; regions; security certifications and exact scope; breach notification; support escalation; SLA definitions/exclusions/credits; pricing/FX/tax; quotas/overage; resale/white-label rights; data portability; API versions/rate limits; authentication/rotation; webhook signing/replay; sandbox parity; idempotency; reconciliation/export; incident history; continuity; termination/data return/deletion; transition assistance; exit plan; owner and review date.

### Tanzania-specific gates
- Domains: verify TCRA registrar/accreditation and .tz partner eligibility before claiming registrar capability.
- Payments: obtain qualified local legal classification of the actual TEKORA role under the current National Payment Systems framework. Distinguish software provider, merchant, technical service provider, aggregator, payment facilitator, acquiring, switching, e-money and custody. Verify provider/bank status with BoT.
- Privacy: map controller/processor roles, PDPC obligations, lawful basis, notices, cross-border transfers, subprocessors, rights, retention and breach handling.
- Cybersecurity: written scope and Rules of Engagement for security testing; scanning is not certification.
- Communications: sender-ID registration, network support, opt-in/opt-out, transactional/promotional separation and delivery evidence.
- Tax: qualified TRA advice for VAT, withholding, EFD/e-receipts, imported/cross-border digital services, marketplace/agent treatment and foreign-provider invoices.
- Consumer/commercial: terms, cancellation, refund, renewal, SLA, warranties, exclusions and dispute process require local review.
The existing PROVIDER_COUNTRY_INTEGRATION_DUE_DILIGENCE.md remains the detailed source register. No legal conclusion is made here.

## 7. UX information architecture and screen acceptance

### Global navigation
Public: Home, Services, Solutions/Industries, verified Pricing, Documentation, Status, Trust/Security, Support, Sign in.
Customer: Overview, Organization, Projects, Services/Resources, Orders, Billing, Payments/Control Numbers, Usage, Developer, Integrations, Support, Notifications, Settings.
Developer: Quickstart, API reference, SDKs, API credentials, Webhooks, Sandbox, Logs, Usage/limits, Changelog, Status.
Operations: Work queue, Customers/Organizations, Catalogue/SKUs, Orders, Provisioning, Providers, Billing/Payments, Control-number reconciliation, Usage/Metering, Support/Incidents, Security, Approvals, Audit, Reports, Configuration.
Hiding a navigation item is not authorization; every server operation enforces permissions.

| Screen ID | Screen | Required content and states | Acceptance |
|---|---|---|---|
| UX-PUB-01 | Public home | Value proposition, category discovery, trust, supported geography and honest CTA. | Content, responsive and accessibility review. |
| UX-PUB-02 | Service catalogue | Search, filters, category/product/delivery model, availability and provider dependency. | Search and empty/error tests. |
| UX-PUB-03 | Product detail | Capabilities, exclusions, prerequisites, region, limits, billing unit, responsibility and SLA evidence. | Trace to approved SKU. |
| UX-PUB-04 | Quote/checkout | Versioned price, tax/fees, currency, expiry, terms, payment and recovery. | Price snapshot/payment E2E. |
| UX-CUS-01 | Customer overview | Resources, service health, usage/cost, alerts and support; separate provider/platform status. | Role-scoped data tests. |
| UX-CUS-02 | Organization/projects | Ownership, members, invitations, scopes, policies and audit. | Tenant and permission tests. |
| UX-CUS-03 | Orders/provisioning | Timeline, pending/UNKNOWN, retry/reconciliation, cancellation and support. | Timeout/partial-failure tests. |
| UX-CUS-04 | Resource detail | Config, provider/region, events, actions, usage, backup and lifecycle. | Ownership/destructive-action tests. |
| UX-CUS-05 | Billing/invoices | Invoice states, line snapshots, tax, attempts, refunds/credit notes and downloads. | Finance reconciliation. |
| UX-CUS-06 | Control numbers | Issuance, amount, payer, expiry, payment state, reconciliation and support. | Sandbox/webhook tests. |
| UX-CUS-07 | Usage/cost | Units, periods, estimates/actuals, price version, forecast and dispute. | Metering/rating tests. |
| UX-DEV-01 | Developer quickstart | First sandbox request, environment separation, examples and safe errors. | First-time user test. |
| UX-DEV-02 | API credentials | Scope, create-once secret, rotation/revoke, last-used and audit. | Secret exposure test. |
| UX-DEV-03 | API/webhooks | Versioned schemas, signatures, retries, replay and delivery logs. | Contract/replay tests. |
| UX-OPS-01 | Operations queue | Priority, owner, filters, contract-backed SLA clock and safe bulk actions. | Role/audit tests. |
| UX-OPS-02 | Provisioning console | Provider request/result, correlation, UNKNOWN reconciliation and retry guard. | Operator simulation. |
| UX-OPS-03 | Provider registry | Capabilities, regions, terms, credential status, incidents and evidence level. | Evidence freshness audit. |
| UX-OPS-04 | Finance/reconciliation | Invoices, attempts, control numbers, refunds, settlements, mismatches and approvals. | Ledger/provider reconciliation. |
| UX-OPS-05 | Incident/status communication | Severity, affected services, approved templates, channels and delivery history. | Notification delivery tests. |
| UX-OPS-06 | Audit/approvals | Actor, reason, before/after, dual approval, export and retention. | Permission/integrity tests. |
| UX-SYS-01 | Global settings | Language, timezone, theme, notifications, MFA/session and accessibility. | Preference and accessibility tests. |
| UX-SYS-02 | Error/recovery | Offline, degraded, rate-limited, forbidden, timeout, unknown, retry and support. | Complete state coverage. |

### Global UX requirements
Premium, minimal, calm visual hierarchy; avoid generic dark admin templates and excessive gradients. One global token/component system; category accents are secondary. Typography candidates remain unapproved until licensing, Swahili/English glyph coverage, readability, responsive rendering and performance pass. Support Light/Dark/System, keyboard, visible focus, semantic landmarks, reduced motion, zoom/reflow and touch targets. Every action has pending/disabled/success/error/unknown states. Destructive actions show impact and recovery. Tables have responsive alternatives and accessible states. Charts never rely on color alone. Forms preserve safe input after recoverable errors. No fake metrics, customer logos, testimonials, provider badges or SLA claims in prototypes. Usability research must include representative prospective users; no sessions/results are claimed yet.

## 8. MVP prioritization

Score candidate products 1–5 with evidence and written rationale: customer value/pain 20%; demand evidence 15%; cross-category strategic leverage 15%; technical feasibility 10%; operational readiness 10%; provider/legal readiness 10%; unit economics/cost exposure 10%; security/privacy/regulatory risk 10% reverse-scored so lower risk scores higher. Unknown evidence remains unknown, not a fabricated neutral score.

Release classes remain: core platform capability, MVP candidate, launch expansion, advanced/enterprise, partner-dependent and deferred/unsupported. Do not remove long-term scope when deferring an item.

Candidate first coherent journey (hypothesis only): account/organization/project onboarding; a small verified service catalogue; quote/order; sandbox or legally approved payment route; controlled provisioning; resource overview; usage/billing visibility; support/notifications; internal operations and reconciliation. The actual products require customer research, provider/legal readiness, cost/margin model, support capacity and user approval.

MVP decision record: decision ID/date/participants; product/SKU; target segment; problem evidence/interview references; provider evidence class; legal gate; technical dependency; cost/margin; security/privacy review; support owner/runbook; scored rationale; excluded features; acceptance tests; geography; sandbox/live status; rollback/exit; approve/defer/reject; approver and review trigger.

## 9. Testing and release strategy

Test levels: unit domain rules/authorization/transitions/pricing; component modules; contract OpenAPI/AsyncAPI/provider adapters; integration PostgreSQL/Redis/RabbitMQ/object storage/identity; E2E customer and operations journeys; security SAST/dependency/license/secret/DAST in authorized scope/tenant isolation/IDOR/CSRF/CORS/SSRF/injection/rate limit; performance concurrency/queue lag/provider latency/database saturation/cost; accessibility WCAG 2.2 AA manual and automated; resilience outage/delayed or reordered webhook/timeout-after-success/queue redelivery/partial failure/restore; operational alerts/runbooks/incident/reconciliation drills.

Mandatory scenario IDs:
TST-001 duplicate command same idempotency key; TST-002 same key with different payload; TST-003 concurrent purchase; TST-004 upstream success with response timeout; TST-005 delayed webhook; TST-006 duplicate webhook; TST-007 out-of-order webhook; TST-008 invalid signature/replay; TST-009 provider rate limit; TST-010 expired credentials; TST-011 partial provisioning; TST-012 cancellation/fulfilment race; TST-013 payment reversal after entitlement activation; TST-014 expired control number; TST-015 settlement mismatch; TST-016 late/corrected usage; TST-017 downgrade with excess usage; TST-018 tax/rounding; TST-019 cross-tenant access; TST-020 privilege escalation; TST-021 secret in logs; TST-022 export with legal hold; TST-023 deletion to processors; TST-024 corrupted backup restore; TST-025 migration rollback constraints; TST-026 provider termination; TST-027 failed incident communication; TST-028 mobile network interruption; TST-029 keyboard-only checkout; TST-030 dark-theme contrast; TST-031 API rate exhaustion; TST-032 poison queue/dead-letter replay; TST-033 dual-approved operator correction; TST-034 orphan/drifted resource; TST-035 disaster recovery exercise.

Phase exit gates: Requirements phase needs approved IDs, origin, priority, acceptance and traceability. UX phase needs IA, responsive prototypes, typography/color evidence, WCAG review, usability findings and design decisions. Architecture phase needs module/context map, sequence/state diagrams, ERD, OpenAPI/AsyncAPI, threat model, provider adapters, deployment/recovery, observability, cost/capacity model. Documentation alone never authorizes implementation.

## 10. Risk register

| Risk ID | Risk | Initial likelihood/impact | Mitigation / trigger | State |
|---|---|---|---|---|
| RSK-001 | Scope too broad for first release | High/High | Evidence-backed MVP subset; trigger unclear acceptance/schedule growth. | OPEN |
| RSK-002 | Public API mistaken for resale/contract approval | High/High | Provider evidence gates and written terms before publication. | OPEN |
| RSK-003 | Payment role requires license/authorization | Medium/Critical | Local legal classification and BoT/provider verification before live funds. | BLOCKING |
| RSK-004 | Control-number route lacks required lifecycle | Medium/High | Sandbox issue/expiry/payment/reversal/reconciliation tests and contract. | OPEN |
| RSK-005 | .tz registrar access unavailable | Medium/High | Verify accredited registrar/partner route before offering. | OPEN |
| RSK-006 | Tax/e-invoicing treatment incorrect | Medium/High | Qualified TRA advice before quote/invoice launch. | OPEN |
| RSK-007 | Privacy/cross-border processing non-compliant | Medium/Critical | Data inventory, PDPC/legal review, DPA and transfer controls. | OPEN |
| RSK-008 | Provider outage/region unavailable | High/High | Degraded mode, health separation, tested exit and recovery. | OPEN |
| RSK-009 | Duplicate provisioning after timeout | Medium/Critical | Idempotency, UNKNOWN and reconciliation before retry. | OPEN |
| RSK-010 | Webhook spoofing/replay | Medium/Critical | Raw-body signature, timestamp, replay window, dedupe. | OPEN |
| RSK-011 | Tenant isolation/authorization failure | Medium/Critical | Central policy and adversarial tests. | OPEN |
| RSK-012 | Secret leakage | Medium/Critical | Secret manager, masking, scanning, rotation and access review. | OPEN |
| RSK-013 | Negative margin/mispricing | High/High | Provider/FX/tax/fee cost model, versioned price book and margin floor. | OPEN |
| RSK-014 | Usage disputes | Medium/High | Raw provenance, corrections, estimates and reproducible rating. | OPEN |
| RSK-015 | Backup/restore unproven | Medium/Critical | Immutable backups and measured restore drills. | OPEN |
| RSK-016 | Security testing exceeds authorization | Low/Critical | Written scope, safe limits, emergency stop and evidence review. | OPEN |
| RSK-017 | UX complexity across 22 categories | High/Medium | Shared IA, progressive disclosure and usability tests. | OPEN |
| RSK-018 | Font/color fails language/accessibility/performance | Medium/Medium | Licensing, glyph, contrast and device tests. | OPEN |
| RSK-019 | Support burden exceeds capacity | High/High | Limited catalogue, support hours, runbooks and escalation. | OPEN |
| RSK-020 | Vendor lock-in / difficult exit | Medium/High | Export, adapters, contract exit and migration/restore rehearsal. | OPEN |
| RSK-021 | Public claims exceed capability | Medium/High | Publication approval and evidence freshness checks. | OPEN |
| RSK-022 | Decisions/requirements lost over time | Medium/High | Stable IDs, additive change history and phase reports. | OPEN |
| RSK-023 | Breaking API/event schema change | Medium/High | Compatibility tests, versioning and deprecation windows. | OPEN |
| RSK-024 | Disaster recovery plan untested | Medium/Critical | Tabletop and technical recovery exercises. | OPEN |
| RSK-025 | Provider termination/credential revocation | Medium/High | Notice terms, portability, transition runbook and kill switch. | OPEN |
| RSK-026 | Manual finance/operator override abuse/error | Medium/High | Least privilege, dual control, reason and immutable audit. | OPEN |

Likelihood and impact are preliminary qualitative estimates, not measured probabilities. Assign owners and review quantitative scoring during risk workshops.

## 11. Open decision register

DEC-001 target customer segment; DEC-002 first MVP products/SKUs; DEC-003 primary/backup providers; DEC-004 payment/control-number legal and technical route; DEC-005 .tz registrar route; DEC-006 font family/weights; DEC-007 final light/dark color tokens; DEC-008 tax/invoice model; DEC-009 initial geography/data residency; DEC-010 support hours/severity/SLA; DEC-011 deployment topology/DR targets; DEC-012 retention/deletion schedules; DEC-013 identity verification levels; DEC-014 brand/domain/trademark availability. All remain PENDING until evidence and explicit decision are recorded.

## 12. Evidence record template

Record ID; claim/decision; source URL or artifact; source owner; publication/retrieval date; exact excerpt or tested behavior; jurisdiction/region; version; evidence class; confidence; assumptions; contradictory evidence; reviewer; expiry/revalidation date; decision; linked requirement IDs and change history. Sanitize provider samples; never commit credentials or personal data.

## 13. Current completion and next gate

- Shared requirements: PARTIAL — parent IDs created; child-level mappings remain.
- Category requirements: PARTIAL — all 22 parent IDs established; detailed child requirements remain.
- Workflows/state machines: PROPOSED — domain review and provider mappings required.
- Data/API contracts: PROPOSED — formal ERD, OpenAPI/AsyncAPI and threat model remain.
- Provider evidence: PARTIAL — candidates and verification gates recorded; no provider approvals.
- UX screen inventory: PROPOSED — prototypes, research and usability sessions remain.
- MVP prioritization: PENDING — no SKU/product set approved.
- Test strategy: PROPOSED — executable tests do not yet exist.
- Risk register: OPEN — owners and treatment approvals pending.
- Application implementation: NOT STARTED / NOT AUTHORIZED.

This document is additive. Keep all previous requirements and all 22 categories intact even when a product is deferred from MVP. New findings update the linked ID and decision history; they do not delete earlier records.
