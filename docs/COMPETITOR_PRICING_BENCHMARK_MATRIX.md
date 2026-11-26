# TEKORA — Competitive Pricing Benchmark Matrix (All 22 Categories)

**Research snapshot:** 26 November 2026  
**Status:** DISCOVERY / PROVISIONAL — NOT AN APPROVED TEKORA PRICE LIST  
**Currency convention:** Local Tanzania offers are shown in TZS as published. International prices remain in source currency (mostly USD). Do not convert currencies without a dated FX source and recorded rate. Taxes, carrier fees, FX, payout costs and provider-specific conditions may be additional.

## 1. Purpose and pricing rules

This matrix turns the platform-wide pricing policy into category-level research and launch decisions. It is additive to, and must be read with, `PRODUCT_CATALOGUE_SKU_PRICING_FRAMEWORK.md`, the Master Blueprint, provider due diligence and the technical decision register. It does not replace earlier requirements or reduce the 22-category scope.

TEKORA's working market hypothesis is to price approximately **3–8% below a genuinely comparable offer** only where verified supplier cost, equivalent specification, support, taxes, delivery quality and minimum contribution margin permit. This is a testable hypothesis, not a universal discount or approved price. Use parity or a premium where TEKORA provides demonstrably better local support, management, reliability, integration or convenience. Quote-based products must not be given invented list prices.

**No TEKORA customer-facing prices are approved by this matrix.** Every candidate SKU needs supplier quotes, total-cost calculation, legal/tax review, margin simulation, approval and effective-dated price publication.

## 2. Evidence grading

| Grade | Meaning | Permitted use |
|---|---|---|
| E1 — Public price | Current public price/specification located; provider contract and delivery route not validated | Benchmark only |
| E2 — Technical validation | API/technical path tested in an authorized sandbox or controlled environment | Technical feasibility only |
| E3 — Commercial validation | Written wholesale quote, currency, region, fees, volume tiers and commercial terms obtained | Cost modelling |
| E4 — Legal validation | Local legal/regulatory classification and contractual duties reviewed | Market eligibility |
| E5 — Operational approval | Support, escalation, incident, SLA, continuity, reconciliation and runbooks accepted | Controlled sale/launch |

Most references below are E1 only. Public retail prices are not automatically TEKORA wholesale costs or evidence of resale rights.

## 3. Verified public benchmark observations

