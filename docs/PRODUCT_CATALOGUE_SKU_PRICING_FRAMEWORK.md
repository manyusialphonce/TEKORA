# TEKORA — Product Catalogue, SKU & Pricing Framework

**Status: PROPOSED / DISCOVERY.** No customer-facing price, margin, provider cost, plan allowance or commercial promise is approved by this document.

## 1. Catalogue hierarchy
Service category → product family → product → offer/SKU → versioned price book → region/currency → provider offer/fulfilment route → customer eligibility. Separate the product promise from its delivery route. One product may have multiple providers, but capability, geography and contract must be explicit.

## 2. Product classification
- CORE PLATFORM: common control-plane capability required across categories.
- MVP CANDIDATE: small number of validated offers with manageable delivery and support.
- LAUNCH EXPANSION: proven adjacent products.
- ADVANCED: complex/high-operational-burden products.
- PARTNER-DEPENDENT: cannot be sold before provider/contract/authorization.
- DEFERRED: excluded from initial launch.
A category being documented does not mean every SKU is in MVP.

## 3. SKU schema (mandatory fields)
`sku_id`, `product_id`, `version`, `display_name`, `description`, `category_id`, `delivery_model`, `provider_offer_id`, `region`, `currency`, `billing_model`, `billing_unit`, `base_price`, `included_quantity`, `overage_rate`, `minimum_commitment`, `setup_fee`, `trial_policy`, `renewal_policy`, `proration_policy`, `cancellation_policy`, `refund_policy`, `tax_treatment_reference`, `cost_basis_version`, `margin_floor_policy`, `quota_policy`, `support_tier`, `effective_from`, `effective_until`, `status`, `approval_id`.

Never overwrite a price already used by an order. Publish a new effective-dated price version; preserve historical invoices and quote snapshots.

## 4. Billing models
One-time; recurring monthly/calendar or fixed 30-day (must be explicitly distinguished); daily; weekly; annual; per seat/user/device/resource; per API call/event/message/minute/GB/GB-month/compute unit; tiered; volume; prepaid bundle/credits; committed-use; professional-services milestone/retainer; hybrid base + usage + overage. Define rounding, minimum charge, free allowance, grace, pause/suspend, proration, renewal and FX policy per SKU.

## 5. Pricing engine rules
- Quote must snapshot SKU, price version, currency, quantity, tax basis, discount, promotion, validity and terms.
- TZS is the default discovery-market currency; support other currencies only where provider settlement, tax and FX treatment are validated.
- Do not silently convert provider USD costs using a stale rate. Store rate source, timestamp and FX buffer policy.
- Cost model includes provider cost, tax, FX, transaction fee, support, infrastructure, storage/egress, refunds/chargebacks, fraud, partner share and operational overhead.
- Set minimum gross-margin or contribution-margin policy per category; require approval below threshold.
- Distinguish fixed recurring, usage estimate and actual metered charge.
- Show customer total before order confirmation, including known pass-through charges and tax treatment.
- Pricing changes are versioned and future-effective; notify affected customers according to contract and applicable law.
- Avoid guaranteed savings claims without measured baseline and methodology.

## 6. Metering record
`meter_event_id`, tenant/project/resource, `meter_name`, unit, quantity, observed_at, received_at, source/provider, source_event_id, idempotency_key, aggregation_window, estimated_or_actual, correction_of, region, dimensions, cost_allocation_tags, integrity metadata. Keep raw events and derived aggregates separately. Define late event, duplicate, correction, missing data, dispute and retention behavior.

## 7. Initial candidate packaging (not approved)
| Category group | MVP candidate hypothesis | Defer until evidence |
|---|---|---|
| Shared platform | Organizations, projects, roles, catalog, order, support, notifications, audit, usage and billing foundation | Complex multi-region orchestration |
| Domains/DNS | Domain portfolio, DNS management via approved integration | Registrar claim / .tz registration without accreditation or partner |
| Hosting | Static/app hosting or managed CMS pilot | Broad dedicated/GPU catalogue |
| Cloud/containers | Inventory, cost visibility, controlled provisioning via one verified provider | Multi-cloud marketplace and managed Kubernetes |
| Networking | Network inventory, change approvals, monitoring integration | Carrier/private-link guarantees |
| Data/DB/storage | One engine + backup/restore workflow; storage integration | Broad database fleet and DR SLA |
| Email/comms | Transactional email and one approved SMS route | Campaigns, voice and multi-channel orchestration |
| Payments | Provider-neutral payment state model, sandbox simulator, invoice and reconciliation | Holding funds, regulated processing, public control-number claims |
| Developer hub | API catalogue, sandbox keys, docs, webhook test/replay | Public API marketplace with unapproved providers |
| DevOps/security/observability | Integrations, deployment audit, authorized assessment workflows, basic monitoring | 24/7 MDR/SRE/SOC claims |
| AI/media/data | Internal assistant grounded in documentation, telemetry integrations | High-volume AI inference, live media hosting |
| Business/consulting/IoT/trust/licensing | Managed project/service workflow, SSO/MFA foundations | Device safety-critical control, identity proofing, publisher marketplace |

