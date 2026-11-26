# TEKORA — SKU-Level Competitive Pricing Analysis, Wave 01

**Research snapshot:** 26 November 2026  
**Coverage:** Category 01 Domains/DNS; Category 02 Web Hosting/Compute; Category 09 SMS/WhatsApp Messaging  
**Status:** PROVISIONAL MARKET MODELLING — NOT AN APPROVED PRICE BOOK  
**Currency:** TZS unless explicitly stated. Public competitor prices may exclude VAT and may be introductory or conditional.

## 1. Why this wave is separated

The all-category matrix maps the full 22-category scope. This document begins the deeper SKU-level pass for categories where multiple Tanzania-facing public price points and product specifications are visible. It does not imply the other 19 categories are excluded; they remain in the master matrix and will be analysed in subsequent waves.

The working 3–8% undercut hypothesis is applied only to comparable, published retail price points. It is not applied to supplier pass-through costs, regulated products, or offers whose specifications and tax treatment cannot be normalized. Proposed ranges below are market-positioning hypotheses and must pass supplier-cost, tax, margin, and legal approval.

## 2. Evidence and calculation conventions

- **Observed price:** public price found on a provider's page on the research date.
- **Comparable:** same billing unit, geography, resource/specification, term, included features and tax basis sufficiently aligned.
- **Target hypothesis:** candidate TEKORA public price range to test after supplier quote and unit economics; not a promise to customers.
- **Cost gate:** no price can be approved until fully loaded cost is known.
- **VAT:** competitor pages differ in tax disclosure. Do not compare tax-exclusive and tax-inclusive figures without normalization.
- **Renewal:** record registration/promo and renewal prices separately; do not hide renewal increases.
- **SMS segment:** one credit/segment is not necessarily one message. GSM-7 and Unicode limits differ; long messages can be billed as multiple segments.

For cost (C) and approved gross margin (m), pre-tax price floor is (C/(1-m)). TEKORA target must be at or above the floor.

## 3. Category 01 — Domains, DNS & Internet Services

### 3.1 .co.tz domain registration / renewal

