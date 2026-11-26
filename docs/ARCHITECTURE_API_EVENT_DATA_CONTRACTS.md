# TEKORA — Architecture Contracts, API/Event Baseline & Data Governance

**Status: PROPOSED baseline.** No endpoint, schema or event is a final implementation contract until Requirements and Architecture phases approve it.

## 1. Architectural principles
Modular monolith initially; explicit bounded contexts; PostgreSQL system of record; Redis cache/ephemeral coordination only; RabbitMQ asynchronous delivery where justified; REST/OpenAPI for public/internal synchronous contracts; versioned events for asynchronous integration; S3-compatible object storage behind an adapter; provider-specific adapters; outbox/inbox and idempotency; no microservices by default.

## 2. Bounded contexts
Identity & Access; Customer & Organization; Projects & Environments; Catalog & Pricing; Orders; Provisioning; Provider Integrations; Resources & Assets; Billing & Finance; Payments; Control Numbers; Subscriptions & Entitlements; Metering & Usage; Notifications; Support & Incidents; Workflow & Approvals; Developer Hub; Audit & Compliance; Analytics.

Payment, control-number, invoice, order, subscription, entitlement and settlement must not be collapsed into one status field or one aggregate.

## 3. API contract conventions
- Prefix: `/api/v1`; JSON UTF-8; UTC ISO-8601 timestamps; explicit currency code and decimal string for money.
- Authentication: OIDC/OAuth2 where appropriate; short-lived access tokens; server-side authorization on every resource; organization/project/resource ownership checks.
- Idempotency: required for create/order/payment/provisioning commands; key scoped to principal + operation + resource; persist request hash and authoritative outcome; reject same key with different payload.
- Concurrency: ETag/version or optimistic lock for mutable resources.
- Pagination: cursor-based for large inventories; stable sort and documented filters.
- Errors: RFC 9457 Problem Details shape with stable `code`, safe `detail`, `correlationId`, `retryable`; never leak secrets, provider raw credentials or sensitive PII.
- Rate limits: documented by identity, tenant and endpoint; return Retry-After where appropriate.
- Webhooks: signed raw-body verification, timestamp tolerance, unique event ID, replay protection, delivery attempt log, bounded retries, dead-letter/manual replay.
- Versioning: additive changes preferred; breaking change new API version or sunset window and migration guide.
- Secrets: reveal once; hash where possible; encrypted at rest; rotate/revoke; never log.

## 4. Candidate resource paths
`/organizations`, `/projects`, `/environments`, `/catalog/categories`, `/catalog/products`, `/offers`, `/quotes`, `/orders`, `/resources`, `/provisioning-operations`, `/providers`, `/invoices`, `/payment-attempts`, `/control-numbers`, `/subscriptions`, `/entitlements`, `/usage/records`, `/usage/summary`, `/webhook-endpoints`, `/webhook-deliveries`, `/notifications`, `/support/tickets`, `/incidents`, `/audit-events`.

These are resource naming candidates, not an assertion that endpoints exist.

## 5. Core state machines (separate aggregates)
- Order: DRAFT → QUOTED → SUBMITTED → ACCEPTED/REJECTED → FULFILLING → FULFILLED/PARTIALLY_FULFILLED/FAILED → CANCEL_REQUESTED → CANCELLED (with compensation/fee rules).
- Provisioning operation: REQUESTED → VALIDATING → QUEUED → RUNNING → SUCCEEDED/FAILED/UNKNOWN → RECONCILING → COMPENSATING → COMPENSATED/MANUAL_REVIEW.
- Payment attempt: CREATED → INITIATED → PENDING → SUCCEEDED/FAILED/EXPIRED/UNKNOWN → REVERSED/REFUNDED (only on verified evidence).
- Control number: REQUESTED → PROVIDER_PENDING → ACTIVE → PARTIALLY_PAID/PAID/EXPIRED/CANCEL_PENDING/CANCELLED/RENEWED/UNKNOWN; only expose states provider supports; reconcile authoritative status.
- Subscription: PENDING → TRIALING/ACTIVE → PAST_DUE/PAUSED → CANCELLATION_PENDING → CANCELLED/EXPIRED; entitlement is independently derived from policy and payment evidence.
- Entitlement: PENDING → ACTIVE → SUSPENDED/REVOKED/EXPIRED; record reason, source, effective dates and audit.
- Invoice: DRAFT → ISSUED → PARTIALLY_PAID/PAID/OVERDUE/VOID/WRITTEN_OFF; immutable issued totals with credit-note/adjustment path.
- Settlement: EXPECTED → IMPORTED → MATCHED/PARTIALLY_MATCHED/UNMATCHED → DISPUTED/ADJUSTED/CLOSED.

UNKNOWN is a first-class state when upstream outcome cannot be established. Never convert timeout to FAILED without reconciliation.

## 6. Event envelope
Required fields: `event_id`, `event_type`, `schema_version`, `occurred_at`, `published_at`, `producer`, `tenant_id`, `aggregate_type`, `aggregate_id`, `aggregate_version`, `correlation_id`, `causation_id`, `idempotency_key`, `data_classification`, `payload`. Include no secrets; minimize PII; define ordering per aggregate; use outbox, consumer inbox, retry policy, DLQ and controlled replay.

Candidate events: `order.submitted.v1`, `order.accepted.v1`, `provisioning.requested.v1`, `provisioning.succeeded.v1`, `provisioning.failed.v1`, `payment.status_observed.v1`, `control_number.issued.v1`, `control_number.status_observed.v1`, `invoice.issued.v1`, `subscription.state_changed.v1`, `entitlement.state_changed.v1`, `usage.recorded.v1`, `provider.health_changed.v1`, `incident.opened.v1`, `notification.delivery_failed.v1`.

## 7. Data governance baseline
For every data domain record owner, controller/processor role, purpose, lawful basis, classification, data subject, source, region, recipients/subprocessors, retention trigger, legal hold, export, deletion, backup expiry, audit and breach response. Separate tenant business data from platform operational telemetry and provider secrets. Define cross-border transfer review and data-subject request workflow. Do not assume all data must or can be hosted only in Tanzania; determine obligations by applicable law, sector and contract.

## 8. Reliability and operations
Use timeouts, bounded retries with jitter, circuit breakers, bulkheads, rate limits, health checks and reconciliation. Retry only idempotent operations or operations with provider idempotency. Preserve provider request/response references with redaction. Manual review queue for ambiguous financial/provisioning states. Every adapter has runbook, health signals, rate limits, support contact, sandbox tests and kill switch.