This is a prioritization hypothesis. Validate with interviews, signed pilot intent, delivery costs and support capacity.

## 8. Pricing acceptance criteria
- Quote reproducible from stored price version.
- Invoice matches quote, tax policy and quantity.
- Meter events idempotent and auditable.
- Late/corrected usage recalculates according to disclosed policy.
- Renewal, cancellation, proration, downgrade and overage scenarios tested.
- Customer sees estimated vs actual and provider pass-through fees.
- Finance can reconcile provider invoices and customer charges.
- Admin price changes require role separation, approval and audit.


---

## 9. Mandatory platform-wide pricing and monetization strategy (26 November 2026)

**Priority: CRITICAL — mandatory across all 22 categories and every customer-facing product.**  
**Status: STRATEGY BASELINE PROPOSED; every TEKORA retail price remains UNAPPROVED until cost, provider, tax, margin and market validation.**

Pricing is a product capability and a strategic market-positioning decision. It must not be left to manual ad hoc decisions or applied as one blanket discount across the catalogue.

### 9.1 Commercial positioning

TEKORA should compete on **strong value at a fair, locally understandable and predictably billed price**, not simply claim to be the cheapest provider.

- Benchmark the exact comparable service, region, resource specification, usage allowance, support, SLA, taxes, billing commitment and renewal price.
- Where our delivery cost, service quality and risk allow, target a modest undercut of a genuinely comparable public competitor price. Initial test hypothesis: **3–8% below the comparable market reference** for selected price-sensitive standard SKUs; this is a pricing experiment, not a universal rule or approved promise.
- In some categories, compete at price parity or above where TEKORA includes meaningful local value: TZS billing, local support, managed operations, Tanzanian payment methods, clear invoices, local onboarding, data-residency options where genuinely available, or a better service level.
- Never undercut below fully loaded variable cost plus required contribution margin. Do not sell a loss-making SKU just to advertise a low headline price.
- Separate provider pass-through costs, TEKORA platform/service fee, taxes, optional add-ons and one-time setup charges.
- Compare renewal prices as carefully as introductory prices. No misleading first-year price that hides a large renewal increase.
- Provide TZS as the primary Tanzania-market display and settlement currency where supported. Display USD or other currencies only with a timestamped FX source and clear indication that the final settlement may vary.
- Publish effective date, tax inclusion/exclusion, billing unit, included allowance, overage, renewal, cancellation and refund terms next to each price.

### 9.2 Benchmark research snapshot and evidence rules

Research snapshot: **26 November 2026**. Prices are public-page observations, not binding supplier quotations. They may vary by country, region, account type, promotion, billing commitment, tax, exchange rate, traffic profile and product version. Re-check official pricing pages and obtain written partner quotations immediately before approving TEKORA SKUs.

