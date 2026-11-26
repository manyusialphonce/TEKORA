# Pricing & Monetization Strategy Research Report

**Date:** 26 November 2026  
**Repository:** manyusialphonce/TEKORA  
**Status:** STRATEGY AND CATEGORY COVERAGE ADDED; COMPETITOR RESEARCH PARTIAL; NO RETAIL PRICES APPROVED.

## 1. Objective

Add a mandatory platform-wide competitive pricing, free/freemium and monetization strategy for all 22 TEKORA service categories. User direction: research market prices, position TEKORA modestly below comparable competitors where viable (not necessarily for every product), and allow selected free products to remain free with a paid upgrade path when more capability is needed.

## 2. Changes committed

- Extended `docs/PRODUCT_CATALOGUE_SKU_PRICING_FRAMEWORK.md` with Section 9:
  - Competitive positioning and conditional 3–8% undercut hypothesis.
  - Public benchmark snapshot and source URLs.
  - Charging units and free/paid strategy for all 22 categories.
  - Free Forever, Freemium, Trial, Credits, Sandbox, Paid, Pay-as-you-go and Quote distinctions.
  - Free-tier hard limits, spend controls and explicit paid-conversion rules.
  - Competitor/provider evidence, COGS, FX, margin and price-floor algorithm.
  - Price-book/billing data model and finance/admin controls.
  - Tanzania regulatory/tax/provider validation requirements.
  - Free-to-paid package examples and acceptance criteria.
- Extended README, AGENTS, MASTER_IMPLEMENTATION_PROMPT, Master Platform Blueprint, Technical Decision Register and Implementation Execution Playbook to make pricing requirements mandatory across future implementation.

## 3. Public competitor benchmark observations

Snapshot date 26 November 2026. These are public advertised prices/allowances, not TEKORA wholesale costs or signed partner quotes.

| Category | Observed benchmark | Evidence |
|---|---|---|
| Tanzania VPS | Lineserve Linux 2 GB TZS 32,400/mo; 4 GB TZS 64,800; 8 GB TZS 129,600 | https://www.lineserve.co.tz/vps |
| Managed VPS Tanzania | Hi-Tech Hosting 4 GB/4 vCore/80 GB NVMe managed VPS TZS 34,500/mo | https://hitechwebhosting.com/tz/managed-vps |
| Tanzania domains | Sakurahost .co.tz TZS 19,500 registration / TZS 25,000 renewal; WazoHost TZS 22,000 new / TZS 25,000 renewal | https://www.sakurahost.co.tz/domains/ ; https://my.wazohost.co.tz/domain/pricing |
| Tanzania SMS | Send: TZS 20/SMS at low volume, volume tier down to TZS 10.7; before VAT | https://send.co.tz/pricing/ |
| Tanzania gateway | BLMPay published tiered percentage fees by verification level and method, plus payout fee schedule | https://pay.blmtec.co.tz/ |
| Managed DB | Supabase Free $0 (500 MB DB etc.); Pro from $25/mo; Prisma also publishes Free and paid usage tiers | https://supabase.com/pricing ; https://www.prisma.io/pricing |
| Object storage | Cloudflare R2 10 GB-month free then $0.015/GB-month; Backblaze B2 starts $6.95/TB/month subject to terms | https://www.cloudflare.com/products/r2/ ; https://www.backblaze.com/cloud-storage/pricing |
| Edge/serverless | Cloudflare Workers paid plan from $5/month with included usage and overage | https://developers.cloudflare.com/workers/platform/pricing/ |
| Hosting/deployment | Vercel publishes usage rates for functions, builds, requests, storage and seats | https://vercel.com/pricing |
| DNS | AWS Route 53 public hosted zones $0.50/zone/month for first 25 plus query rates | https://aws.amazon.com/route53/pricing/ |
| Business productivity | Zoho Workplace Africa/Middle East list and Microsoft 365 per-user tiers vary by product/commitment | https://www.zoho.com/workplace/pricing.html ; https://www.microsoft.com/en-us/microsoft-365/business/microsoft-365-plans-and-pricing |
| Transactional email | Amazon SES Essentials published $0.16 per 1,000 emails in first tier | https://aws.amazon.com/ses/pricing/ |
| Monitoring | Grafana Cloud has free allowances and usage-based pricing for metrics, hosts and logs | https://grafana.com/pricing/ ; https://grafana.com/products/cloud/logs/ |
| Developer tooling | GitHub Copilot has Free and paid tiers | https://github.com/features/copilot/plans |
| Cloud compute | AWS Lightsail fixed resource bundles vary by region/OS/transfer allowance | https://aws.amazon.com/lightsail/pricing/ |

