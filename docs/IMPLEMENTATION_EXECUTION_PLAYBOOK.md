# TEKORA Implementation Execution Playbook

**Purpose:** Convert the platform blueprint and supporting discovery documents into controlled, testable implementation work for OpenCode.  
**Status:** PREPARATION BASELINE — phases are planned; application implementation has not started.  
**Owner:** TEKORA project owner.  
**Implementation agent:** OpenCode, operating under `AGENTS.md`.

## 1. Non-negotiable execution model

Follow:

**UNDERSTAND → AUDIT → PLAN → IMPLEMENT → TEST → VERIFY → HARDEN → DOCUMENT**

One phase is active at a time. Independent work may run in parallel only within the currently approved phase, with explicit ownership, dependency boundaries and shared contracts. A later phase cannot start because the previous phase is "mostly done".

Each phase:
1. Reads relevant specifications and stable requirement IDs.
2. Audits current code/docs and identifies baseline.
3. Produces a scoped plan, dependency map and risk assessment.
4. Receives required approval.
5. Implements only the approved scope.
6. Runs focused and regression tests.
7. Performs independent verification and security review.
8. Updates documentation and traceability.
9. Writes a report under `docs/reports/`.
10. Presents evidence, blockers and next-phase gate for owner approval.

## 2. Phase roadmap

| Phase | Name | Key outputs | Exit gate |
|---|---|---|---|
| 00 | Discovery & Project Definition | Repository audit, glossary, stakeholder/segment evidence, decision log, scope and risk baseline | Owner accepts project baseline |
| 01 | Master Service Catalog & Gap Analysis | All 22 categories mapped to products, capability gaps, dependencies and evidence | Every category has traceable scope and gaps |
| 02 | Requirements Engineering | Functional/non-functional requirements, IDs, workflows, state machines, acceptance criteria | Requirements baseline approved |
| 03 | UI/UX Research & Design | IA, journeys, prototypes, design tokens, typography/color validation, accessibility/usability evidence | Design baseline approved |
| 04 | Technical Architecture & Engineering Design | ADRs, context/module map, ERD, API/event contracts, threat model, deployment/recovery/cost plan | Architecture and stack approved |
| 05 | Platform Foundation | Repository app structure, local environment, CI, identity/tenant foundation, DB migrations, observability baseline | Foundation builds/tests and owner accepts |
| 06 | Core Service Development | Approved MVP product workflows and shared catalog/order/provisioning/billing foundations | Each selected capability passes its own gate |
| 07 | Unified Developer Hub | API docs, credentials, webhooks, sandbox, SDK strategy, logs/usage | Developer journey and security acceptance |
| 08 | Internal Operations Platform | Work queues, approvals, support, finance/reconciliation, provider registry, audit | Operator controls and audit tests pass |
| 09 | System Integration & E2E Validation | Cross-module contracts, end-to-end journeys, failure recovery, reconciliation | Critical journeys pass in isolated staging |
| 10 | Security, Performance & Reliability Hardening | Threat remediation, load tests, DR, observability, restore and incident exercises | Risk owners accept residual risk |
| 11 | Production Readiness / Controlled Launch | Legal/provider approvals, support readiness, runbooks, monitoring, release and rollback | Explicit production launch authorization |
| 12 | Continuous Improvement & Expansion | Metrics, feedback, backlog, new categories/providers, lifecycle and cost optimization | Ongoing governance and periodic reviews |

## 3. Phase 00 — first OpenCode assignment

The initial task is an audit, not coding.

### Scope
- Confirm remote and local branch heads.
- Inspect working tree, repository tree, full commit history relevant to current docs and issue #1.
- Inventory every file, workflow, manifest, source tree, generated file, migration and test.
- Read all root instructions and linked documentation.
- Compare actual repository state with documentation claims.
- Identify contradictions, duplicate requirements, missing IDs, incomplete acceptance criteria and unverified assumptions.
- Confirm that no credentials or sensitive data are present in tracked files.
- Produce `docs/reports/PHASE_00_REPOSITORY_AUDIT.md`.

### Prohibited during this task
- No application code creation.
- No dependency installation or lockfile generation.
- No database/cloud/domain/DNS/payment-provider changes.
- No production calls or customer messaging.
- No deletion or rewrite of existing documentation.
- No automatic approval of technical or product decisions.

### Report structure
1. Executive summary.
2. Commit/branch/tree snapshot and timestamp.
3. Inventory by file and directory.
4. Existing source/build/test/CI status.
5. Documentation coverage and contradictions.
6. Security/privacy findings.
7. Technical decisions still pending.
8. Risks and blockers.
9. Recommended next phase plan.
10. Exact evidence and commands executed.
11. Status table using DONE, PARTIAL, BLOCKED, MISSING, BROKEN, NEEDS VERIFICATION.
12. Owner approvals required.