| Area | Public benchmark observed | What it tells TEKORA | Source |
|---|---|---|---|
| Tanzania VPS | Lineserve Linux 2 GB: TZS 32,400/month; 4 GB: TZS 64,800; 8 GB: TZS 129,600. Specs include CPU/RAM/SSD/IP/traffic. | Local TZS benchmark exists; compare like-for-like resources, location, bandwidth, IPv4, SLA, VAT and management. | https://www.lineserve.co.tz/vps |
| Tanzania managed VPS | Hi-Tech Hosting published 4 GB/4 vCore/80 GB NVMe managed VPS at TZS 34,500/month; higher plans listed. | Managed service may have a different price/specification profile; validate exact support, CPU allocation and traffic fair-use before comparison. | https://hitechwebhosting.com/tz/managed-vps |
| Tanzania domains | Sakurahost published .co.tz registration TZS 19,500/year and renewal TZS 25,000/year; WazoHost published .co.tz TZS 22,000 new and TZS 25,000 renewal. | Renewal is not necessarily equal to registration. Separate registry cost, registrar/partner margin and taxes. | https://www.sakurahost.co.tz/domains/ ; https://my.wazohost.co.tz/domain/pricing |
| Tanzania SMS | Send published TZS 20/SMS for 1–10,000 credits, declining by volume to TZS 10.7/SMS above 1 million; prices before VAT. | Use per-segment pricing, destination-specific routes, prepaid bundles and volume tiers; do not treat every SMS as one segment. | https://send.co.tz/pricing/ |
| Tanzania payment gateway | BLMPay published percentage fees varying by verification tier and payment method (example: Business Mobile Money 3%, card 3.5%, QR 2.5%) plus payout charges. | Fees are channel-, risk-, verification- and payout-dependent. TEKORA must not publish one generic payment fee without a signed provider schedule and regulatory classification. | https://pay.blmtec.co.tz/ |
| Managed database | Supabase Free $0 with 500 MB database, 5 GB egress and other limits; Pro starts at $25/month with additional usage rates. Prisma Postgres also publishes a $0 tier and paid tiers. | Freemium with explicit resource limits is an established pattern; storage, compute, egress, backups and support must be separately costed. | https://supabase.com/pricing ; https://www.prisma.io/pricing |
| Object storage | Cloudflare R2: 10 GB-month free, then standard storage $0.015/GB-month; request charges apply, egress is free. Backblaze B2 starts at $6.95/TB/month and includes egress allowance subject to terms. | Storage pricing needs storage class, operations, retrieval, egress and retention dimensions; never price by GB alone if operations create material costs. | https://www.cloudflare.com/products/r2/ ; https://www.backblaze.com/cloud-storage/pricing |
| Edge/serverless | Cloudflare Workers has a free allowance and a paid plan from $5/month with metered overages and stated included usage. | A small platform base plus usage can be easier to enter than a large fixed commitment. | https://developers.cloudflare.com/workers/platform/pricing/ |
| Developer hosting | Vercel publishes included usage and metered prices for functions, builds, storage, requests and team seats. | Price build minutes, compute, requests, storage, environments and seats independently where costs differ. | https://vercel.com/pricing |
| DNS | AWS Route 53 public hosted zones start at $0.50/zone/month, with DNS query charges. | DNS can be priced per zone plus usage or bundled with a domain/hosting SKU; query and premium routing costs must be covered. | https://aws.amazon.com/route53/pricing/ |
| Business email | Zoho Workplace Africa/Middle East price list includes low-cost per-user monthly annual-billing offers; Microsoft 365 business plans are higher and differ by apps/storage/security. | Mailbox, suite, storage, security and support are distinct value tiers; reseller entitlement and tax must be validated. | https://www.zoho.com/workplace/pricing.html ; https://www.microsoft.com/en-us/microsoft-365/business/microsoft-365-plans-and-pricing |
| Transactional email | Amazon SES Essentials published $0.16 per 1,000 emails in the first volume tier, with tiered rates. | Meter by recipient/message/attachment/region as applicable; distinguish email API infrastructure from mailbox hosting and deliverability services. | https://aws.amazon.com/ses/pricing/ |
| Monitoring/logs | Grafana Cloud publishes free telemetry/log allowances and usage-based paid rates, plus platform fee on Pro for some products. | Free observability is viable with caps and retention limits; ingestion, active series, host hours and retention are billable dimensions. | https://grafana.com/pricing/ ; https://grafana.com/products/cloud/logs/ |
| Developer assistant | GitHub Copilot publishes Free and paid plans with feature/usage differences. | Developer tools can use individual Free/Pro and team/business plans; seat and premium request entitlements must be explicit. | https://github.com/features/copilot/plans |
| Cloud compute international | AWS Lightsail publishes fixed monthly resource bundles; price varies by OS/region and transfer allowance. | A simple fixed-size SKU is useful for predictable workloads; region-specific price and bandwidth need adjustment. | https://aws.amazon.com/lightsail/pricing/ |
| Payment processing international comparator | Paystack publishes country-specific fees; its listed country coverage/fees do not establish availability or authorization for Tanzania. | Use only as a structural benchmark, not as a Tanzania provider or price promise. | https://support.paystack.com/en/articles/2130306 |

