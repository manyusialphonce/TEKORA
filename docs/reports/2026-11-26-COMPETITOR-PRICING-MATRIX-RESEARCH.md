# TEKORA — Competitor Pricing Benchmark Matrix Research Report

**Date:** 26 November 2026  
**Scope:** First-pass public pricing research and monetization mapping for all 22 TEKORA service categories.  
**Status:** PARTIAL — discovery artifact committed; no approved retail prices or commercial launch decisions.

## Objective

Convert the existing pricing/freemium strategy into a category-by-category benchmark matrix without removing or replacing earlier requirements. The research distinguishes public competitor retail prices from TEKORA supplier costs and from legally approved customer-facing prices.

## Work completed

- Researched public pricing references for Tanzania hosting, managed VPS, .tz domain reseller pricing, SMS, WhatsApp and payment gateway fee schedules.
- Researched selected international public price references for database services, cloud usage, object storage, transactional email, business email and observability.
- Mapped all 22 service categories to charging units, initial competitive approach, free/entry path, paid monetization and validation blockers.
- Preserved the 3–8% undercut as a conditional hypothesis only; no blanket discount or final TEKORA price was set.
- Defined a free-to-paid model catalogue and explicit protections against silent conversion, surprise overage and unlimited free consumption.
- Defined benchmark evidence grades E1–E5, required benchmark record fields, unit-economics formula, approval sequence and acceptance criteria.
- Identified categories that must remain quote-based or blocked until provider, legal, commercial and operational evidence exists.

## Primary public price anchors captured

| Provider | Observed price | Product |
|---|---:|---|
| Hi-Tech Hosting | TZS 5,500/month billed annually | Shared hosting entry |
| Hi-Tech Hosting | TZS 34,500/month | Managed VPS, 4 vCPU / 4 GB RAM / 80 GB NVMe |
| NetPoa | From TZS 89,000/month | Tanzania VPS |
| reseller.co.tz | From TZS 20,000/year | .tz domains |
| reseller.co.tz | From TZS 16/SMS | SMS |
| Send | TZS 20 down to TZS 10.7/SMS segment | Tanzania SMS by prepaid volume, before VAT |
| Send | TZS 100/outbound message | WhatsApp |
| BLMPay | Business: 3.00% mobile money, 3.50% cards, 2.50% QR | Payment processing; payout fees separate |
| Twilio | USD 0.4336/outbound SMS segment | Tanzania SMS |
| Amazon SES | USD 0.16/1,000 emails in first Essentials tier | Transactional email |
| Supabase | Free tier; Pro from USD 25/month | Database/backend platform |
| Cloudflare | R2 standard USD 0.015/GB-month; 10 GB-month free | Object storage |
| Grafana Cloud | Pro app observability from USD 0.025/host-hour; USD 19 platform fee | Observability |

All are public E1 observations only. Terms, region, taxes, support, contract and exact comparability must be reviewed before use in a price decision.

## Important limitations

- Public retail prices do not establish TEKORA wholesale cost, reseller authorization, provider SLA or profitability.
- Pricing research is not exhaustive; categories such as networking, cybersecurity engagements, consulting, IoT, identity/compliance and enterprise licensing often require tailored written quotes.
- No supplier quote, BoT classification, TCRA reseller authorization, tax opinion, payment/control-number approval or operational SLA was established by this research.
- FX conversions were intentionally not invented.
- No actual TEKORA retail price, free quota, margin target or tax treatment is approved.

## Changed files

- `docs/COMPETITOR_PRICING_BENCHMARK_MATRIX.md` — new 22-category matrix.
- `README.md` — to be updated with the new matrix reference and current research status.

## Verification

- GitHub create-file operation returned commit: `1d89afa707377d066db54b9397c5e3ddd625639c`.
- The matrix contains all 22 categories and labels unresolved pricing as provisional, quote-required or blocked.
- No application code, deployment, payment integration, supplier onboarding or external purchase was performed.

## Recommendation

Continue with SKU-level research in priority categories, obtaining 3–5 normalized comparables where public market alternatives exist and written supplier quotes for candidate launch SKUs. Complete full cost and margin simulations before any price publication. Keep the remaining categories in the catalogue and do not mark them commercially ready without E3–E5 evidence.
