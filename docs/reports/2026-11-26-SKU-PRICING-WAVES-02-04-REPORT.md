# SKU Pricing Waves 02–04 — Research Report

**Date:** 26 November 2026  
**Scope:** Categories 03–22, completing the first SKU-structure pass for all 22 categories.  
**Status:** PARTIAL / DISCOVERY; no customer-facing prices approved.

## Work performed

- Mapped chargeable SKU families and billing units for cloud, Kubernetes/container, networking, database, storage/backup, email, payment infrastructure, developer/API, software/DevOps, security, observability, AI, media, data, business applications, IT consulting, IoT, identity/compliance and licensing.
- Defined monetization approaches and bounded free-entry models.
- Added public benchmarks where available, including Lineserve cloud/Kubernetes, Supabase, Cloudflare R2, Backblaze, Zoho, Amazon SES, Grafana and managed IT service pricing.
- Explicitly kept quote-based, legally blocked and supplier-dependent offerings quote-based instead of inventing prices.
- Defined the key procurement, cost, tax, legal, provider, capacity, staffing and security gates.

## Coverage

Categories 03–22 have SKU structures, billing units, pricing models, free-entry rules and validation gates in the new document. Combined with Wave 01 (Categories 01, 02 and 09), the first SKU architecture pass covers all 22 categories. Some overlap with Wave 01 is intentional: Category 09 was previously researched at SKU-level; category-wide service frameworks are additive and cross-reference prior evidence.

## Public benchmark signals

- Lineserve cloud server public entry at TZS 29,700/month; VPS prices depend on configuration.
- Lineserve Kubernetes control-plane public launch pricing: Basic TZS 55,720/month plus workers; HA TZS 232,680/month plus workers.
- Supabase, Cloudflare R2, Backblaze B2, Zoho Workplace, SES and Grafana provide international public price references but require regional, specification and cost normalization.
- Wemanage publishes managed IT starting prices of TZS 500,000/month and TZS 800,000/month under its stated device and contract conditions; not directly comparable.

## Documents changed

- New: `docs/SKU_LEVEL_COMPETITIVE_PRICING_WAVES_02_04.md`
- Updated: `README.md`
- Updated: `docs/PRODUCT_CATALOGUE_SKU_PRICING_FRAMEWORK.md`
- Updated: `docs/COMPETITOR_PRICING_BENCHMARK_MATRIX.md`
- Updated: `docs/MASTER_PLATFORM_BLUEPRINT.md`

## Limitations and status

- This is pricing architecture and first-pass public benchmark research, not a complete quote collection.
- Many categories require written wholesale/provider quotes or bespoke scope.
- Payment processing and control-number fees remain blocked pending regulatory/legal/provider verification.
- Reseller authorization, supplier cost, tax/EFD treatment, FX, margin floors, service capacity and SLAs remain unresolved where not evidenced.
- No TEKORA price book, supplier contract, legal authorization, launch or service delivery is approved.

## Next step

For candidate launch SKUs, obtain 3–5 normalized competitors where comparable public data exists, written supplier cost quotes, technical validation, cost/margin simulations, tax/legal approval, and controlled price-book acceptance. Prioritize quote-request templates and cost worksheets rather than assigning unsupported prices.