TCRA directs .tz applicants to accredited registrars and publishes domain pricing through the official .tz ecosystem. TEKORA must verify its own accreditation/partner route and the current registry schedule before selling .tz registration. Public competitor prices do not replace registry/provider quotes. Official references: https://tcra.go.tz/faq and https://www.karibu.tz/registrars.

### 9.3 Pricing model by all 22 service categories

The following defines the required charging dimensions and initial monetization approach. It does **not** authorize an arbitrary retail price where supplier cost, legal status or comparable specifications are unknown.

| # | Category | Primary charging units | Free / entry offer hypothesis | Paid monetization and pricing guardrail |
|---:|---|---|---|---|
| 01 | Domains, DNS & Internet Services | Domain-year by TLD; DNS zone/month; query/request; premium DNS add-on; transfer/renewal | Free DNS for a limited number of zones; free managed developer subdomain under controlled policy | Domain registration/renewal at registry + registrar/partner cost + service margin. Publish registration AND renewal separately. Premium DNS/managed DNS usage-based. Never promise .tz registration without authorized registrar route. |
| 02 | Web Hosting, Application Hosting & Compute | Instance/month or hour; vCPU-hour; GB RAM-hour; storage GB-month; bandwidth/egress GB; build minute; deployment/project | Limited static site or preview tier, with sleep/usage caps and no production SLA | Fixed resource bundles plus metered overage. Separate managed/unmanaged, Linux/Windows licensing, backup, IP, support and region. Never offer unlimited compute/bandwidth without a fair-use/cost model. |
| 03 | Cloud Infrastructure & Virtualization | vCPU-hour; RAM GB-hour; disk GB-month; snapshot; image; IP; network transfer | Small sandbox quota or trial credits with expiry/usage cap | Resource-based pay-as-you-go and committed-use discounts. Set spend limits, alerts and hard quotas. Provider cost/region/FX must be covered. |
| 04 | Containers, Kubernetes & Runtime | vCPU/memory runtime; node/hour; cluster/month; request; registry GB-month; build/deploy minute; egress | Small single-app/container preview or learning quota; no managed production cluster free by default | Cluster/node management fee plus infrastructure pass-through and usage. Charge for control plane/operations/support where applicable. Managed Kubernetes is partner/capacity dependent. |
| 05 | Networking & Connectivity | IP/month; bandwidth/GB; VPN tunnel/month; device/site/month; network service/month; managed change | Basic network inventory/health view; limited monitoring | Per resource/site/tunnel plus bandwidth and managed support. Carrier, cross-connect, transit and hardware costs pass through transparently. |
| 06 | Database Services | Database instance/hour; compute; storage GB-month; operations; backup GB; restore; egress | Small dev database with capped storage/compute, sleep/pause or inactivity policy, limited backups | Instance tier plus storage, backup retention, IOPS/operations and egress. Charge restore/managed DBA separately where labor intensive. Never imply production durability for free tier. |
| 07 | Storage, Backup & Disaster Recovery | GB-month by class; API operation; retrieval GB; egress GB; backup protected GB; retention days; restore job | Small object-storage quota or backup trial with short retention and no guaranteed RPO/RTO | Storage class + operations + retrieval + egress + retention. DR priced by protected capacity, replication region, recovery tier and tested RPO/RTO. Restore testing is a billable service tier. |
| 08 | Email Infrastructure | Mailbox/user/month; storage GB; outbound recipient/1,000; domain; dedicated IP; deliverability/support | Limited developer/test email sandbox; restricted transactional test quota, no bulk campaigns | Mailbox subscriptions per seat; sending per recipient/volume/region; dedicated IP and deliverability add-ons. Enforce anti-spam and sender verification. |
| 09 | SMS, Voice & Omnichannel Communication | SMS segment/destination; WhatsApp conversation/template/category; voice minute; number/month; recording GB; channel fee | Small test quota, verified sandbox destinations or limited trial credits | Provider pass-through + TEKORA orchestration fee/margin; volume tiers. Separate segments, destination, sender ID, templates, carrier surcharges, VAT and channel. Never absorb unpredictable carrier cost. |
| 10 | Payment Infrastructure, Billing & Fintech Integrations | Transaction percentage + fixed fee; payout; refund; reconciliation item; invoice/control-number service fee where legally permitted | Sandbox transactions and test control numbers free; no real-money processing in free plan | Provider fee + disclosed TEKORA fee only if permitted by contract and law. Differentiate gateway technical subscription from regulated payment fee. No custody, settlement or fee claim without licensing/provider approval. |
| 11 | Developer Tools & API Infrastructure | API calls; requests; API key/application; webhook delivery; event; bandwidth; build minute; seat | Free developer account, limited API requests, test keys, docs and webhook sandbox | Usage tiers, team seats, higher limits, audit, analytics, SLA and support. Rate limits and overage must be visible before use. |
| 12 | Software Development, DevOps & Deployment | Build minute; deployment; pipeline; runner minute; artifact GB-month; seat; managed project/retainer | Free repository integration or preview build quota for individual developers | Usage-based CI/CD plus team seats and managed DevOps. Professional engineering is quoted by scope/milestone/retainer, not an artificial per-request fee. |
| 13 | Cybersecurity & Information Security | Asset/month; endpoint/device/month; scan; assessment; log GB; incident retainer; analyst hour | Basic posture checklist and limited self-service scan with explicit scope | Per asset/endpoint/scan and managed response tier. Penetration testing, incident response and compliance advisory require authorization, scope and qualified staffing; no free unlimited scans. |
| 14 | Monitoring, Observability & SRE | Host-hour; active series; GB logs/traces; event; synthetic check; retention day; on-call coverage | Small number of monitors and limited retention/telemetry | Base platform fee + ingestion/host/series/retention/alert overage. 24/7 SRE/on-call is a separately staffed paid service with explicit SLA. |
| 15 | AI, ML & Automation Infrastructure | Input/output tokens; model call; image/audio/video unit; GPU-second/hour; embedding; vector GB-month; workflow run | Small monthly credit, low-rate models, limited tokens or local sandbox; strict spend cap | Provider cost pass-through + orchestration fee/margin; charge per model/token/media/GPU and storage. User-supplied API keys may be supported. No unlimited AI usage in free plans. |
| 16 | Media, Video & Realtime Infrastructure | Participant-minute; room-minute; stream-minute; recording GB; transcoding minute; delivery GB; concurrency | Small demo room, limited participant-minutes and short recording retention | Usage-based participant/stream/recording/transcoding/egress plus optional managed support. LiveKit/media provider and egress costs must be modeled before publishing. |
| 17 | Data Engineering & Analytics | Rows/events processed; compute-hour; pipeline run; GB scanned/stored; dashboard/seat; retention | Small sample dataset and limited scheduled runs | Metered compute/rows/GB scanned, pipeline tier, dashboard seats and retention. Heavy jobs use budgets, quotas and cost estimates. |
| 18 | Business Applications & Digital Productivity | User/seat/month; workspace; storage; workflow run; document/signature; add-on | Limited personal workspace or trial; selected collaboration features | Per-seat plans, storage/workflow add-ons, business/enterprise features, support and migration/setup fees. Third-party license pass-through must be clear. |
| 19 | IT Consulting, Managed IT & Professional Services | Hour/day; project milestone; monthly retainer; device/site; response tier | Initial discovery call or bounded assessment, not unlimited consulting | Fixed-scope quote, milestone, retainer or SLA tier. Record deliverables, exclusions, hours, response windows and change requests. |
| 20 | IoT, Smart Systems & Connected Infrastructure | Device/month; message/event; data GB; SIM/connectivity; command; gateway; support | Small developer device quota and simulated telemetry; no safety-critical live control | Per active device + messaging/connectivity/storage + managed gateway/support. Hardware, SIM/carrier, installation and field visit charged separately. |
| 21 | Digital Trust, Compliance & Identity | Verified identity/check; credential/month; signing transaction; certificate/year; audit/export; compliance project | Test identities, sandbox certificates and limited policy templates | Per verification/signature/certificate or managed compliance engagement. Regulatory trust services require approved providers and legal validation. |
| 22 | Licensing, Software Distribution & Digital Products | License/user/device/year; subscription; activation; download/bandwidth; update/support | Free/open-source distribution and evaluation license only where publisher permits | Authorized reseller price + disclosed margin, renewal and support. Respect publisher territory, volume, transfer, activation and audit terms. Never sell unauthorized keys or imply ownership of third-party licenses. |

