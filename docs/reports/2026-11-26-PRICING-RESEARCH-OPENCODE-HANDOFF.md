# Pricing Research Completion & OpenCode Handoff Report — 26 November 2026

## Scope
Consolidate pricing discovery across all 22 TEKORA service categories into one implementation-facing catalogue and three SKU research waves.

## Deliverables
- `docs/SKU_LEVEL_COMPETITIVE_PRICING_WAVE_01.md`: categories 01, 02, 09 (existing baseline).
- `docs/SKU_LEVEL_COMPETITIVE_PRICING_WAVE_02.md`: categories 03–08.
- `docs/SKU_LEVEL_COMPETITIVE_PRICING_WAVE_03.md`: categories 10–22.
- `docs/MASTER_SKU_PRICING_CATALOGUE.md`: canonical SKU families, data contract, commercial statuses, pricing formula, safeguards and OpenCode reading/implementation sequence.
- All-category competitor benchmark matrix and pre-existing product catalogue framework remain in force.

## Readiness result
All 22 categories have SKU family/charging-unit mapping and a defined pricing/monetization approach. This is not exhaustive supplier due diligence for every individual SKU and not a final price book. Public retail anchors are indicative only. Direct wholesale quotes, supplier contracts, FX/tax validation, regulatory classification, margin floors, reseller permissions, and operational capability remain unresolved where stated.

## Critical controls
- No fabricated wholesale cost or final retail price.
- No blanket 3–8% undercut; only comparable offers with validated cost and margin.
- No live payments, control-number collection, payouts, production infrastructure spend or provider commitments without explicit authorization.
- No unlimited free compute, AI, messages, voice/video, storage, support or consulting.
- Versioned prices and immutable quote/order/invoice snapshots.
- Idempotent metering, hard quotas, alerts, explicit paid opt-in and audit trail.
- All quote/legal/provider dependent products stay NEEDS_QUOTE/blocked until approved.

## OpenCode handoff
OpenCode must read the canonical docs in the order specified by the Master SKU Catalogue. It must first audit repository and phase status, then work only on the currently approved phase. Pricing documents are product requirements, not permission to skip architecture, foundation or approval gates. Implementation must preserve all prior requirements and update README, Blueprint traceability and phase reports with evidence.

## Verification
Repository files and references must be re-fetched after commit. No local runtime validation or application tests are claimed by this documentation-only work.
