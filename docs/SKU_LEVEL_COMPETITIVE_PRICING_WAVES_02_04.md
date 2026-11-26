# TEKORA SKU-Level Competitive Pricing Analysis — Waves 02–04 (Categories 03–22)

**Snapshot:** 26 November 2026  
**Status:** PARTIAL / DISCOVERY — provisional models; no TEKORA retail prices approved.  
**Currency:** TZS-first for Tanzania; foreign provider prices must be normalized using a dated FX source before a decision.

This expands Wave 01 to the remaining 20 categories in the 22-category scope. Where public comparable rates are insufficient, we define billable units, a quote/procurement path, an indicative packaging model and a launch gate instead of fabricating competitor prices.

## Pricing discipline (applies to all rows)

- The earlier 3–8% undercut is a conditional hypothesis only, applied to equivalent offers with validated cost and margin.
- Prices must be built from provider costs, FX, taxes, collection/payout fees, infrastructure, support, security, incident handling, fraud/refunds, partner margin and overhead.
- Price floor for gross margin m: (P=C/(1-m)). The cost definition must be fully loaded.
- Free tiers are bounded, have no hidden overage, no silent conversion and no production SLA unless expressly funded.
- Provider retail price is not TEKORA wholesale cost; vendor price does not imply resale permission.
- For quoted services, use a scoped quote and approval rather than invented public pricing.
- Tax and EFD/invoicing treatment, customer contract, provider authorization and local regulatory classification must be reviewed before publication.

## Category 03 — Cloud Infrastructure & Virtualization

### SKU families and billable units
| SKU family | Unit / dimensions | Monetization approach | Free entry | Gate |
|---|---|---|---|---|
| Cloud VM | instance-hour/month; vCPU; RAM; OS; region | Resource bundles + hourly usage, optional commitment discount | Sandbox credit, small cap | Region/cost/reseller agreement |
| Bare metal / dedicated server | server-month, setup, bandwidth, IP, hardware lifecycle | Quote; transparent installation/term/renewal | None; assessment | Hardware, colo, support, liability |
| Private cloud | cluster/node-month, storage, support, SLA | Quote with sizing and HA tiers | Architecture workshop | Capacity, RPO/RTO, SLA |
| GPU compute | GPU-hour, VRAM class, CPU/RAM, storage, egress | Metered or reservation | Small trial credits only | GPU supply, power, abuse and cost |
| Cloud IP / networking | IP-month, bandwidth/egress, VPN/tunnel | Separate metered SKU | Limited test | Provider terms, IPv4 scarcity |