### 9.4 Free, freemium, trial and paid policy

TEKORA must support different monetization models per SKU. Free is a deliberate acquisition and adoption tier, not a universal promise that every service is free.

**Plan types (distinct and must not be conflated):**
- **Free forever:** recurring $0/TZS 0 plan with a defined feature/usage allowance and fair-use policy. Available only where ongoing marginal cost and abuse exposure are acceptable.
- **Freemium:** a permanent limited free tier; users upgrade when they need more capacity, features, collaboration, reliability or support.
- **Free trial:** time-limited access to a paid plan or higher tier. State exact start/end, included usage, conversion behavior and cancellation.
- **Promotional credits:** finite value/usage credits with expiry, eligibility, non-transferability and abuse controls.
- **Sandbox/developer tier:** simulated or test-mode functionality; explicitly no real transactions, delivery guarantee or production SLA.
- **Paid plans:** recurring, one-time, prepaid, usage-based or hybrid.
- **Pay-as-you-go:** no fixed subscription where possible; user pays for actual billable consumption with budgets and alerts.
- **Quote/contract:** enterprise, managed, regulated or labor-intensive service requiring a scoped proposal.

**Free-tier design rules:**
1. Each SKU must declare whether it is FREE_FOREVER, FREEMIUM, TRIAL, CREDIT, SANDBOX, PAID or QUOTE.
2. State limits by measurable unit: projects, resources, CPU/RAM, GB, requests, messages, tokens, participant-minutes, seats, retention, support and concurrency.
3. State what happens at limit: block new usage, pause resource, degrade non-critical feature, ask for upgrade, or charge only after explicit opt-in. Do not create surprise overage.
4. Free resources with ongoing provider cost must have hard quotas, abuse controls, expiry/idle policies and cost monitoring.
5. Never promise a free custom domain when only a free managed subdomain is supplied. Never bundle free hosting/compute/email/storage just because a hostname is free.
6. Do not require payment details for a free tier unless justified and clearly disclosed.
7. Free-tier eligibility may be limited to one account/verified person, student/developer program, non-commercial project or other stated segment; define appeal and accessibility.
8. Do not remove a permanent free entitlement retroactively without notice and policy/contract review.
9. Do not automatically charge a customer at the end of a free trial. Require explicit opt-in for paid conversion, except where a clearly disclosed and lawfully accepted subscription arrangement permits otherwise; send reminders and provide easy cancellation.
10. Allow upgrade at any time. Downgrade should take effect with clear treatment of excess usage, data retention and service continuity.
11. Provide export path and reasonable grace period before deletion/suspension, subject to security/abuse/legal requirements.
12. Protect platform sustainability: no unlimited compute, AI, SMS, voice, video, storage egress, managed support or human consulting at zero price.

