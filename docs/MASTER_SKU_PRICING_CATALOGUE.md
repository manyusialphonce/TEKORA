# TEKORA — Master SKU Pricing Catalogue & OpenCode Implementation Index

**Version:** 1.0 · **Research snapshot:** 26 November 2026 · **Status:** discovery baseline, not an approved commercial price book.

## 1. Purpose and authority

This is the single implementation-facing index for SKU design across all 22 service categories. It consolidates the earlier catalogue framework, competitor matrix and SKU research waves. It is not permission to sell, activate providers, charge customers, process live payments or publish unapproved prices.

Authority order:
1. Product intent and requirements: `docs/MASTER_PLATFORM_BLUEPRINT.md`.
2. Execution rules: `AGENTS.md` and `MASTER_IMPLEMENTATION_PROMPT.md`.
3. Catalogue and commercial data model: this document plus `PRODUCT_CATALOGUE_SKU_PRICING_FRAMEWORK.md`.
4. Evidence: competitor matrix and Wave 01–03 documents.
5. Current actual implementation state: README and phase reports.

## 2. Mandatory reading order for OpenCode

Before touching catalogue/pricing code, read:
- `README.md`
- `AGENTS.md`
- `MASTER_IMPLEMENTATION_PROMPT.md`
- `docs/MASTER_PLATFORM_BLUEPRINT.md` (entire document)
- `docs/PRODUCT_CATALOGUE_SKU_PRICING_FRAMEWORK.md`
- `docs/COMPETITOR_PRICING_BENCHMARK_MATRIX.md`
- `docs/SKU_LEVEL_COMPETITIVE_PRICING_WAVE_01.md`
- `docs/SKU_LEVEL_COMPETITIVE_PRICING_WAVE_02.md`
- `docs/SKU_LEVEL_COMPETITIVE_PRICING_WAVE_03.md`
- `docs/TECHNICAL_DECISION_REGISTER.md`
- `docs/IMPLEMENTATION_EXECUTION_PLAYBOOK.md`
- Relevant provider/regulatory and design-system documents.

If a referenced file is absent, report MISSING and do not fabricate its contents. Resolve inconsistency through a proposed decision record; never silently override.

## 3. Canonical catalogue hierarchy

Category → product family → product → SKU/offer → immutable price-book version → region → currency → provider offer/route → eligibility/entitlement → subscription/order/quote snapshot.

Product promise must be independent of provider fulfilment. A product can have multiple providers, but provider capability, region, authorization, capacity, contract and failover eligibility must be explicit.

## 4. SKU registry — all 22 categories