### Public Tanzania anchor
Lineserve public cloud-server starting price reported at TZS 29,700/month for a configurable 1 vCPU, 1 GB RAM, 20 GB SSD, one IPv4 build; Linux VPS starts at TZS 32,400/month. This is an E1 benchmark, not an apples-to-apples quote. Source: [Lineserve](https://www.lineserve.co.tz/).

**TEKORA:** do not set fixed target prices for arbitrary cloud builds until exact CPU/RAM/storage/traffic/region/IPv4 costs are mapped. Use a cost calculator, transparent monthly estimate and budget caps. Dedicated and GPU resources quote or metered with advance budget controls.

## Category 04 — Containers, Kubernetes & Runtime

| SKU | Unit | Pricing model / proposed packaging | Free entry / guardrails |
|---|---|---|---|
| Managed Kubernetes control plane | cluster-month, HA tier | Basic and HA control-plane fee | Sandbox cluster; no production SLA |
| Worker node pool | vCPU/RAM/storage/node-hour | Metered compute bundles | Hard cap; node costs paid |
| Persistent volume | GB-month, IOPS | Storage tier + backup | Limited ephemeral storage |
| Container registry | GB-month, request, retention | Included quota then metered | Low storage quota |
| CI build runners | build-minute, runner class | Included monthly allowance + overage only opted-in | Free build-minute allowance |
| Runtime/edge functions | invocation, CPU-ms, memory, egress | usage tiers with capped spend | Limited requests/runtime |
| Deployment support | project, engineer-hour, retainer | Quote / managed tier | Documentation and sandbox |

### Local benchmark
Lineserve publicly lists Kubernetes control-plane launch pricing: Basic TZS 55,720/month plus worker resources; fault-tolerant 3-master option TZS 232,680/month plus resources. Worker-resource public rates include vCPU TZS 13,320/month, RAM TZS 6,120/GB-month, local disk TZS 380/GB-month, public IP TZS 3,000/month and Basic LB TZS 32,760/month. These are E1 observations and are subject to provider launch pricing, capacity and terms. Source: [Lineserve Kubernetes](https://www.lineserve.co.tz/kubernetes).

**TEKORA:** treat the control-plane fee and workers as separate SKUs; quote a minimum viable dev cluster and HA production cluster. Do not discount node resources without verified supplier economics.

## Category 05 — Networking & Connectivity

| SKU | Unit / quote basis | Pricing approach | Gate |
|---|---|---|---|
| Dedicated internet | Mbps, site/month, installation | Quote per site, bandwidth, contention, last-mile, SLA | Licensed operator/coverage |
| Business broadband | connection/month, installation, router | Authorized reseller bundle | Operator contract and coverage |
| Managed Wi-Fi | AP/device/month, site, installation | Hardware + setup + support retainer | Site survey and hardware |
| SD-WAN | site/month, bandwidth, device | Bundle + usage/contract | Provider network and SLA |
| VPN / secure access | user/site/month | Seat/site tier | Security, support, provider |
| Firewall appliance/service | device/month, throughput, license | Hardware + license + managed fee | Product licensing and scope |
| IP addresses | IP/month, allocation | Pass-through plus handling only where lawful | Provider terms |
| Network audit/design | engineer-day / site | Quote | Scope, travel and deliverables |

**Benchmark status:** no sufficiently normalized Tanzania enterprise connectivity tariff was established in this wave. Quote-based until operator tariffs, installation, coverage, contention, SLA, equipment and reseller authority are confirmed. Public competitors include connectivity and managed network services, but landing-page claims are not a price comparable. Source context: [ComNet](https://www.comnet.co.tz/).

## Category 06 — Database Services

| SKU | Unit | Target pricing structure | Free path |
|---|---|---|---|
| Managed PostgreSQL/MySQL | instance-hour/month, vCPU, RAM | Compute tiers + storage | Development tier with pause and quota |
| Database storage | GB-month | Separate storage allocation | Included low allowance |
| Backups/PITR | GB-month, retention days | Retention tier and backup storage | Short retention |
| Read replica | replica-hour, region | Compute-priced | No free production replica |
| Managed Redis/cache | node-hour, memory GB | Memory tiers + HA | Small ephemeral cache |
| NoSQL/managed document DB | throughput, storage, request | Metered with caps | Low request allowance |
| DB migration | database/GB, engineer-hour | Quote or fixed migration SKU | Migration checklist |

**Benchmark anchors:** Supabase public Free includes small DB/storage/egress allowances and Pro starts at USD 25/month; Prisma Postgres public tiers are an adjacent benchmark. They are not equivalent managed-database offers and need spec normalization. Source: [Supabase](https://supabase.com/pricing), [Prisma](https://www.prisma.io/pricing).

**TEKORA:** publish DB tier matrix only after sizing baseline, HA, backup, restore, region, connection limits and support are priced. Charge compute, storage, backup and egress separately where costs differ.

## Category 07 — Storage, Backup & Disaster Recovery

| SKU | Unit | Pricing model | Guardrails |
|---|---|---|---|
| Object storage | GB-month, API operations | Storage tier + operations | Free cap and lifecycle |
| Block volume | GB-month, IOPS | Performance tier | Snapshots separately |
| File storage | GB-month, throughput | Tiered | Usage caps |
| Backup | protected GB-month, retention | Data size + retention tier | Encryption and restore tests |
| Snapshot | GB-month | Snapshot storage | Explicit expiry |
| Archive | GB-month, retrieval | Low storage + retrieval/restore fees | Retrieval-time disclosure |
| DR replication | protected system/month, transfer | RPO/RTO tiers and replicated storage | Tested recovery, no implied SLA |
| Restore assistance | restore event, engineer-hour | Quote/incident fee | Terms and priority tier |

**Benchmark:** Cloudflare R2 publicly lists standard storage USD 0.015/GB-month with 10 GB-month free and operations billed by class; Backblaze B2 pricing is an adjacent benchmark. Validate live price sheets, region, minimums and egress before quote. Sources: [Cloudflare R2](https://www.cloudflare.com/products/r2/), [Backblaze B2](https://www.backblaze.com/cloud-storage/pricing).

**TEKORA:** don't price backup as merely “storage.” Cost restoration, retention, versioning, encryption, replication, monitoring, support, and recovery testing.

## Category 08 — Email Infrastructure

| SKU | Unit | Pricing model | Free entry |
|---|---|---|---|
| Business mailbox | user/month, storage | Seat tiers and storage quota | Trial or limited test mailbox |
| Mail storage expansion | GB/user-month | Add-on | No unlimited |
| Transactional email | 1,000 accepted sends, reputation tier | Usage + provider pass-through | Sandbox/test-only |
| Bulk email | delivered/accepted volume, sender reputation | Tiered, opt-in, abuse control | No free bulk production |
| Dedicated IP | IP-month, warmup service | Add-on/quote | None |
| Migration | mailbox, GB, engineer-hour | Fixed scope or quote | Assessment |
| DNS/email security setup | domain, configuration | Setup fee/managed add-on | Self-serve guides |

**Benchmarks:** Zoho Workplace public plans vary by regional price and annual term; Amazon SES is a sending-service cost anchor. Verify region, currency, tax, dedicated IP, provider restrictions and send limits. Sources: [Zoho](https://www.zoho.com/workplace/pricing.html), [Amazon SES](https://aws.amazon.com/ses/pricing/).

**TEKORA:** separate mailbox hosting from sending API; model spam filtering, migration, support, storage, reputation and abuse. No mass-mail free tier.

## Category 10 — Payment Infrastructure, Billing & Fintech Integrations

| SKU | Billable unit | Monetization | Gate |
|---|---|---|---|
| Gateway integration | successful transaction %, fixed fee | Provider pass-through + transparent TEKORA fee only if permitted | BoT/legal/provider |
| Payment collection API | API/service subscription | Quote or subscription | License classification |
| Control-number collection | collected amount/fee per payment | Only agreed provider fee; no invented surcharge | Provider/regulatory |
| Subscription billing | account/month, invoice, collection | SaaS fee | Contract, tax, consent |
| Reconciliation | transaction/batch/month | Enterprise tier or quote | Data access and accuracy |
| Payout/settlement | payout or transaction | Provider fee disclosed | Licensed partner |
| Refund/chargeback | event fee | Pass-through per provider terms | Consumer and provider rules |
| Sandbox | test event | Free capped test | No real money |

**Benchmark:** BLMPay public fee schedule is a price anchor only. TEKORA must not receive/custody/route funds or make payment-provider claims without legal classification, licensed provider contract, settlement design and required approvals. Payment/control-number pricing remains blocked.

## Category 11 — Developer Tools & API Infrastructure

| SKU | Unit | Pricing model | Free path |
|---|---|---|---|
| API gateway | requests/1k, project, bandwidth | Free cap + metered tiers | Sandbox requests |
| API keys/identity | key/project/seat | Included tiers or paid admin features | Limited |
| Webhook delivery | event delivery, retries, logs | Included quota then usage | Sandbox |
| Secrets vault | secret/month, API operations | Tiered | Small dev cap |
| SDK/tooling | seat/project | Premium support/integration tiers | Core tools free |
| Developer portal | org/seat | Free portal + premium org features | Public docs |
| Rate-limit tiers | requests/minute and daily quota | subscription/usage | Safe caps |

**TEKORA:** publish rate limits, event delivery semantics, retention, retry policy, latency expectations and spend limits. Price only after request cost and support burden are measured.

## Category 12 — Software Development, DevOps & Deployment

| SKU | Unit / scope | Pricing approach |
|---|---|---|
| Discovery / architecture | workshop/day, written deliverable | Fixed scope |
| Web/mobile software | project milestone, engineer-day | Estimate with change-control |
| CI/CD setup | pipeline/project | Fixed setup or scoped quote |
| Deployment/release | release/project | Fixed scope |
| Managed DevOps | month, coverage/SLA | Retainer |
| CI runner usage | build-minute/runner | Metered provider pass-through |
| Migration/modernization | system, project, engineer-day | Quote |
| Maintenance | month, incident/support tier | Retainer |

**Benchmark status:** public comparable rates are not normalized. Avoid artificial hourly list prices. Use transparent discovery, milestone, scope, acceptance, warranty, IP and change-control terms. No free implementation beyond clearly bounded discovery.

## Category 13 — Cybersecurity & Information Security

| SKU | Unit | Pricing approach | Gate |
|---|---|---|---|
| Vulnerability assessment | scope/assets, engagement | Quote | Written authorization |
| Penetration testing | scoped assets/test days | Quote | Rules of engagement |
| Security hardening | server/site/device | Fixed scope | Baseline and rollback |
| Managed endpoint | device/month | Seat tier | Vendor license and incident capacity |
| WAF/security service | site/month, requests | Pass-through + managed fee | Provider contract |
| SIEM/logging | GB/day, retention, assets | Usage tiers | Data handling |
| Incident response | retainer/hour/event | Retainer + scoped emergency fee | 24/7 capacity, liability |
| Awareness training | seat/session | per seat or session | Materials and privacy |
| Compliance readiness | scope, day, deliverables | Quote | No implied certification |

**TEKORA:** free public security checklists or self-assessment only; security tests require written permission and scope. Never price or promise incident response SLA before staffing and legal liability are established.

## Category 14 — Monitoring, Observability & SRE

| SKU | Unit | Model |
|---|---|---|
| Metrics | active host, sample volume | Tiered usage |
| Logs | GB ingested/retained | Ingestion + retention |
| Traces | spans/GB | Usage tiers |
| Synthetic checks | check/region/month | Included quota + tier |
| Alerting | alert, notification | Included and premium |
| SRE coverage | service/month, coverage hours | Retainer/quote |
| On-call | incident, coverage schedule | Contract tier |
| Dashboard | org/user | SaaS seat/module |

Grafana Cloud is a public benchmark, but provider limits and price units vary. Source: [Grafana](https://grafana.com/pricing/). Meter cardinality, retention and alert delivery. Free telemetry must have caps; 24/7 SRE is quote-based until capacity exists.

## Category 15 — AI, ML & Automation Infrastructure

| SKU | Unit | Pricing model | Controls |
|---|---|---|---|
| LLM API | input/output tokens by model | Provider cost + disclosed platform fee | Per-project budgets |
| Embeddings | tokens/vector | Metered | Caps |
| AI image | image/size/quality | Model-specific | Quotas |
| Speech/audio | audio minute/token | Model-specific | Limits |
| Video AI | minute, resolution | Quote/metered | Cost estimate |
| GPU inference | GPU-hour, memory | Reserved/usage | Idle shutdown |
| Fine-tuning | token, job, compute | Provider passthrough | Consent/data policy |
| Vector storage | GB-month, query | Metered | Usage caps |
| Agent workflow | run/task/tool | Costed orchestration | Budget, safety and audit |
| Automation | execution, step, seat | Tiered | Rate limits |

No generic price: rates are model/provider/version/region specific. Recheck official provider pricing immediately before approval; include retries, orchestration, safety, evaluation, storage and observability costs. Free sandbox credit is capped and expires transparently.

## Category 16 — Media, Video & Realtime Infrastructure

| SKU | Unit | Pricing model |
|---|---|---|
| Realtime video/audio | participant-minute, egress | Usage + provider fees |
| Recording | minute/GB | recording + storage |
| Transcoding | media-minute, resolution | Metered |
| Streaming/CDN | viewer-minute, GB | Usage |
| TURN relay | GB | Metered |
| Live session support | event/hour | Quote |
| Media storage | GB-month | Tiered |
| Moderation | asset/request | Provider pass-through |

Use a cost calculator before publishing. Participant-minutes, bitrate, relay traffic, recording, transcription, CDN, storage and moderation all have distinct cost drivers. Free developer minutes must be low and non-production.

## Category 17 — Data Engineering & Analytics

| SKU | Unit | Model |
|---|---|---|
| Data ingestion | GB/event | Usage tiers |
| ETL/ELT | job, compute-hour | Metered |
| Warehouse | compute-hour, TB scan | Usage |
| Data storage | GB-month | Tiered |
| Dashboard/report | seat/report | Subscription |
| Data quality | rule, run | Usage/retainer |
| Pipeline maintenance | month | Retainer |
| Analytics consulting | scope/project | Quote |

No normalized public Tanzania rates captured. Build estimates from supplier compute/storage costs and workload testing. Free tier uses sample datasets and strict caps; quote data architecture, migration and managed pipelines.

## Category 18 — Business Applications & Digital Productivity

| SKU | Unit | Model |
|---|---|---|
| Productivity license | user/month/year | Authorized reseller price + support |
| CRM/ERP module | seat/module/month | Subscription |
| Workflow automation | execution/seat | Tiered |
| Document signing | signature/event | Provider pass-through |
| Collaboration | user/month | License tiers |
| Business app setup | tenant/project | Fixed scope |
| Training | session/seat | Quote |
| Integration | system/API | Scope quote |

Zoho/Microsoft/other vendors publish region-specific plans; no resale price should be assumed without authorization and region-specific terms. Free evaluation subject to vendor terms, not TEKORA's unlimited license promise.

## Category 19 — IT Consulting, Managed IT & Professional Services

| SKU | Unit | Model |
|---|---|---|
| IT health assessment | site/day | Bounded discovery or quote |
| Service desk | device/user/month | Tiered with device minimum |
| Managed IT | site/month, device batch | Contracted retainer |
| Onsite support | visit/hour/day | Quote + travel |
| Network administration | site/month | Managed retainer |
| IT director advisory | month/hour | Retainer |
| Installation | device/site | Project quote |
| Training | session/seat | Quote |

Local competitor Wemanage publicly reports managed support starting at TZS 500,000/month for Assist (up to 20 devices, no server) and TZS 800,000/month for Manage (server or over 20 devices), minimum 10 devices and batches of 5. These are company-specific terms, not normalized TEKORA price comparables. Source: [Wemanage](https://wemanage.co.tz/).

TEKORA should define device tiers, coverage, remote/onsite, SLA, hours, travel, exclusions and minimum term. Do not claim 24/7 without staffing.

## Category 20 — IoT, Smart Systems & Connected Infrastructure

| SKU | Unit | Model |
|---|---|---|
| Device onboarding | device | Setup |
| IoT platform | active device/month | Tiered |
| Data ingestion | event/MB | Metered |
| SIM/connectivity | SIM/month, MB/GB | Provider passthrough |
| Gateway | device + install | Hardware + service |
| Device fleet management | device/month | Subscription |
| Monitoring | device/alert | Usage |
| IoT deployment | site/project | Quote |
| Maintenance | device/site/month | Retainer |

Pricing needs supplier quotes for hardware, SIM/operator, data, device certification, replacement, security updates, storage and field visits. Free simulator/dev sandbox only; no free live connectivity.

## Category 21 — Digital Trust, Compliance & Identity

| SKU | Unit | Model |
|---|---|---|
| Identity verification | check/event | Provider fee + disclosed service fee |
| OTP/authentication | message/check | Channel-specific usage |
| e-signature | signature/document | Provider license or usage |
| Certificate | certificate/year | Authorized provider terms |
| Access management | user/month | Subscription |
| Audit trail | record/storage | Tiered retention |
| Compliance advisory | scope/day | Quote |
| Privacy/data protection | assessment/project | Quote; no legal attestation claim |

Require PDPC/data protection, consent, purpose, retention, provider contracts, local law and security review. No identity/compliance service may be described as official certification unless TEKORA is legally authorized.

## Category 22 — Licensing, Software Distribution & Digital Products

| SKU | Unit | Model |
|---|---|---|
| SaaS license | seat/month/year | Authorized vendor pricing |
| Perpetual license | license/activation | Contract/territory specific |
| OS/server license | VM/server/user | License pass-through |
| Developer license | seat | Vendor terms |
| Digital templates/tools | item/license | Direct SKU price if rights held |
| Software support | month/seat | Managed add-on |
| Renewal | license/year | Explicit renewal price |
| Installation | tenant/system | Fixed scope |

Do not resell restricted licenses without partner authorization. Distinguish vendor price, TEKORA implementation, support, tax and renewal. Free/open-source items only where their license allows the distribution and service model.

## Cross-category target pricing / free policy

| Model | Suitable categories | Rules |
|---|---|---|
| Free forever | Docs, public API explorer, basic tools | Sustainable, bounded, no implied SLA |
| Freemium | Developer tools, limited DB/storage/monitoring | Clear quotas and pause/block rules |
| Trial | Hosting, email, business apps | End date and explicit paid opt-in |
| Credits | Cloud, AI, storage, media | Expiry, cap, abuse rules |
| Sandbox | Payments, messaging, identity | Test-only, separate credentials |
| Metered | SMS, AI, APIs, storage, data | Budget caps, notifications and clear units |
| Subscription | Hosting, managed DB, licenses, IT | Renewal, cancellation, support terms |
| Quote | Connectivity, security, consulting, IoT, enterprise | Scope, SLA, legal/commercial approvals |

## Public benchmark snapshot (E1, not approved pricing)

| Market reference | Observed pricing signal | TEKORA applicability |
|---|---|---|
| Lineserve cloud server | Configurable starting from TZS 29,700/month | Benchmark resource-bundle construction only |
| Lineserve managed Kubernetes | Basic TZS 55,720 control-plane/month plus workers; HA TZS 232,680 plus workers | Compare cluster management and node billing |
| Supabase | Free and Pro pricing tiers | DB/storage/egress normalization |
| Cloudflare R2 | Storage and operation-based pricing | Object storage cost basis |
| Zoho Workplace | Region/term-dependent per-user plans | Mailbox/productivity licensing |
| Amazon SES | Usage-based sending | Transactional email |
| Grafana Cloud | Usage/host and platform fee model | Observability units |
| Wemanage | Assist from TZS 500k/month; Manage from TZS 800k/month under stated device terms | Managed IT scope, not directly comparable |
| ComNet | Connectivity, cloud, security and managed IT; quote-led | Supplier/partner discovery only |

## Mandatory SKU research record and workflow

For every candidate SKU: benchmark ID, source provider/URL/date, country/region, spec, unit, price, billing term, promo vs renewal, quotas, overage, taxes, fees, SLA, support, backup, exclusions, evidence grade, FX/date, comparable rationale, supplier quote, TEKORA target, full cost, margin, approvals and status.

Workflow: normalize competitor evidence → request supplier quotes → validate technical service → calculate fully loaded cost → FX/tax review → margin floor → legal/commercial review → price owner approval → versioned price book → customer notice → quote/invoice/usage/refund tests.

## Open blockers and status

- Categories 03–08: pricing architecture documented; public anchors are partial; supplier quote and technical sizing gates remain.
- Category 10: BLOCKED for collection/custody/control-number fee or processing claims pending legal classification and licensed-provider arrangement.
- Category 13: service testing must be scoped and authorized; incident-response SLAs require staffing.
- Categories 15–16: model/provider/region-specific pricing and workload cost validation required.
- Categories 19–20: quote-based until staff, hardware, connectivity, coverage and operational costs are established.
- Category 21: legal, provider, data protection and certification authorization gates.
- Category 22: license/territory/reseller permission gate.
- All provisional target ranges in earlier wave documents are hypotheses; no final TEKORA price, tax, margin, quota or launch status is approved.

## Research sources

- [Lineserve Cloud / VPS](https://www.lineserve.co.tz/)
- [Lineserve Kubernetes](https://www.lineserve.co.tz/kubernetes)
- [ComNet Tanzania](https://www.comnet.co.tz/)
- [Supabase pricing](https://supabase.com/pricing)
- [Prisma pricing](https://www.prisma.io/pricing)
- [Cloudflare R2](https://www.cloudflare.com/products/r2/)
- [Backblaze B2](https://www.backblaze.com/cloud-storage/pricing)
- [Zoho Workplace](https://www.zoho.com/workplace/pricing.html)
- [Amazon SES](https://aws.amazon.com/ses/pricing/)
- [Grafana Cloud](https://grafana.com/pricing/)
- [Wemanage](https://wemanage.co.tz/)
- [Tanzania PDPC](https://pdpc.go.tz/)
- [Bank of Tanzania payment systems](https://www.bot.go.tz/PaymentSystem/regulations?lang=en)

## Outcome

**PARTIAL / DISCOVERY — all remaining categories 03–22 have SKU-level billing structures and monetization paths documented, but many lack normalized price comparables or supplier quotes.** Do not claim every SKU is commercially priced or ready for sale. All 22 categories are retained. Next step is obtaining written quotes and deeper 3–5 competitor comparisons per launch SKU wherever comparable public data exists.