**Suggested plan ladder (names are provisional):**
- Free / Developer — onboarding, learning and low-volume testing.
- Starter — individuals and small projects.
- Growth — growing businesses and teams.
- Business — operational workloads, collaboration and support.
- Scale — high usage, advanced controls and predictable service.
- Enterprise / Custom — negotiated terms, procurement, dedicated support and SLA where actually deliverable.

Not every category needs all six tiers. A domain may have per-year SKUs; SMS may be prepaid credits; consulting may be quote-based; a database may be free + usage + managed tiers. Do not force a subscription where the market/product does not fit.

### 9.5 Proposed market pricing policy

Use this decision algorithm for every price version:

1. Identify the closest three to five valid competitors or supplier alternatives, prioritizing Tanzania/East Africa when genuinely comparable, then international providers.
2. Normalize every benchmark to identical units and equivalent resource/feature/service levels. Convert billing periods and included usage; exclude incomparable promotions.
3. Record registration and renewal separately; monthly and annual separately; list price and effective discounted price separately.
4. Capture country/region, currency, tax, VAT inclusion, date checked, URL, terms, support, SLA, quotas and confidence.
5. Obtain actual provider/wholesale quote and calculate fully loaded cost of goods sold (COGS): provider cost, FX spread, transaction fee, taxes borne by TEKORA, infrastructure overhead, support labor, fraud/refunds, partner share, backup/egress and compliance.
6. Set a category-specific minimum contribution margin and risk buffer. For a simple resale SKU, price floor must cover provider cost + variable platform cost + payment/FX cost + support allocation + tax treatment + required contribution. For managed services include labor and on-call coverage.
7. Calculate a target price: comparable benchmark less a modest 3–8% where financially viable, or parity/premium where value warrants it. Select a price at or above the floor.
8. If the target is below the floor, do NOT force a discount. Re-negotiate supplier cost, reduce included allowance, change packaging, use a different provider, or position on local value.
9. Test price elasticity with a controlled pilot and real customer evidence before mass publication.
10. Obtain pricing/finance approval, create immutable price-book version and effective date, then publish.
11. Review high-volatility pass-through prices monthly or when supplier pricing changes; review stable subscriptions at least quarterly and full competitor benchmarking at least quarterly.
12. Notify affected customers of material changes before effective date under contract and applicable law.

