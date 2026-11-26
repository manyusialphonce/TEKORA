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