| # | Category | SKU families and canonical charging units |
|---|---|---|
| 01 | Domains, DNS & Internet Services | DOMAIN-REG/RENEW (domain-year); DNS-ZONE (zone-month); DNS-QUERY (million queries); DNS-RECORD/SECURITY (zone-month); DEVELOPER-SUBDOMAIN (hostname/term) |
| 02 | Web Hosting, Application Hosting & Compute | HOST-SHARED (account-month); HOST-WP (site-month); APP-RUNTIME (instance-hour/month); BUILD (minute); COMPUTE (vCPU-hour/GB-hour); EGRESS (GB) |
| 03 | Cloud Infrastructure & Virtualization | CLOUD-VM (instance-month by vCPU/RAM/disk); CLOUD-IP (IP-month); CLOUD-EGRESS (GB); SNAPSHOT (GB-month); MANAGED-CLOUD (instance-month) |
| 04 | Containers, Kubernetes & Runtime | K8S-CLUSTER (cluster-month); WORKER (node-hour); CPU/MEMORY (resource-hour); REGISTRY (GB-month+ops); BUILD (runner-minute); MANAGED-K8S (cluster-month) |
| 05 | Networking & Connectivity | INTERNET (site-month/bandwidth); DEDICATED-LINK (committed Mbps-month); VPN (tunnel/site-month); SD-WAN (site-month); FIREWALL/WIFI (device/site-month); ONSITE (visit/day) |
| 06 | Database Services | DB-INSTANCE (instance-hour/month); STORAGE (GB-month); BACKUP/PITR (GB-month/retention); HA (replica-month); QUERY/IOPS where provider-metered; DBA (support-month) |
| 07 | Storage, Backup & DR | OBJECT/BLOCK/FILE (GB-month); OPS (request); EGRESS (GB); BACKUP-PROTECTED (GB-month); RESTORE (job/GB); DR (workload-month with RPO/RTO) |
| 08 | Email Infrastructure | MAILBOX (seat-month); ARCHIVE (GB-month/seat); TRANSACTIONAL (1k sends); MARKETING (contact tier+sends); IP (IP-month); MIGRATION (mailbox/project) |
| 09 | SMS, Voice & Omnichannel Communication | SMS (segment); WHATSAPP (conversation/message/category as provider bills); VOICE (minute); NUMBER (number-month); EMAIL/OMNICHANNEL events; sender-ID registration (one-time/renewal if authorized) |
| 10 | Payment Infrastructure, Billing & Fintech | PAYMENT (transaction/%/fixed); PAYOUT (payout); REFUND (event); RECONCILIATION (account-month); BILLING (tenant-month); CONTROL-NUMBER only after authorization |
| 11 | Developer Tools & API | API-REQUEST (1k/1M); WEBHOOK (event); API-LOG (GB-month); EDGE (compute); TEAM (seat-month); SUPPORT (tier-month) |
| 12 | Software Development, DevOps & Deployment | ENGINEERING (hour/day); MILESTONE (deliverable); CI (runner-minute); DEPLOY (environment-month); MIGRATION/PROJECT (fixed scope); MANAGED-DEVOPS (retainer-month) |
| 13 | Cybersecurity & Information Security | ASSESS/PENTEST (authorized engagement); SCAN (asset-month); MONITOR (endpoint/log GB); INCIDENT (hour/retainer); TRAINING (seat); HARDEN (project) |
| 14 | Monitoring, Observability & SRE | HOST (host-hour); METRIC (series/sample); LOG (GB ingest+retention); TRACE (span); SYNTHETIC (check); ONCALL (coverage-month) |
| 15 | AI, ML & Automation Infrastructure | TEXT/EMBED (model-version tokens); IMAGE (image); AUDIO (minute/token); VIDEO (generated second); GPU (GPU-second/hour); VECTOR (GB+ops); AGENT (task+tools); AUTOMATION (run/seat) |
| 16 | Media, Video & Realtime Infrastructure | RTC (participant-minute); STREAM (viewer-minute); RECORD (minute); TRANSCODE (source minute/profile); STORAGE (GB-month); DELIVERY/TURN (GB) |
| 17 | Data Engineering & Analytics | INGEST (GB/event); TRANSFORM (run/compute-minute); WAREHOUSE (compute-hour); QUERY (TB scanned); STORAGE (GB-month); DASHBOARD (seat); PIPELINE (pipeline-month) |
| 18 | Business Applications & Digital Productivity | APP (seat-month); MODULE (module-month); WORKFLOW (run); STORAGE (GB-month); INTEGRATION (connector-month); IMPLEMENTATION (project) |
| 19 | IT Consulting, Managed IT & Professional Services | ASSESSMENT (engagement); SERVICE-DESK (user/device-month); MANAGED-SITE (site-month); ONSITE (visit/day); PROJECT (milestone); RETAINER (month) |
| 20 | IoT, Smart Systems & Connected Infrastructure | DEVICE (device-month); CONNECTIVITY (SIM/MB/GB); EVENT (event); GATEWAY (device-month); STORAGE (GB-month); INSTALL (site/project); MANAGED-FLEET (fleet-month) |
| 21 | Digital Trust, Compliance & Identity | VERIFY (check); AUTH/OTP (event/channel); SIGN (document); CERT (certificate-year); AUDIT/COMPLIANCE (scoped engagement) |
| 22 | Licensing, Software Distribution & Digital Products | LICENSE (seat-month/year); SUBSCRIPTION (term); ACTIVATION (event); ADDON (seat/term); SUPPORT (tenant-month); DIGITAL-PRODUCT (license) |

SKU family labels are canonical candidates, not all sellable SKUs. Create concrete SKU only after specification, delivery model, region, provider, cost and eligibility are documented.

## 5. Required SKU record

Every SKU must include:
- Immutable SKU ID, family, category, product ID, display name, description, status and owner.
- Version, effective-from/to, approval ID, change reason and audit actor/time.
- Delivery model: owned, managed, integrated, reseller, partner-delivered or professional service.
- Provider offer ID, provider, region, capability evidence, contract status, fulfilment route and fallback.
- Exact specification, unit, included quantity, hard limits, soft alerts, overage behavior and fair-use policy.
- Billing model: one-time, daily, weekly, fixed 30-day, calendar-month, annual, per-seat, per-device, per-resource, usage-metered, tiered, volume, prepaid bundle, committed use, quote or hybrid. Never conflate calendar month and 30-day term.
- Currency, base price, setup fee, tax treatment, renewal price, proration, cancellation, refund, trial and credit rules.
- Cost basis: provider wholesale, compute, storage, egress, API operations, FX, payment collection/payout fees, tax, support, fraud/chargebacks, refunds, partner share and allocated overhead.
- Margin floor, contribution margin, pricing formula, approval, customer-visible disclosures and quote snapshot.
- Entitlements, quotas, service limits, metering source, idempotency key, observed/received timestamps, corrections and cost attribution.
- Support tier, SLA, RPO/RTO where applicable, maintenance and incident responsibility.
- Evidence references, competitor comparisons, last verified timestamp, confidence grade and unresolved blockers.