### 9.6 Price calculation and guardrails

For cost-plus price calculation, define all components explicitly:

- Direct provider/wholesale unit cost.
- Variable infrastructure and usage cost.
- FX conversion source, timestamp and buffer.
- Payment collection and payout costs.
- Tax treatment and tax borne by seller.
- Support and operations allocation.
- Partner/reseller share.
- Fraud, refund, chargeback and credit risk.
- Required contribution margin.
- Promotional discount and its funding owner.

Do not use one global markup percentage for all 22 categories. Compute category and SKU-level floor/target/ceiling and set a minimum margin by risk and support burden.

If percentage margin is used, distinguish gross margin from markup. For unit cost C and target gross margin m, price floor before applicable taxes is C/(1-m), not C*(1+m). Store calculations at adequate decimal precision; round only at the customer-facing currency boundary and document rounding.

### 9.7 Price book and billing-engine requirements

Add or explicitly map these entities to the architecture/data model:
- `PriceBook`, `PriceBookVersion`, `PriceVersion`, `PriceComponent`, `PriceRule`.
- `CompetitorBenchmark` and `BenchmarkEvidence` (URL, captured_at, geography, currency, tax, plan/spec, allowance, term, confidence, source type).
- `ProviderCostQuote`, `CostBasisVersion`, `FXRateSnapshot`, `MarginPolicy`.
- `Promotion`, `Coupon`, `CreditGrant`, `TrialEntitlement`, `FreeTierPolicy`, `UsageBudget`, `SpendLimit`.
- `CustomerQuoteSnapshot`, `SubscriptionPriceSnapshot`, `InvoiceLinePriceSnapshot`.
- `PriceApproval`, `PriceChangeNotice`, `PriceExperiment`.

Mandatory price metadata:
- Region/country and currency.
- Billing unit, billing period and minimum charge.
- Included allowance and overage rates by meter.
- Trial/free eligibility, duration, caps and conversion policy.
- Setup/activation/deposit fees.
- Tax-inclusive/exclusive display and applicable tax reference.
- Introductory vs renewal price.
- Proration, cancellation, refund, credit and suspension rules.
- Provider cost, cost-basis version and source timestamp.
- FX rate source/time/buffer.
- Price floor, target margin, approved discount and approver.
- Effective-from/effective-until and grandfathering policy.
- Customer-visible description and disclosure.

**Billing invariants:**
- No charge for blocked/failed usage unless the published contract says the billable event occurred.
- Deduplicate usage by source identity/idempotency key.
- Keep estimated and actual usage distinct; correct late/duplicate events transparently.
- Never charge beyond a spend cap unless customer explicitly authorizes it.
- Do not mutate past quote, order, invoice or subscription price snapshots.
- Do not silently move a free customer to paid.
- Payment gateway fees, TEKORA subscription fees, tax, payout fees and provider pass-through charges must remain separate ledger components.
- A control number is a payment reference/collection mechanism, not itself proof that payment has settled. Do not add a TEKORA fee to a control-number transaction unless contract and legal review permit it.
- Prevent double charging during retries, webhook replay, renewal race and reconciliation.

### 9.8 Admin pricing and finance controls

The internal platform must provide:
- Competitor benchmark registry with source URL, date, region, plan and confidence.
- Provider cost/quote registry with expiry and contract evidence.
- SKU price-book editor with version comparison and preview.
- Margin simulator showing cost, FX, tax, fees, contribution and break-even.
- Scenario calculator: price parity, 3%, 5%, 8% undercut, value premium and volume discount.
- Free-tier cost exposure dashboard: free users, active resources, cost/user, conversion, abuse and gross contribution.
- Usage budget/spend cap and alert policy.
- Promotion and coupon approvals with eligibility, duration, redemption limits and budget.
- Dual approval for price below margin floor, manual credit, refund and retroactive adjustment.
- Price-change impact report: active subscriptions, renewals, quotes and customer notices.
- Audit trail for every change, actor, approver, reason and effective time.
- Customer-facing transparency: price, units, included amount, overage, taxes, renewal and cancellation before confirmation.