| Benchmark | Published observation | Normalization notes |
|---|---|---|
| Hi-Tech Hosting managed VPS | TZS 34,500/month for 4 vCPU, 4 GB RAM, 80 GB NVMe; higher plans also published | Managed service, 32 TB traffic advertised; compare support and resource guarantees before matching. [Source](https://hitechwebhosting.com/tz/managed-vps/) |
| Hi-Tech Hosting shared hosting | From TZS 5,500/month billed annually; plan table lists website, email, database and bandwidth limits | Introductory/billed-annually price; compare renewal and actual storage/resource policy. [Source](https://hitechwebhosting.com/tz/shared-hosting/) |
| NetPoa | Tanzania VPS from TZS 89,000/month; business email from TZS 60,000/year; WhatsApp Business API from TZS 20/message | Public landing-page starting prices; exact plan specs/fees require confirmation. [Source](https://netpoa.tz/) |
| reseller.co.tz | .tz domains from TZS 20,000/year; SMS from TZS 16/message | Reseller prices shown; check each TLD, registration/renewal parity and SMS route/segment. [Source](https://reseller.co.tz/) |
| Send | SMS TZS 20 down to TZS 10.7 per segment by prepaid top-up volume; WhatsApp TZS 100 per outbound message | Published Tanzania destination pricing before VAT; SMS segmentation changes chargeable units. [Source](https://send.co.tz/pricing/) |
| BLMPay | Business tier: mobile money 3.00%, cards 3.50%, dynamic QR 2.50%; payout fees separately tiered | Provider-published pricing; verify legal status, acquiring/settlement, payout schedule, reversals and full merchant agreement. [Source](https://pay.blmtec.co.tz/) |
| Twilio Tanzania SMS | USD 0.4336 per outbound SMS segment; carrier fees may apply | Global provider price is not directly comparable to domestic bulk SMS; check sender-ID and route capability. [Source](https://www.twilio.com/en-us/sms/pricing/tz) |
| Amazon SES | Essentials USD 0.16 per 1,000 emails for first published tier | Sending-only benchmark; include dedicated IP, add-ons, deliverability operations and support where applicable. [Source](https://aws.amazon.com/ses/pricing/) |
| Zoho Workplace | Public annual per-user plans displayed from approximately USD 1/user/month in plan comparison | Region, eligible edition, annual term and local taxes matter. [Source](https://www.zoho.com/workplace/plan-comparison.html) |
| Supabase | Free: 500 MB database, 5 GB egress, 1 GB file storage; Pro from USD 25/month | Includes limits and project/compute rules; do not equate with a dedicated managed DB SKU. [Source](https://supabase.com/pricing) |
| Cloudflare | Pro website plan USD 20/month billed annually or USD 25 monthly; R2 standard storage USD 0.015/GB-month with 10 GB-month free; Workers paid plan and usage rates published | Different products and billing units; storage operations and compute must be costed separately. [Source](https://www.cloudflare.com/plans/) |
| Grafana Cloud | Free telemetry/observability tiers; Pro application observability starts at USD 0.025/host-hour with a USD 19 platform fee in the published plan | Usage and telemetry dimensions matter; free allowances are not unlimited. [Source](https://grafana.com/pricing/) |

## 4. Category-by-category competitive pricing and monetization matrix

**Interpretation:** “TEKORA target approach” is a pricing hypothesis, not a numeric quote. Where a comparable and defensible public benchmark exists, the matrix identifies the benchmark. Where it does not, the product is quote-based or cost-plus until evidence is obtained.

| # / Category | Main chargeable SKUs and units | Public benchmark evidence found | Recommended TEKORA approach | Free / entry path | Evidence status / critical gate |
|---|---|---|---|---|---|
| 01. Domains, DNS & Internet Services | Domain-year by TLD; registration/renewal/transfer; DNS zone/month; query volume; DNSSEC/managed DNS; IP/egress | .tz reseller from TZS 20,000/year; domain TLD-specific pricing. [reseller.co.tz](https://reseller.co.tz/) | Price each TLD separately; compare registry + registrar wholesale + ICANN/registry fees + FX + support. Aim 3–8% below a like-for-like local retail offer only if authorized and profitable. DNS may be freemium; premium DNS by zone/features/queries. | Free managed subdomain for eligible developers; basic DNS for owned/managed domains; paid custom domains and premium DNS. | E1. TCRA/accredited registrar or authorized reseller route, registry costs, renewal pricing and suffix ownership need E3–E5. |
| 02. Web Hosting, Application Hosting & Compute | Shared hosting/site-month; WordPress; app runtime; VPS vCPU/RAM/storage/traffic-month; managed operations; backup; migration | Shared hosting from TZS 5,500/month billed annually; managed VPS 4 vCPU/4 GB/80 GB at TZS 34,500/month. [Hi-Tech shared](https://hitechwebhosting.com/tz/shared-hosting/) · [Managed VPS](https://hitechwebhosting.com/tz/managed-vps/) | Compare exact CPU, RAM, NVMe, traffic, backup, management and support. Use tiered bundles; do not advertise “unlimited” if resource policies are capped. Separate managed support and backups. | Time-limited or quota-limited static hosting / developer preview; no unrestricted free VPS. | E1. Need provider wholesale quotes, resource contention policy, backup/egress cost, abuse controls and support cost. |
| 03. Cloud Infrastructure & Virtualization | VM instance-hour/month; CPU/RAM; network egress; IP; managed cloud; private cloud; virtualization host | NetPoa Tanzania VPS from TZS 89,000/month; Cloudflare and global cloud providers publish metered components. [NetPoa](https://netpoa.tz/) · [Cloudflare](https://www.cloudflare.com/plans/) | Price compute by resource class and region; show estimated monthly cost and egress separately. Offer local managed bundles only after capacity and data-location claims are verified. | Small sandbox credits with expiry and hard budgets; no persistent unlimited free compute. | E1. Region, hardware, power, redundancy, FX, egress, provider contract and failover costs need validation. |
| 04. Containers, Kubernetes & Runtime | Cluster control-plane/month; node-hour; vCPU/RAM; pod/runtime; registry GB; build minutes; egress; support | Cloudflare Workers publishes free and metered request/CPU/container units. [Cloudflare pricing](https://www.cloudflare.com/plans/) | Distinguish managed Kubernetes control plane, worker nodes, registry, build/deploy and support. Bundle baseline then meter overages with spend caps. | Limited build minutes and preview deployment; cluster resources are paid/credits. | E1 partial. Kubernetes provider/region, node pricing, control-plane fees, network and on-call support require quotes. |
| 05. Networking & Connectivity | Site/month; bandwidth Mbps; GB transfer; tunnel/site; managed router/firewall; IP; installation; SLA/support | No sufficiently normalized Tanzania public enterprise connectivity tariff captured in this pass. | Quote by site, access technology, bandwidth, contention, installation, CPE, redundancy and SLA. Resell only with operator authorization and transparent last-mile ownership. | Network assessment or limited lab simulator; connectivity itself paid. | NEEDS QUOTE / E3–E5. TCRA/operator authorization, coverage, installation and uptime evidence. |
| 06. Database Services | DB instance-hour/month; vCPU/RAM; storage GB-month; IOPS; backup/PITR; connection/replica; support | Supabase Free 500 MB DB and 5 GB egress; Pro from USD 25/month; compute tiers separately listed. [Supabase](https://supabase.com/pricing) | Provide small managed DB tiers with explicit storage, compute, backup retention, connection and egress. Separate DB compute from backup and data transfer. | Development DB with low storage, inactivity pause and no production SLA; upgrade when production needs arise. | E1. Need region/HA/backup/restore cost, data residency, noisy-neighbour controls and support. |
| 07. Storage, Backup & Disaster Recovery | GB-month/TB-month; request/operation; retrieval; egress; backup policy; retention; restore test; DR site | Cloudflare R2 standard USD 0.015/GB-month, 10 GB-month free; Backblaze B2 benchmark in earlier pricing research. [Cloudflare](https://www.cloudflare.com/plans/) | Separate hot/cool/archive tiers, API operations, retrieval and egress. Price backup by protected data + retention + restore support; DR by RPO/RTO tier. | Small object-storage allowance for dev/test; backup trial with limited retention. | E1. Validate data durability, region, lifecycle, restore throughput, egress and recovery commitments. |
| 08. Email Infrastructure | Mailbox/user/month; storage; outbound email/1,000; dedicated IP/month; domain authentication; migration; deliverability support | Zoho Workplace public annual plans from approx USD 1/user/month; SES USD 0.16/1,000 outbound emails. [Zoho](https://www.zoho.com/workplace/plan-comparison.html) · [SES](https://aws.amazon.com/ses/pricing/) | Split business mailbox hosting from transactional email delivery. Meter mailboxes per user; outbound by message/volume and reputation management separately. | Limited test mailbox or low-volume transactional sandbox; no free mass outbound email. | E1. Sender reputation, spam controls, abuse, deliverability, local tax, support and provider reseller terms. |
| 09. SMS, Voice & Omnichannel Communication | SMS segment; WhatsApp message/template/conversation category; voice minute; phone number/month; email; push; RCS; verification | Send: TZS 20 down to TZS 10.7/SMS by top-up, before VAT; WhatsApp TZS 100/outbound. reseller.co.tz SMS from TZS 16. Twilio Tanzania SMS USD 0.4336/segment. [Send](https://send.co.tz/pricing/) · [reseller.co.tz](https://reseller.co.tz/) · [Twilio](https://www.twilio.com/en-us/sms/pricing/tz) | Use local route cost + carrier fees + sender-ID + platform fee. Tier volume with prepaid credits; price by actual segments and channel-specific rules. Separate campaign, OTP and transactional use cases. | Small verified sandbox/test credits; live traffic is paid. | E1. Sender-ID approval, opt-in/consent, delivery receipts, carrier route and anti-fraud. Twilio route restrictions must be checked. |
| 10. Payment Infrastructure, Billing & Fintech Integrations | Successful transaction % + fixed fee; payout; refund; chargeback; reconciliation; control-number collection; API/merchant/month | BLMPay published Business tier 3% mobile money, 3.5% card, 2.5% QR plus payout fees. [BLMPay](https://pay.blmtec.co.tz/) | Do not set a gateway fee until licensed provider, acquiring cost, payout, settlement, reversals, tax and legal role are verified. Separate provider pass-through and TEKORA service fee. | Sandbox only; test transactions with no real money. | E1. Critical E3–E5 gate: BoT classification, provider license/contract, merchant onboarding, control-number pathway, custody/settlement, reconciliation. |
| 11. Developer Tools & API Infrastructure | API request/1k or 1M; API key/project; webhook delivery; log retention; build minutes; seats; sandbox usage | Cloudflare Workers usage pricing; Supabase API included request policy; GitHub Copilot and other dev tools have public free/paid tiers (see official plan pages). [Cloudflare](https://www.cloudflare.com/plans/) · [Supabase](https://supabase.com/pricing) | Free developer tier with hard rate limits; paid tiers by requests, seats, retention, environments and premium support. Charge for high-cost compute/egress separately. | Free docs, API explorer and limited sandbox quotas; production API calls may be metered. | E1 partial. Need per-request infrastructure cost, abuse/rate limiting, API support burden and fair-use definitions. |
| 12. Software Development, DevOps & Deployment | Project/engagement; engineer-day/hour; milestone; CI minutes; runner size; deployment/environment; managed release retainer | Public software-engineering projects are commonly quote-based; CI/cloud build usage varies by provider. | Fixed-scope discovery and milestone quotes; time-and-materials with caps; monthly managed DevOps retainer. Clearly separate professional services from product subscriptions. | Free consultation/discovery call with bounded duration; paid implementation and ongoing operations. | NEEDS QUOTE. Scope, acceptance, change control, IP, warranty, support and delivery capacity. |
| 13. Cybersecurity & Information Security | Assessment scope; asset/endpoint/month; log GB; scan; penetration-test engagement; incident response retainer; training/seat | Cloudflare publishes website security plan tiers; broader professional security work is quote-based. [Cloudflare plans](https://www.cloudflare.com/plans/) | Quote assessments by authorized scope/assets/depth; managed security by endpoint/log volume/coverage and response SLA. Never underprice incident response capacity. | Public security checklist or limited posture self-assessment; actual scans/testing are scoped and authorized. | E1 partial. Legal authorization, scope, qualified personnel, liability, evidence handling and incident escalation are mandatory. |
| 14. Monitoring, Observability & SRE | Host-hour; metric samples; log GB ingested/retained; trace spans; synthetic checks; alert/seat; on-call coverage | Grafana Cloud Free and Pro; application observability from USD 0.025/host-hour with USD 19 platform fee. [Grafana](https://grafana.com/pricing/) | Transparent usage-based pricing; distinguish ingestion, retention, cardinality, active hosts, alerting and SRE service. Include budget alerts and cardinality safeguards. | Small telemetry allowance and short retention; paid overage only after opt-in or clear cap behavior. | E1. Need ingestion/retention cost, noisy-neighbour controls, alert delivery and 24/7 staffing economics. |
| 15. AI, ML & Automation Infrastructure | Input/output tokens; model request; image/audio/video units; GPU-second/hour; vector GB; embedding; agent task; automation run | Provider APIs publish model-specific token and modality pricing; no single comparable rate applies. | Pass through model cost + transparent TEKORA orchestration fee; show per-model estimates, usage caps and per-project budgets. GPU/hosting by actual compute. | Small sandbox credits, low token limits and non-production models; paid usage beyond allowance. | NEEDS CURRENT MODEL-SPECIFIC QUOTES. Recheck official provider price sheets per model/version/region and include safety/monitoring costs. |
| 16. Media, Video & Realtime Infrastructure | Participant-minute; egress GB; recording minute/GB; transcoding minute; stream viewer-minute; storage; CDN | Cloudflare pricing includes RealtimeKit participant-minute and export-minute rates in published plans; R2 storage/operations separately. [Cloudflare](https://www.cloudflare.com/plans/) | Price realtime by participant-minute and egress, recording/transcoding separately, storage by GB-month. Set concurrency, bitrate and recording caps. | Limited developer test minutes; live/recording production usage is paid. | E1 partial. Need actual SFU/CDN region costs, TURN, recording pipeline, egress, retention and moderation. |
| 17. Data Engineering & Analytics | Data GB ingested/processed; pipeline run; query TB scanned; warehouse compute-hour; dashboard seat; retention | Cloudflare Basin publishes pipeline transform/delivery and SQL scan units; Supabase/Grafana provide adjacent database/observability benchmarks. [Cloudflare](https://www.cloudflare.com/plans/) · [Grafana](https://grafana.com/pricing/) | Meter ingestion, transformations, compute, storage, query scans and egress separately; quote complex data platform engineering. | Small sample dataset and low monthly query/ingestion cap; paid production scale. | E1 partial. Need workload profiles, query cost models, data governance and retention. |
| 18. Business Applications & Digital Productivity | User/seat/month; module/month; workflow/run; storage; integration; onboarding; support | Zoho Workplace annual plans approx USD 1+ per user/month provide productivity-suite reference. [Zoho](https://www.zoho.com/workplace/plan-comparison.html) | Per-seat base with optional modules and implementation/onboarding. Avoid bundling licenses without reseller authorization and tenant administration costs. | Free personal/basic tier or time-limited pilot; advanced collaboration, automation and support paid. | E1. Validate licensing rights, region, user minimums, data protection and support obligations. |
| 19. IT Consulting, Managed IT & Professional Services | Engineer-hour/day; site/device/month; service desk seat; SLA tier; project milestone; travel/onsite | Publicly comparable enterprise managed-service rates not sufficiently normalized in this research pass. | Quote by deliverables, asset count, coverage hours, response/resolution targets, onsite travel and complexity. Use minimum monthly retainers for managed services. | Initial short discovery call; paid assessment, implementation and ongoing support. | NEEDS QUOTE. Staffing, geography, SLA capacity, liability, subcontractors and service scope. |
| 20. IoT, Smart Systems & Connected Infrastructure | Device/month; SIM/data MB/GB; message/event; gateway; cloud ingestion; device management; installation/support | No comparable Tanzania device + connectivity + cloud tariff validated in this pass. | Separate hardware, connectivity, platform/device management, cloud storage and installation. Price per active device/month plus usage; project quote for deployment. | Limited device simulator / small development sandbox; live SIM/data and hardware are paid. | NEEDS QUOTE. Operator coverage, device certification, security lifecycle, hardware sourcing and field support. |
| 21. Digital Trust, Compliance & Identity | Identity verification; authentication event; e-signature; certificate/year; KYC check; audit/retention; compliance advisory | No directly comparable locally approved price set validated in this pass; some component providers price per verification/API call. | Price each verification/check per successful/attempted event according to supplier billing; quote advisory and compliance readiness by scope. Never imply certification or legal attestation. | Developer sandbox/test identities only; real verification and certificates are paid. | NEEDS E3–E5. Data protection, identity provider contracts, consent, data residency, liability and regulator acceptance. |
| 22. Licensing, Software Distribution & Digital Products | License/user/year; subscription/month; activation; seat; renewal; support; reseller margin | Zoho Workplace is a public productivity licensing benchmark; other vendors publish region-specific partner price lists. [Zoho](https://www.zoho.com/workplace/plan-comparison.html) | Authorized reseller/partner pricing only; disclose vendor license vs TEKORA support/management. Quote products with restricted territory or unpublished partner discounts. | Free/open-source discovery and evaluation where license permits; trials only within vendor terms. | E1 partial. Vendor authorization, territory, tax, renewal, audit, software license terms and anti-piracy controls. |

## 5. Cross-category free-to-paid model

Free is an acquisition and developer-adoption mechanism, not a promise that every service is free. Select the model by marginal cost, abuse exposure, customer value and operational burden.

| Model | Appropriate use | Required controls |
|---|---|---|
| Free Forever | Documentation, public API explorer, limited DNS tools, basic status pages, basic developer profile | Sustainable limits, no implied SLA, abuse prevention |
| Freemium | Developer tools, limited DB/storage, monitoring, business productivity | Explicit quota, upgrade path, quota notifications and spend controls |
| Trial | Managed hosting, business email, paid software modules | Duration, eligible customer, end date, data export and explicit paid opt-in |
| Promotional Credits | Cloud, AI, storage, media, API usage | Credit expiry, eligible SKUs, per-account limits, fraud detection, no cash value |
| Sandbox | Payments, identity, SMS/voice test APIs, webhook testing | No real funds/messages/identity decisions; test data and separate credentials |
| Pay-as-you-go | SMS, email, API, AI, storage operations, data transfer | Usage metering, idempotency, spend alerts, caps, dispute evidence |
| Subscription | Hosting, managed DB, email seats, managed IT, software licenses | Renewal disclosure, proration, cancellation, failed-payment handling |
| Quote / Contract | Connectivity, cybersecurity engagements, enterprise cloud, consulting, IoT deployments | Scope, acceptance, SLA, legal and commercial approval |

**Mandatory conversion rules**
1. No silent paid conversion when a free trial expires. Require explicit consent and a valid payment/contract mandate.
2. At quota exhaustion, apply the published behavior: block, pause, throttle or request an upgrade. Never silently incur overage.
3. Warn customers before reaching 50%, 80% and 100% of a quota where technically appropriate.
4. Provide per-project and organization budgets, hard caps, usage export and alerts for variable-cost services.
5. Free-tier abuse, multiple-account farming, phishing, spam, crypto-mining and resource exhaustion must be addressed in policy and operations.
6. State what is excluded: SLA, support response, backup, custom domain, outbound email, production workloads or data retention.
7. Preserve data export and fair deletion/grace periods when free resources are suspended or expire.

## 6. Price construction and approval workflow

For cost (C) and target gross margin (m), the minimum selling price before tax is:

[
P_{floor} = \frac{C}{1-m}
]

Do not use (C \times (1+m)) as a gross-margin formula. Fully loaded cost must include:
- supplier wholesale charge and minimum commitment;
- FX spread and currency conversion;
- taxes and non-recoverable duties;
- payment collection, payout and settlement fees;
- network, compute, storage, backup, egress and third-party API usage;
- support, onboarding, migration and incident response;
- fraud, refunds, chargebacks, failed provisioning and bad debt;
- partner share, licensing and operational overhead;
- capacity reserve and risk buffer.

**Approval sequence:** competitor evidence → normalized SKU comparison → written provider quote → FX/tax inputs → unit-economics simulation → margin floor → legal/commercial review → finance approval → product owner approval → effective-dated price book → customer notice → invoice/quote regression tests.

A discount is valid only if the final price remains above the approved floor and all terms remain comparable. The 3–8% undercut is a hypothesis to test, not a mandatory setting.

## 7. Mandatory benchmark record for each SKU

Each benchmark record must contain:
- `benchmark_id`, source provider, source URL, captured_at, reviewer and evidence grade;
- product/SKU, exact specification, geography/region, currency, billing interval and commitment;
- list price, renewal price, introductory discount, included quota and overage;
- tax status, payment/payout fees, setup fees, minimum commitment and cancellation terms;
- support tier, SLA, backup/retention, bandwidth/egress and exclusions;
- FX rate/date if normalized to TZS, normalization formula and confidence;
- supplier quote reference and validity date (where available);
- TEKORA target range, fully loaded cost, gross margin and contribution margin;
- decision status: PROPOSED, NEEDS QUOTE, NEEDS LEGAL REVIEW, APPROVED or REJECTED.

Public webpages can change. Re-capture and timestamp before a price is approved or published.

## 8. Initial category launch sequencing hypothesis

This is a discovery prioritization hypothesis, not authorization to sell:
- **Potential early, lower-complexity validation:** domains/DNS through authorized route, shared hosting/reseller hosting, business email, SMS/API through validated local provider, developer sandbox, limited observability.
- **Provider-dependent / stronger controls:** VPS/cloud, databases, storage/backup, container runtime, transactional email, AI APIs, realtime media.
- **High regulatory / operational / quote complexity:** payment orchestration and control numbers, connectivity, cybersecurity services, managed IT/SRE, IoT, digital identity/compliance, enterprise licensing.

Score each candidate with customer demand, margin, technical readiness, provider evidence, legal eligibility, support capacity, security exposure and integration leverage. Do not choose MVP solely by the cheapest advertised competitor price.

## 9. Open decisions and blockers

| Decision | Status | Required evidence |
|---|---|---|
| 3–8% undercut policy | PROPOSED | SKU-specific economics and controlled market tests |
| TEKORA target gross/contribution margin by category | PENDING | Supplier quotes, overhead allocation and finance approval |
| Free quota and expiry for each product | PENDING | Cost modelling, abuse rates, support capacity |
| Tanzania TZS pricing and tax display | PENDING | Tax advice, settlement route, invoice/EFD requirements |
| .tz domain reseller route | NEEDS VERIFICATION | TCRA/registry eligibility, registrar contract and wholesale schedule |
| Payment fees and control-number charges | BLOCKED | BoT legal classification, licensed provider contract, settlement and payout schedule |
| SMS/WhatsApp sender and route pricing | NEEDS VERIFICATION | Sender ID approval, carrier route, provider quote, consent rules |
| Cloud/AI/Media regions and supplier rates | NEEDS QUOTE | Written region-specific commercial offer and usage-cost model |
| Consulting/security/IoT rates | NEEDS QUOTE | Scope templates, staffing cost, liability and service capacity |

## 10. Research sources

Local / Tanzania:
- [Hi-Tech Hosting — shared hosting](https://hitechwebhosting.com/tz/shared-hosting/)
- [Hi-Tech Hosting — managed VPS](https://hitechwebhosting.com/tz/managed-vps/)
- [NetPoa](https://netpoa.tz/)
- [reseller.co.tz](https://reseller.co.tz/)
- [Send — Tanzania SMS and WhatsApp pricing](https://send.co.tz/pricing/)
- [BLMPay — Tanzania payment gateway pricing](https://pay.blmtec.co.tz/)
- [Twilio — Tanzania SMS pricing](https://www.twilio.com/en-us/sms/pricing/tz)

International:
- [Supabase pricing](https://supabase.com/pricing)
- [Cloudflare plans and usage pricing](https://www.cloudflare.com/plans/)
- [Amazon SES pricing](https://aws.amazon.com/ses/pricing/)
- [Zoho Workplace plan comparison](https://www.zoho.com/workplace/plan-comparison.html)
- [Grafana Cloud pricing](https://grafana.com/pricing/)

Earlier pricing research remains in [2026-11-26 Pricing & Monetization Research](reports/2026-11-26-PRICING-MONETIZATION-RESEARCH.md). Additional provider research is required for all category-specific SKUs before approval.

## 11. Acceptance criteria

- All 22 categories have chargeable units, free/entry model, paid path and guardrails.
- Every proposed launch SKU has at least 3–5 normalized comparables where the market has public alternatives; otherwise the reason for quote-based pricing is recorded.
- At least one local and one international source are considered where relevant; local source takes precedence for Tanzania market positioning.
- Supplier costs and terms are evidenced independently from public competitor retail prices.
- Currency, FX date, VAT/tax status, billing unit, renewal and included allowances are explicit.
- Every price passes fully loaded cost and approved margin-floor simulation.
- Free quotas, trial expiry, overage and paid conversion are explicit and tested.
- Price changes are versioned, approved, auditable and customer-notified.
- Quote, invoice, subscription, usage and refund tests preserve historical price snapshots.
- No category is marked commercially ready solely because a public competitor price was found.

**Overall outcome: PARTIAL.** A first-pass, 22-category benchmark and monetization matrix is documented. Several categories have credible public price anchors; multiple categories remain quote-based or require supplier, legal and operational validation. No TEKORA final retail price, provider partnership, legal eligibility or launch readiness is asserted.