## 6. Commercial status vocabulary

Use exactly: DISCOVERY, NEEDS_EVIDENCE, NEEDS_QUOTE, PROPOSED, APPROVED, ACTIVE, SUSPENDED, RETIRED. APPROVED requires named approver, date, evidence and scope. ACTIVE additionally requires provider/legal/operational launch gates. No inferred status.

## 7. Price calculation and protections

For fully loaded unit cost C and target gross margin m, minimum pre-tax price is C/(1-m). Do not use C*(1+m) as gross-margin pricing. Cost must include direct and attributable variable costs plus approved risk/overhead allocation. If C, m, FX, tax or supplier contract is unknown, price status is NEEDS_QUOTE or NEEDS_EVIDENCE, not guessed.

No silent paid conversion after trial/credits. No surprise overage. Show estimate, usage, limits, budget alert and hard-stop behavior before activation. Preserve price history; quote/order/subscription/invoice records retain immutable snapshots. Price updates require effective dates, approvals, customer notice and renewal rules.

## 8. Wave research index and limits

- Wave 01: categories 01, 02 and 09 — `SKU_LEVEL_COMPETITIVE_PRICING_WAVE_01.md`.
- Wave 02: categories 03–08 — `SKU_LEVEL_COMPETITIVE_PRICING_WAVE_02.md`.
- Wave 03: categories 10–22 — `SKU_LEVEL_COMPETITIVE_PRICING_WAVE_03.md`.
- All-category comparison framework: `COMPETITOR_PRICING_BENCHMARK_MATRIX.md`.

The Waves are research snapshots and provisional hypotheses. Public retail prices are not TEKORA wholesale costs. Do not treat any suggested target band as approved customer pricing. Several categories require direct supplier quotations, licensing/authorization, legal review or operational validation.

## 9. OpenCode implementation sequence

1. Audit repo and current phase; do not assume docs-only or clean working tree without evidence.
2. Build catalogue domain model and migrations only after Phase 04 architecture and Phase 05 foundation approvals.
3. Implement category/product/SKU/provider-offer/price-book/version/quote/entitlement/metering models with stable IDs and constraints.
4. Build read-only catalogue admin and pricing simulation before publishing/charging.
5. Implement quote snapshots and invoice calculations with deterministic decimal arithmetic, currency precision and tax adapters.
6. Implement idempotent usage ingestion, corrections, late events, aggregation and cost allocation.
7. Implement approval workflow, audit trail, effective dates, customer notices and immutable history.
8. Add provider adapters only after due diligence and credentials/contracts; sandbox first.
9. Add test fixtures with synthetic data clearly marked; never mix fixtures with production data.
10. Test edge cases: timezone/renewal boundaries, leap years, DST where relevant, retries, duplicate events, late/corrected usage, partial refunds, cancellation, proration, tax rounding, FX changes, suspended providers and price-version transitions.
11. Keep UI aligned with global design system and accessible, transparent pricing disclosures.
12. Update README, module docs, Blueprint traceability and phase report with actual evidence.

## 10. Explicit non-authorizations

This document does not authorize live payments, control-number collection, money custody, payouts, domain registration, carrier connectivity, sending bulk messages, issuing identity certificates, security testing against third parties, production cloud spend, or customer-facing price publication.

## 11. Research document precedence and OpenCode navigation

For Categories 03–22, `SKU_LEVEL_COMPETITIVE_PRICING_WAVES_02_04.md` is the detailed consolidated research source and includes the broader SKU families, monetization models, benchmark signals, free policy, gates and source list. `SKU_LEVEL_COMPETITIVE_PRICING_WAVE_02.md` (03–08) and `SKU_LEVEL_COMPETITIVE_PRICING_WAVE_03.md` (10–22) are focused summaries prepared for quick navigation; they do not supersede or replace the consolidated document. For 01/02/09, use Wave 01. If a summary differs from the consolidated evidence, flag the discrepancy and use the detailed source pending owner review.

For first-session setup, follow `docs/OPENCODE_START_HERE.md` and the `/tekora-start` command. Do not skip Phase 00 audit or the explicit phase approval gate.
