# TEKORA — Provider, Country & Integration Due-Diligence Register

**Research snapshot:** 26 November 2026. **Status: PARTIAL.** Public documentation is discovery evidence, not proof of a commercial relationship, production access, legal approval, price commitment, SLA or suitability. No provider is approved by this register.

## Evidence rules
- VERIFIED PUBLIC DOCUMENTATION means only that the referenced public page currently describes the capability or requirement.
- NEEDS COMMERCIAL VERIFICATION means obtain written confirmation, contract, current price quote, service limits, support and permitted resale/managed-service terms.
- NEEDS LEGAL VERIFICATION means counsel/regulator review is required before offering the capability.
- BLOCKED means do not advertise or activate until prerequisite is met.
- Re-check links, terms, pricing, supported regions, API versions and status before procurement or production.

## Tanzania regulatory and country gates

| Area | Public evidence | TEKORA implication | Status |
|---|---|---|---|
| .tz domains | TCRA FAQ says registration is through accredited registrars; lists registrar definition and points to Karibu registrar list. Domain Names Management Regulations 2020 require .tz applications through accredited registrar. | Either pursue accreditation if commercially justified, or integrate with a currently accredited registrar under a written reseller/agent arrangement. Verify exact TLD/SLD eligibility, registrant verification, pricing and renewal/transfer terms. | VERIFIED RULE; TEKORA STATUS NEEDS VERIFICATION |
| Payments | BoT identifies NPS Act 2015 and its supervisory role; OAG lists revised NPS Act publication 2025 and Electronic Money Regulations amendment GN 86 of 2026. | Determine whether each TEKORA activity is software/technical integration, merchant aggregation, payment facilitation, acquiring, wallet/e-money, switching or another regulated role. Get written legal classification and provider approval. | LEGAL REVIEW REQUIRED |
| Personal data | PDPA 2022 and 2023 Collection and Processing Regulations are published; PDPC describes controller/processor registration and oversight responsibilities. | Map controller/processor roles, registration applicability, DPO, lawful basis, notices, rights, breach response, transfers, retention and processor contracts. | LEGAL/PRIVACY REVIEW REQUIRED |
| Cybersecurity/evidence | Cybercrimes Act 2015 (revised publication shown 2025) is listed by OAG. | Security testing must have written authorization, defined scope, safe limits and evidence controls. | LEGAL REVIEW REQUIRED |
| SMS | Twilio Tanzania guidelines state two-way SMS unsupported, sender ID registration required on major networks and pre-registration timing; unregistered IDs blocked from 16 June 2025. | Sender ID approval is a launch dependency; do not promise two-way SMS through Twilio for TZ. Verify each network/provider independently. | PUBLIC DOC VERIFIED; COMMERCIAL/NETWORK VALIDATION REQUIRED |
| Tax/e-invoicing | No sufficiently complete current TRA-specific tax/e-invoicing opinion established in this discovery pass. | Obtain tax advice on VAT, withholding, invoicing, EFD/e-receipt applicability, cross-border digital services, imported services and marketplace/agent treatment. | NEEDS VERIFICATION |

### Primary references
- TCRA FAQ: https://www.tcra.go.tz/faq
- TCRA Domain Names Management Regulations 2020: https://www.tcra.go.tz/uploads/documents/sw-1619088302-The%20Electronic%20and%20Postal%20Communications%20%28Domain%20Names%20Management%29%20Regulations%2C%202020..pdf
- BoT payment-system regulations: https://www.bot.go.tz/PaymentSystem/regulations?lang=en
- OAG National Payment Systems Act: https://oagmis.oag.go.tz/portal/acts/80
- OAG Personal Data Protection Act: https://oagmis.oag.go.tz/portal/acts/237
- PDPC: https://pdpc.go.tz/
- OAG Personal Data Collection and Processing Regulations 2023: https://oagmis.oag.go.tz/portal/legislation/1350
- OAG Cybercrimes Act: https://oagmis.oag.go.tz/portal/acts/89

## Candidate provider matrix (not approved)