| Provider | New registration | Renewal | Notes |
|---|---:|---:|---|
| Sakurahost | TZS 19,500 | TZS 25,000 | Public table labels new price as sale; 1 year. [Source](https://billing.sakurahost.co.tz/domain/pricing) |
| Syntrax Cloud | TZS 25,000 | Not separately stated | Public page describes 1-year price; renewal must be confirmed. [Source](https://cloud.syntrax.co.tz/vps) |
| NetPoa | TZS 25,000 | Not separately stated | Landing page lists .co.tz from TZS 25,000/year. [Source](https://netpoa.tz/) |
| TLDHub comparison | Lowest shown USD 11.40 registration and USD 11.40 renewal | USD 11.40 | International registrar comparison; not a TZS local-market offer and FX/payment fees apply. [Source](https://tldhub.com/co.tz) |

**TEKORA provisional target hypothesis**
- New registration: **TZS 18,500–19,000/year** only if authorized wholesale/registrar cost allows it.
- Renewal: **TZS 23,000–24,000/year** only if registry + registrar + FX + support cost is below the approved price floor.
- Transfer: quote separately; verify whether transfer extends registration and which registry fee applies.
- Do not price renewal using the new-customer promotional price.

**Decision:** PROVISIONAL. The TCRA FAQ directs customers to the accredited registrar list and applicable domain regulations. TEKORA must confirm its own accredited registrar or authorized reseller route and obtain the current wholesale schedule before offering registration. [TCRA FAQ](https://www.tcra.go.tz/faq) · [Karibu registrars](https://karibu.tz/domains/registrars/)

### 3.2 Other TLDs

| TLD | Observed Tanzania public price | TEKORA treatment |
|---|---|---|
| .tz | Sakurahost shows TZS 100,000 registration and renewal | Do not bundle with .co.tz; confirm premium/second-level eligibility and registry conditions. |
| .africa | Sakurahost shows TZS 50,000 registration; TZS 63,500 renewal | Separate registration and renewal; no assumed fixed discount. |
| .net | Sakurahost shows TZS 45,000 registration; TZS 48,500 renewal | Check global registrar wholesale, ICANN fee, FX and renewal. |
| .sc.tz | Sakurahost shows TZS 14,500 registration; TZS 25,000 renewal | Make promo-to-renewal difference explicit. |

Source: [Sakurahost domain pricing](https://billing.sakurahost.co.tz/domain/pricing). Prices are public observations, not wholesale quotes.

**SKU design**
- DOMAIN-TLD-REG-1Y
- DOMAIN-TLD-RENEW-1Y
- DOMAIN-TLD-TRANSFER
- DOMAIN-DNS-BASIC-ZONE-MONTH
- DOMAIN-DNS-PREMIUM-ZONE-MONTH
- DOMAIN-DNS-QUERY-MILLION (only where provider cost is query-metered)
- DOMAIN-DNSSEC-ENABLEMENT / managed DNS support

DNS should not be priced per record by default. Basic DNS may be bundled with domain management; premium DNS is differentiated by SLA, anycast network, security controls, analytics and support, not arbitrary record count.

### 3.3 Free developer subdomains

- Free TEKORA-managed subdomain remains a developer acquisition benefit, not a free registrable .co.tz or .com domain.
- Proposed initial allowance remains one hostname/account with renewable 90-day term, subject to eligibility, abuse checks and infrastructure-cost approval.
- No free mailbox, outbound mail, compute, production SLA, wildcard DNS or arbitrary nameserver delegation by default.
- Do not launch until the dedicated domain, DNS isolation, host registry, TLS automation, abuse process and support runbooks are approved.

## 4. Category 02 — Web Hosting, Application Hosting & Compute

### 4.1 Shared hosting: entry and business tiers

| Provider / plan | Public price | Billing / published features |
|---|---:|---|
| Hostraha Essential | TZS 56,999/year (~4,750/month) | 25 GB SSD, 2 websites, 25 email accounts, 5 databases, free SSL and daily backups. [Source](https://www.hostraha.co.tz/pricing) |
| Hostraha Business | TZS 94,999/year (~7,917/month) | 50 GB SSD, 5 websites, 100 email accounts, 50 databases, free domain and daily backups. [Source](https://www.hostraha.co.tz/pricing) |
| Hostraha Advanced | TZS 139,999/year (~11,667/month) | 100 GB SSD, 10 websites, unlimited email accounts/databases as advertised, daily backups. [Source](https://www.hostraha.co.tz/pricing) |
| Hi-Tech Hosting shared entry | From TZS 5,500/month billed annually | Compare its current plan allowances and renewal terms before direct SKU matching. [Source](https://hitechwebhosting.com/tz/shared-hosting/) |
| NetPoa shared hosting | From TZS 99,000/year | Landing page states shared cPanel hosting, LiteSpeed, weekly off-site backups, free migration and 99.9% uptime guarantee. [Source](https://netpoa.tz/) |

**Candidate TEKORA target ranges (annual commitment; pre-tax until tax treatment verified)**

| TEKORA candidate SKU | Normalized target spec | Target hypothesis | Comparable anchor / rationale |
|---|---|---:|---|
| SHARED-STARTER | 10–25 GB SSD/NVMe; 1–2 sites; SSL; defined mailbox/database quotas; backup schedule stated | TZS 52,000–55,000/year | Hostraha Essential TZS 56,999/year; only valid if storage, site count, backups, support and renewal are comparable. |
| SHARED-BUSINESS | 40–50 GB; up to 5 sites; database/mailbox quotas; daily backup; migration allowance | TZS 89,000–92,000/year | Hostraha Business TZS 94,999/year. |
| SHARED-GROWTH | 80–100 GB; up to 10 sites; stronger resource limits and backup retention | TZS 130,000–135,000/year | Hostraha Advanced TZS 139,999/year. |
| SHARED-ENTERPRISE | Custom resources, isolation, security, backup and SLA | Quote | Do not imply unlimited resources; price based on actual reserved capacity and support. |

**Important:** these are deliberately narrow market hypotheses, not launch prices. Hostraha shows annual billing and excludes applicable taxes. Hi-Tech's page indicates annual billing on the entry price. Confirm renewal, server location, inode/CPU/IO limits, overselling policy, backup restore charges and support response before declaring offers equivalent.

### 4.2 WordPress / managed application hosting

| Benchmark | Public price |
|---|---:|
| Hostraha WP Essentials | TZS 70,000/year (~5,833/month), 25 GB, one website, SSL and daily backups |
| Hostraha WP Business | TZS 105,000/year (~8,750/month), 50 GB, two websites, SSL and daily backups |
| Hostraha WP Professional | TZS 148,750/year (~12,396/month), 100 GB, three websites, SSL and daily backups |

Source: [Hostraha pricing](https://www.hostraha.co.tz/pricing).

**TEKORA SKU hypothesis**
- WP-STARTER: TZS 65,000–68,000/year.
- WP-BUSINESS: TZS 98,000–102,000/year.
- WP-PRO: TZS 139,000–144,000/year.
- Managed performance/security, premium plugins, malware cleanup and developer support must be separate add-ons or clearly included with a costed service scope.

Do not compare generic shared hosting to managed WordPress if caching, WAF, staging, backups, malware remediation and application support differ.

### 4.3 Linux VPS

| Provider / plan | vCPU | RAM | Storage | Public price/month |
|---|---:|---:|---:|---:|
| Lineserve Linux VPS 2 GB | 1 | 2 GB | 40 GB SSD | TZS 32,400 |
| Lineserve Linux VPS 4 GB | 2 | 4 GB | 80 GB SSD | TZS 64,800 |
| Lineserve Linux VPS 8 GB | 4 | 8 GB | 160 GB SSD | TZS 129,600 |
| Lineserve Linux VPS 16 GB | 6 | 16 GB | 320 GB SSD | TZS 259,200 |
| Sakurahost VPS starting point | Specs vary by selected plan | — | NVMe advertised | From TZS 27,800/month |
| Hi-Tech managed VPS | 4 vCPU | 4 GB | 80 GB NVMe | TZS 34,500/month |
| NetPoa Cloud VPS | 2–8 vCPU advertised | 4–16 GB advertised | 20 TB transfer advertised | From TZS 89,000/month |

Sources: [Lineserve](https://www.lineserve.co.tz/pricing), [Sakurahost](https://billing.sakurahost.co.tz/domain/pricing), [Hi-Tech](https://hitechwebhosting.com/tz/managed-vps), [NetPoa](https://netpoa.tz/).

**Do not treat the VPS prices as like-for-like.** CPU allocation/oversubscription, SSD vs NVMe, traffic, IPv4, region, management, backups, Windows licensing, DDoS protection and VAT differ.

**Candidate TEKORA resource SKUs**
- VPS-LINUX-1C-2G-40G: target **TZS 30,500–31,500/month** against Lineserve's published 1 vCPU / 2 GB / 40 GB SSD at TZS 32,400, only if resource guarantees and included network/IP are comparable.
- VPS-LINUX-2C-4G-80G: no fixed target until an exact comparable offer and supplier quote are verified. Hi-Tech's managed 4 vCPU / 4 GB / 80 GB is not a direct match to Lineserve's 2 vCPU / 4 GB / 80 GB.
- VPS-LINUX-4C-8G-160G: target **TZS 122,000–126,000/month** against Lineserve TZS 129,600, subject to equivalent CPU, disk, traffic and IP.
- VPS-LINUX-6C-16G-320G: target **TZS 244,000–252,000/month** against Lineserve TZS 259,200, subject to cost and spec parity.
- VPS-WINDOWS: calculate Windows Server license and compliance separately; never derive it by simply adding an arbitrary markup to Linux.
- VPS-MANAGED-ADDON: quote/price separately for patching, monitoring, backup, security response and support coverage.

### 4.4 Compute and hosting billing guardrails

- Separate VM resource price, public IPv4, backup storage, snapshots, egress, managed operations and software licensing.
- Publish fair-use and traffic policies; never use “unlimited bandwidth” where a hidden fair-use cap exists.
- State whether CPU is dedicated, shared or burstable.
- Define uptime measurement, exclusions, service credits and maintenance windows before advertising SLA.
- For annual hosting, show the renewal price and term before checkout.
- Provide quota warnings and suspend/throttle behavior for abusive usage; no surprise overage.
- Show estimates and hard spending caps for hourly/metered resources.

## 5. Category 09 — SMS, WhatsApp & Messaging APIs

### 5.1 Tanzania bulk SMS retail benchmarks

| Provider | Volume tier | Published rate / SMS | Notes |
|---|---:|---:|---|
| NextSMS | 1–5,000/month | TZS 16 | Sender ID registration required |
| NextSMS | 5,001–50,000 | TZS 15 | Same |
| NextSMS | 50,001–100,000 | TZS 14 | Same |
| NextSMS | 100,001–250,000 | TZS 13 | Same |
| NextSMS | 250,001–500,000 | TZS 12 | Same |
| NextSMS | 500,001–2,000,000 | TZS 10.50 | Same |
| DARSMS | 100–4,999 | TZS 22 | Excludes VAT; no setup/monthly fee; 5-credit trial |
| DARSMS | 5,000–9,999 | TZS 20 | Excludes VAT |
| DARSMS | 10,000–49,999 | TZS 18 | Excludes VAT |
| DARSMS | 50,000+ | TZS 15 | Excludes VAT |
| SasiSMS | From 1,000 credits | TZS 22 | Credits never expire |
| SasiSMS | From 10,000 credits | TZS 19 | Credits never expire |
| SasiSMS | From 100,000 credits | TZS 16 | Credits never expire |
| MasokoDigital | 1–1,000 | TZS 35 | Prepaid; API included |
| MasokoDigital | 1,001–5,000 | TZS 19 | Prepaid |
| MasokoDigital | 5,001–50,000 | TZS 18 | Prepaid |
| MasokoDigital | 50,001–100,000 | TZS 17 | Prepaid |
| MasokoDigital | 100,001–500,000 | TZS 16 | Prepaid |
| MasokoDigital | 500,001–1,000,000 | TZS 15 | Prepaid |
| MasokoDigital | 1,000,001+ | TZS 14 | Prepaid |
| Send | Low volume to very high volume | TZS 20 down to TZS 10.7 | Published volume-based prepaid pricing; VAT excluded |

Sources: [NextSMS](https://nextsms.co.tz/pricing), [DARSMS](https://www.darsms.co.tz/about), [SasiSMS](https://sms.sasidigital.co.tz/), [MasokoDigital](https://masokodigital.co.tz/), [Send](https://send.co.tz/pricing/).

### 5.2 Proposed TEKORA SMS price ladder

| Monthly/prepaid purchase tier | Public competitor band observed | TEKORA target hypothesis |
|---|---:|---:|
| 1–4,999 segments | TZS 16–22 (some vendors have higher minimum/top-up prices) | TZS 15.50–16.00 |
| 5,000–49,999 | TZS 15–20 | TZS 14.50–15.00 |
| 50,000–99,999 | TZS 14–18 | TZS 13.50–14.00 |
| 100,000–249,999 | TZS 13–16 | TZS 12.50–13.00 |
| 250,000–499,999 | TZS 12–16 | TZS 11.50–12.00 |
| 500,000–999,999 | TZS 10.50–15 | TZS 10.20–10.50 |
| 1,000,000+ | TZS 10.50–14 | Quote / target near TZS 10 only if wholesale rate and margin allow |

**Critical:** These target bands are aggressive and only publishable if TEKORA secures a carrier/provider wholesale cost low enough to preserve its approved margin after sender-ID, VAT, payment, failed delivery, support and fraud costs. If the cost floor is above the proposed target, raise the price or do not offer that tier. Do not subsidize high-volume traffic with unrelated subscription revenue without explicit approval.

### 5.3 SMS SKU catalogue

- MSG-SMS-LOCAL-SEGMENT — charged per submitted/accepted billable segment according to the provider's settlement definition.
- MSG-SMS-OTP-SEGMENT — separate OTP route/quality price only if supplier costs differ.
- MSG-SMS-TRANSACTIONAL-SEGMENT — alerts, receipts, reminders.
- MSG-SMS-CAMPAIGN-SEGMENT — marketing/bulk with consent and opt-out requirements.
- MSG-SENDER-ID-REGISTRATION — pass-through + disclosed handling fee, if legally permitted.
- MSG-SMS-API-MONTH — optional platform subscription for dashboard/API features, not a hidden fee on each SMS.
- MSG-DELIVERY-REPORT — included by default if provider cost allows; otherwise disclose.
- MSG-INBOUND-SMS — quote only if inbound Tanzania routes and two-way support are confirmed.

### 5.4 WhatsApp Business pricing

Public pages show materially different price models:
- NextSMS lists TZS 12/message and explicitly says additional Meta fee applies and WhatsApp account/template registration is required.
- MasokoDigital lists TZS 29 marketing, TZS 26 utility and TZS 15 service/free-form message categories.
- NetPoa advertises from TZS 20/message.

Sources: [NextSMS](https://nextsms.co.tz/pricing), [MasokoDigital](https://masokodigital.co.tz/), [NetPoa](https://netpoa.tz/).

**TEKORA recommendation:** Do not publish a single flat “WhatsApp message” price until the current Meta rate card, recipient market, template category, provider markup and any BSP fee are separated. Use this structure:

`Customer price = Meta pass-through + BSP/provider fee + TEKORA platform fee + applicable tax`

Show marketing, utility, authentication and service/free-form as separate billable categories where the provider's charging model requires it. Do not claim that the provider's TZS 12 is all-inclusive when its page states Meta fees are additional.

### 5.5 SMS and WhatsApp free entry

- Free account and API sandbox documentation.
- Small test credit allowance only after provider authorizes it; keep sandbox separate from production.
- No free production campaign or unlimited OTP traffic.
- Require verified sender, consent/source-of-contact evidence, opt-out suppression, rate limits, anti-pumping controls and abuse monitoring.
- Alert on segment count before sending; preview Unicode/long-message segmentation and estimated charge.
- Set per-campaign and per-tenant spend caps. Require confirmation for large campaigns.
- Do not promise sender-ID approval time until confirmed by local carrier/provider.

## 6. Pricing decision register for this wave

| SKU family | Market target | Commercial status | Required before approval |
|---|---|---|---|
| .co.tz new registration | TZS 18,500–19,000/year | PROVISIONAL | Authorized registrar route, wholesale schedule, tax and renewal economics |
| .co.tz renewal | TZS 23,000–24,000/year | PROVISIONAL | Registry renewal cost, renewal service fee, margin floor |
| Shared hosting tiers | TZS 52k–55k; 89k–92k; 130k–135k/year | PROVISIONAL | Resource guarantees, supplier/reseller cost, tax, backup and support cost |
| WordPress tiers | TZS 65k–68k; 98k–102k; 139k–144k/year | PROVISIONAL | Managed WordPress scope and plugin/support cost |
| VPS 1 vCPU / 2 GB / 40 GB | TZS 30.5k–31.5k/month | PROVISIONAL | Exact spec parity, supplier cost, IPv4, traffic and VAT |
| VPS 4 vCPU / 8 GB / 160 GB | TZS 122k–126k/month | PROVISIONAL | Exact spec parity, supplier cost, traffic and VAT |
| SMS volume ladder | TZS 10.20–16 per segment by tier | PROVISIONAL / HIGH RISK | Written wholesale route cost, tax, sender ID, delivery and fraud economics |
| WhatsApp categories | Pass-through + disclosed fees | NEEDS QUOTE | Current Meta pricing, BSP contract, market and template category |

No row above is APPROVED. All values must be recalculated against fully loaded costs.

## 7. Outstanding work for this wave

1. Obtain at least two written wholesale offers for .tz domain, shared hosting/VPS and SMS routes; confirm reseller authorization.
2. Normalize all competitor specifications and tax/renewal terms from the source pages.
3. Confirm the exact TCRA/tzNIC registrar route before any domain sales claim.
4. Confirm SMS sender-ID registration, operator route, Unicode/segment billing, DLR quality, failed-message charges, VAT and delivery SLA.
5. Confirm WhatsApp BSP relationship, Meta pass-through schedule, template categories, quality controls and number onboarding.
6. Build unit-economics worksheets with FX, payment fees, VAT, support, fraud, refunds, backup, egress and margin floor.
7. Run sample invoices and quote snapshots for registration vs renewal, annual hosting renewal, VPS monthly usage and SMS multi-segment billing.
8. Approve price-book versions through product, finance and legal owners before customer display.

## 8. Source register

- [Lineserve Tanzania VPS pricing](https://www.lineserve.co.tz/pricing)
- [Hostraha product pricing](https://www.hostraha.co.tz/pricing)
- [Sakurahost domain pricing](https://billing.sakurahost.co.tz/domain/pricing)
- [Hi-Tech Hosting shared hosting](https://hitechwebhosting.com/tz/shared-hosting/)
- [Hi-Tech Hosting managed VPS](https://hitechwebhosting.com/tz/managed-vps)
- [NetPoa](https://netpoa.tz/)
- [Syntrax Cloud](https://cloud.syntrax.co.tz/vps)
- [NextSMS](https://nextsms.co.tz/pricing)
- [DARSMS](https://www.darsms.co.tz/about)
- [SasiSMS](https://sms.sasidigital.co.tz/)
- [MasokoDigital](https://masokodigital.co.tz/)
- [Send](https://send.co.tz/pricing/)
- [TCRA FAQ](https://www.tcra.go.tz/faq)
- [Karibu accredited registrars](https://karibu.tz/domains/registrars/)

## 9. Outcome

**PARTIAL — Wave 01 researched and documented.** Three categories now have SKU-level public price comparisons and provisional target ranges/charging structures. These are not supplier quotes and do not authorize sales. The remaining categories are retained in the 22-category master matrix for subsequent waves.