## 4. Requirements decomposition

Every requirement must have:
- Stable unique ID.
- Parent requirement/category.
- Origin/source and date.
- Actor/persona and permission.
- Trigger/preconditions.
- Main flow.
- Alternative/error/recovery flows.
- Business rules and invariants.
- Data inputs/outputs/classification.
- API/event/UI touchpoints.
- Dependencies/provider and evidence level.
- Security/privacy/abuse implications.
- Observability/audit expectations.
- Acceptance criteria that can be tested.
- Priority and release class.
- Status and owner.
- Related test IDs and documentation references.

Do not use vague requirements such as "secure", "fast", "user-friendly" or "fully automated" without measurable criteria.

## 5. Implementation work package template

Every bounded work package must record:

- Work package ID and title.
- Phase and owner.
- Requirement IDs included.
- Explicit exclusions.
- Existing behavior to preserve.
- Architecture/module boundaries.
- API/event/data changes.
- Permission and tenant-scope impact.
- Migration and rollback/forward-fix plan.
- UI/UX states.
- Provider/sandbox dependency.
- Threat/risk assessment.
- Unit/integration/contract/E2E/security/accessibility tests.
- Observability, runbook and alert changes.
- Documentation files to update.
- Acceptance criteria.
- Reviewer and approval status.

A work package cannot be marked ready when its critical inputs are unknown.

## 6. Parallel execution rules

Parallel tasks are allowed only when:
- They are in the same approved phase.
- Their files/modules do not overlap, or ownership is explicitly partitioned.
- Shared API/event/data contracts have already been agreed.
- Each task has stable requirement IDs and acceptance criteria.
- Integration ownership and merge order are clear.
- The tasks do not compete for the same migration, dependency version or global configuration.

Examples of potentially independent work after architecture approval:
- Research/validate typography and color tokens.
- Draft category-specific acceptance tests.
- Build an isolated provider adapter contract test harness.
- Create UX prototypes against stable API mocks.
- Develop independent documentation/runbooks.

Never parallelize conflicting schema migrations, global auth changes, root build configuration changes or edits to the same source files without coordination.

## 7. Mandatory implementation standards

### Code
- Follow language/framework conventions and compiler strictness.
- Keep domain logic testable and independent.
- Avoid giant services/controllers/components.
- Validate inputs and enforce invariants at boundaries.
- Prefer explicit types and exhaustive state handling.
- No hidden network calls or unbounded retries.
- Avoid arbitrary dependencies; record why each dependency is needed.
- Pin supported versions and commit lockfiles.
- Keep generated code clearly marked and reproducible.

### Data
- Model ownership and tenant scope explicitly.
- Define retention, export, deletion, legal hold and backup treatment.
- Never store secrets in ordinary application tables without a dedicated secret-management design.
- Use migrations; do not manually mutate shared environments.
- Keep financial calculations exact and auditable.
- Record source/provenance for metered usage and external events.

### UI
- Follow the shared design system.
- Design every loading, empty, pending, partial, unknown, error and recovery state.
- Support mobile, tablet, desktop, keyboard and screen-reader use.
- Do not use color as the only status signal.
- No fake production metrics or placeholder claims presented as real.
- Preserve entered form data after recoverable errors where safe.

### Integrations
- Use provider adapter interfaces and capability discovery.
- Separate sandbox and live credentials/endpoints.
- Use idempotency, signature validation, deduplication, timeouts, bounded retries and reconciliation.
- Treat ambiguous upstream outcomes as UNKNOWN.
- Never retry a non-idempotent side effect blindly.
- Keep provider outage and platform outage distinct in status/UX.

## 8. Test and verification matrix

| Layer | What must be proven | Evidence |
|---|---|---|
| Unit | Domain invariants, calculations, permissions and transitions | Test report |
| Component | Module behavior and boundary contracts | Test report |
| Integration | Real database/cache/broker behavior in isolated environment | Testcontainers/compose report |
| Contract | API/event/provider compatibility | OpenAPI/AsyncAPI and contract test results |
| E2E | Critical customer and operator journeys | Browser/API test results |
| Security | Tenant isolation, authz, injection, secrets, webhook replay, abuse limits | Findings and remediation evidence |
| Accessibility | WCAG 2.2 AA target and manual assistive review | Audit findings |
| Responsive | Mobile/tablet/desktop and zoom/reflow | Viewport evidence |
| Performance | Measured latency/throughput/resource use at defined load | Reproducible benchmark |
| Resilience | Provider timeout, delayed events, queue redelivery, partial failure, restore | Exercise report |
| Operations | Alerts, dashboards, runbooks, escalation and rollback | Drill evidence |