| Capability | Candidate | Publicly documented evidence | What must be checked before selection | Current decision |
|---|---|---|---|---|
| DNS / edge / WAF / CDN | Cloudflare | DNS documentation describes authoritative DNS; Registrar API docs describe search, availability, registration and management for supported extensions. | Confirm exact extension support (.tz not assumed), reseller rights, account model, API scope, support tier, data processing terms, rate limits and current quote. | Candidate for DNS/edge; .tz registrar path unverified |
| Domains | TCRA-accredited .tz registrar(s) listed through Karibu portal | TCRA says .tz registrars must be accredited; public registrar directory is linked by TCRA. | Retrieve current directory, validate accreditation directly, interview shortlisted registrar, API/reseller agreement, renewal/transfer and registrant data handling. | Mandatory procurement research |
| Cloud compute / storage / database | AWS, Azure, Google Cloud, DigitalOcean, Hetzner, OVHcloud (shortlist only) | Mature public provider ecosystems; this document does not yet validate current Tanzania region availability, resale eligibility, exact APIs or terms. | Per-service/region matrix; organization account; API access; reseller/partner status; egress; tax; FX; billing; support; DPA; data residency; service quotas; SLA and outage history. | Unverified shortlist |
| Container platform | Managed Kubernetes/cloud providers and self-managed Kubernetes | Product capabilities vary by region and support tier. | Control plane responsibility, version lifecycle, CNI/CSI, backups, upgrades, cluster security, support, cost and customer isolation. | Partner-dependent |
| SMS | Twilio | Official Tanzania guidelines document sender-ID rules, two-way SMS unsupported and registration lead times. | Local sender registration, exact carrier route, throughput, delivery receipts, support, price/FX, consent, opt-out and fallback. | Candidate only; two-way SMS not supported per current Twilio country page |
| WhatsApp | Twilio / Meta WhatsApp Business Platform | Twilio pricing page includes Tanzania in Rest of Africa pricing group; fees include provider and Meta components. | Business portfolio approval, number eligibility, template approval, current Meta fee, local tax, opt-in, conversation category and provider terms. | Candidate only |
| Payments | PayIt, SN Pay and licensed banks/PSPs (research candidates) | Public PayIt merchant integration page describes mobile-money initiation, polling and signed webhooks; SN Pay docs describe REST, API key and sandbox/live environments. | Independently verify legal entity, BoT licensing/authorization category, merchant onboarding, actual settlement account, fees, refunds, webhook signing, idempotency, control-number support, sandbox fidelity, SLA, data processing and contract. | DO NOT ENABLE until diligence and legal approval |
| Email delivery | SES, Postmark, SendGrid, Mailgun and regional providers | Not individually validated in this pass. | Tanzania delivery route, sender domain, suppression, data location, DPA, abuse policy, dedicated IP, support and total cost. | Unverified shortlist |
| Video/realtime | LiveKit Cloud / self-hosted LiveKit, cloud media providers | Candidate architecture only; no TEKORA contract or regional QoE proof. | TURN/SFU geography, bandwidth cost, recording storage, DPA, encryption, concurrency, support and incident responsibility. | Unverified |
| AI/ML | Model providers and self-hosted models | No provider-specific data-retention or region terms approved. | Model/version availability, region, prompt retention/training, DPA, safety, rate limits, price, fallback and deletion. | Unverified |
| Monitoring/security | OpenTelemetry-compatible tools and security vendors | Standards/tool ecosystem, not a chosen supplier. | Data residency, log PII, retention, agent permissions, incident support, license, cost and export. | Unverified |

## Provider due-diligence checklist
For every candidate collect:
1. Legal entity, registration, jurisdiction, beneficial ownership where relevant and regulatory licence/authorization.
2. Official product documentation, API reference, SDKs, changelog and deprecation policy.
3. Supported countries, regions, currencies, carriers, TLDs, networks and exclusions.
4. Contract, DPA, subprocessor list, transfer mechanism, retention/deletion and breach notification.
5. Reseller, white-label, agent, managed-service and brand usage rights.
6. Authentication, scopes, key rotation, IP allowlists, webhook signing, idempotency and audit.
7. Sandbox/live separation and evidence of sandbox parity.
8. Rate limits, quotas, concurrency, service dependencies and failure semantics.
9. Full pricing: setup, recurring, usage, minimum, overage, FX, tax, egress, refunds and termination.
10. Support hours, escalation, incident communications, status page, RTO/RPO and contractual SLA.
11. Settlement/reconciliation details for financial providers; no screenshot-only proof.
12. Exit plan: data export, credential revocation, DNS/resource migration, notice periods and continuity.

## Procurement decision record
A provider may move to APPROVED only after owner, legal/commercial evidence, technical proof-of-concept, security review, operational runbook, cost model, support plan and explicit approval are recorded. Public API documentation alone is insufficient.