### 9.9 Tanzania and regional tax/commercial validation

- Default display market: Tanzania and TZS where provider settlement and business operations support it.
- Never assume that all advertised competitor prices include VAT. Capture tax-included/excluded status for each benchmark.
- Obtain professional tax review for VAT, EFD/e-receipts, withholding, imported digital services, cross-border supply, marketplace/agent/reseller treatment and invoicing.
- Confirm the exact legal role for payment-related products before charging transaction fees or facilitating settlement.
- For .tz domains, use the TCRA/Karibu accredited registrar and published registry rules; confirm partner wholesale price, renewals, premium domains, transfers, redemption and taxes.
- For SMS/voice/WhatsApp, validate local sender registration, route quality, template rules, carrier fees and current per-destination rates.
- For software licenses, obtain publisher authorization and territory/renewal/seat conditions.
- Do not advertise local data residency, SLA, certification, compliance or 24/7 support unless contract, architecture and operating evidence prove it.

### 9.10 Initial proposed free-to-paid packaging examples

These are product-design examples, not final price quotes:

| Product family | Free entry | Upgrade trigger | Paid model |
|---|---|---|---|
| Developer domain | One controlled TEKORA-managed subdomain, basic DNS and HTTPS if domain/provider capability is verified | Additional hostnames, custom registrable domain, advanced DNS, team controls | Per hostname/domain-year and optional DNS add-ons |
| Static preview hosting | One small project, build quota, bandwidth cap, sleep/inactivity policy | More projects, builds, bandwidth, custom domains, collaboration | Base project tier + build/compute/bandwidth usage |
| Developer API | Test keys, docs, low request quota, sandbox webhooks | Production keys, higher rate, team/audit/analytics | Per request tier + seats/add-ons |
| Database | Small dev instance/storage, pause on inactivity, limited backup | Always-on, more compute/storage, PITR, longer backup retention | Instance + storage + backup + egress |
| Object storage | Small capped storage and operations | Higher capacity, retention, replication, retrieval/egress | GB-month + operations + retrieval/egress |
| Monitoring | A few checks, limited hosts/series and short retention | More hosts/telemetry, longer retention, alerting/on-call | Host/series/GB ingested/retention |
| SMS/voice | Test mode or bounded trial credits to verified recipients | Production sender/volume and multiple destinations | Prepaid credit + per-segment/minute/destination |
| Email | Test sandbox or low daily transactional quota | Production sending, dedicated IP, deliverability support | Per recipient/volume + add-ons |
| AI | Small capped monthly credits | More tokens, models, concurrency, private deployments | Token/media/GPU usage + orchestration |
| Business applications | Limited personal workspace or trial | Team seats, storage, workflows, admin and compliance | Per seat/month + usage add-ons |
| Security | Basic self-service posture checks | Scheduled scans, multiple assets, managed response | Per asset/scan/retainer |
| Professional services | Initial bounded discovery session | Implementation, migration, ongoing operations | Fixed quote, milestone or retainer |

### 9.11 Pricing acceptance criteria (mandatory)

A category/SKU is not ready for sale until:
- At least three comparable market references are captured where available, or a documented reason why the market is opaque/unique.
- Benchmark specifications are normalized and dated.
- Provider/wholesale cost is evidenced and current.
- Price floor, contribution margin and risk buffer are calculated.
- Currency, FX, tax and rounding are validated.
- Registration/introductory/renewal and monthly/annual prices are separately visible where applicable.
- Free/trial limits and end-of-limit behavior are tested.
- Upgrade, downgrade, renewal, cancellation, proration, refund and failed-payment behavior are tested.
- Usage metering, overage, spend cap and no-surprise-billing controls are tested.
- Finance reconciliation and price-change audit are demonstrated.
- Customer disclosure and terms are reviewed.
- Required commercial/legal/provider approvals exist.
- Price is versioned, approved and effective-dated.

**Status by category:** pricing architecture requirements are now defined for all 22 categories. Public benchmark research is PARTIAL, not a complete 3–5-provider comparison for every SKU. No TEKORA final customer-facing retail price is approved by this addendum.