A skipped test is not a pass. A flaky test must be recorded and fixed or explicitly quarantined with an owner and expiry date.

## 9. Definition of Done

A work package is DONE only when:
- Its requirement IDs are satisfied.
- Implementation is in the approved scope.
- Tests are added and relevant suites pass.
- Security/authorization and tenant-boundary effects are verified.
- UI states/accessibility/responsiveness are reviewed where relevant.
- Migrations and recovery are understood.
- Logs/metrics/traces/alerts/runbooks are adequate.
- README and module docs reflect actual behavior.
- Blueprint and requirement status are updated.
- The report records commands, outcomes, failures, limitations and evidence.
- Diff is reviewed and no unrelated changes are included.

## 10. Phase gate and owner approval

OpenCode must stop and request owner approval before:
- Moving to the next phase.
- Selecting a production provider or paid plan.
- Spending money or creating paid infrastructure.
- Registering or transferring a domain.
- Changing production DNS, certificates, routes or firewall.
- Enabling live payments, payouts, SMS, email or other external side effects.
- Handling real customer data in a new system.
- Launching publicly or changing production traffic.
- Performing destructive data or repository operations.

The owner may delegate a specific bounded decision in writing. That delegation does not imply approval of unrelated actions.

## 11. Reports and traceability

Every phase report lives in `docs/reports/` and uses a date-prefixed name, e.g. `2026-11-26-PHASE-00-REPOSITORY-AUDIT.md`.

README describes the actual repository state. Blueprint describes intended/approved platform scope. Phase reports describe work performed and evidence. Do not mix these responsibilities.

Maintain a requirement traceability index and a decision log. When a requirement changes, add a dated change record with reason, affected IDs and approval; do not erase historical rationale.

## 12. Initial state

- Documentation/discovery: PARTIAL.
- 22 category decomposition: PARTIAL; further child-level traceability remains.
- Technical stack: PROPOSED; owner approval required.
- Application source code: NOT PRESENT in the inspected repository tree.
- Automated tests/CI: NOT PRESENT in the inspected repository tree.
- Provider contracts/legal approvals: NOT COMPLETE.
- Developer Free Domain Program: SPECIFIED; provider/domain/production route not approved.
- Implementation: NOT STARTED.

This playbook is an execution framework. It is not evidence that any application feature has been built or that production readiness has been achieved.


## 13. Mandatory pricing workstream

Pricing is a cross-cutting capability and must be designed before catalog/checkout/billing implementation. Read `docs/PRODUCT_CATALOGUE_SKU_PRICING_FRAMEWORK.md` in full.

Required work:
- Benchmark comparable competitor prices and record dated URLs, region, currency, tax, product specifications, allowances, renewal and support.
- Obtain actual provider/wholesale cost evidence and calculate fully loaded cost and category margin floor.
- Support all 22 category charging units; distinguish one-time, recurring, usage, prepaid, hybrid and quote-based billing.
- Implement Free/Freemium/Trial/Credits/Sandbox/Paid/Pay-as-you-go/Quote policy with hard quotas, spend caps, end-of-limit behavior and explicit paid conversion.
- Implement price-book versioning, immutable quote/order/invoice snapshots, FX snapshots, tax references, promotions, approvals and change notices.
- Test overage, duplicate/late usage, trial expiry, upgrade/downgrade, cancellation, proration, renewal, refund, payment retries and reconciliation.
- Do not publish unapproved prices or claim the 3–8% undercut as a universal rule.
- Gate every saleable SKU on provider evidence, cost/margin, tax/legal review where relevant, customer disclosure, tests and named approval.

A pricing work package cannot close while any customer-facing price is unsupported by a dated source/cost model or while the free tier can create uncontrolled provider cost or surprise charges.

## Required pricing implementation inputs

Before a phase that touches catalogue, product offers, SKU, pricing, checkout, billing, metering, subscriptions or provider fulfilment, include the Master SKU Pricing Catalogue and all three SKU Pricing Waves in the phase reading set. Convert each relevant SKU into traceable requirements and acceptance tests. Do not implement customer-visible prices from research hypotheses. Implement versioned price books, approval/audit, immutable quote snapshots, idempotent usage, budget/limit controls and explicit customer consent before paid conversion. Keep blocked categories unavailable until their legal/provider/operational gates pass.