TCRA's FAQ directs .tz registration to accredited registrars and the Karibu registry ecosystem. This means TEKORA must verify its own accreditation/partner route and wholesale terms before offering .tz registration: https://tcra.go.tz/faq ; https://www.karibu.tz/registrars.

## 4. Pricing policy added

- Initial hypothesis: target 3–8% below a genuinely comparable market price only where fully loaded costs, provider terms, quality, tax and margin floor allow.
- Do not use blanket discounting. Price parity or premium may be correct for differentiated local support, managed operations or stronger service.
- No final TEKORA retail prices, margins, free quotas or payment fees are approved yet.
- TZS is primary Tanzania market display/settlement currency when operationally supported.
- Every benchmark is dated and normalized; every SKU requires supplier cost, margin floor, tax treatment and approval.
- Free tiers must have explicit caps and safe end-of-limit behavior; no surprise overage or silent trial-to-paid conversion.
- Distinguish Free Forever, Freemium, Trial, Credits, Sandbox, Paid, Pay-as-you-go and Quote.

## 5. Coverage across all 22 categories

A category-by-category table now specifies primary billing units, free entry hypothesis, paid monetization and key guardrails for:
1 Domains/DNS/Internet
2 Hosting/Compute
3 Cloud/Virtualization
4 Containers/Kubernetes
5 Networking
6 Database
7 Storage/Backup/DR
8 Email
9 SMS/Voice/Omnichannel
10 Payments/Billing/Fintech
11 Developer/API
12 Software Development/DevOps/Deployment
13 Cybersecurity
14 Monitoring/Observability/SRE
15 AI/ML/Automation
16 Media/Video/Realtime
17 Data Engineering/Analytics
18 Business Applications/Productivity
19 IT Consulting/Managed IT
20 IoT/Smart Systems
21 Digital Trust/Compliance/Identity
22 Licensing/Software Distribution

This is full category-level monetization coverage, not a completed SKU-by-SKU market price list.

## 6. Status and gaps

| Work item | Status |
|---|---|
| Pricing strategy documented | DONE |
| All 22 category charging dimensions | DONE |
| Free/freemium/trial/sandbox policy | DONE |
| Competitor benchmark examples | PARTIAL |
| 3–5 comparable competitors for every category/SKU | MISSING / NEEDS RESEARCH |
| Provider wholesale quotations | MISSING |
| TEKORA final SKU retail prices | NOT APPROVED |
| Margin floor by category | NEEDS FINANCE INPUT |
| Tax/legal review by service model | NEEDS PROFESSIONAL VALIDATION |
| Real payment fee / control-number commercial terms | BLOCKED pending provider and legal validation |
| Customer pricing experiments/elasticity | NOT STARTED |

## 7. Next pricing workstream

During Phase 01/02, build a competitor benchmark matrix for every candidate SKU, collect written provider/wholesale quotations, normalize specs/regions/taxes/renewals, calculate cost and margin floors, then submit a versioned proposed price book for owner/finance/legal approval. Do not publish live prices before this gate.

## 8. Validation limitation

Documentation updates were committed through GitHub. No pricing engine code, customer-facing price page, provider contract, live checkout, tax integration or price test was implemented. No claim of regulatory approval or provider authorization is made.
