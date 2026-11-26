# TEKORA — 22-Category Product Discovery Deep Dive

**Status: PARTIAL / DISCOVERY BASELINE.** This is not an approved SKU catalogue, provider commitment, legal opinion, price book or implementation specification. Candidate capabilities must be classified as TEKORA-operated, managed, integrated, resold or partner-delivered. Provider, country, legal, contract and operational facts remain unverified until evidenced.

## Product specification contract

For every SKU, complete: customer segment and job; scope/inclusions/exclusions; prerequisites; region/currency; provider and contract; delivery/responsibility model; lifecycle/state machine; dependencies; data ownership/classification/retention/export/deletion; roles/permissions; API/events; pricing unit/quota/overage/trial/renewal/cancellation; support hours/escalation; SLO only if supportable; failure/recovery; security/threat model; test cases; acceptance evidence; cost/margin; launch classification.

Classification: CORE PLATFORM, MVP CANDIDATE, LAUNCH EXPANSION, ADVANCED, PARTNER-DEPENDENT, DEFERRED. These are proposals, not approvals.

# Group A — Infrastructure foundations

## 01. Domains, DNS & Internet Services
**Product families:** domain search/availability; registration/renewal/transfer; portfolio management; DNS zones/records; managed DNS; DNSSEC; RDAP/WHOIS privacy where supported; registrar lock; certificates; expiry/security monitoring; migration assistance.

**Journey:** search → eligibility and full price/renewal disclosure → contact validation → order → authorized registrar submission → pending/active/failed reconciliation → DNS setup → validation → renewal/transfer/expiry/grace/closure. DNS changes require preview, validation, optional approval, apply, propagation observation and rollback guidance.

**Entities/contracts:** domain, TLD/registry, registrar, registrant reference, nameservers, zone and record versions, DNSSEC key state, certificate, transfer case, renewal instruction. Define supported TLDs, registrar role, ownership, transfer rules, fees, taxes, renewal, grace/redemption, DNS limits and support boundaries.

**Controls/failures:** step-up auth for transfers/contact/nameserver changes; registrar lock; audit; protect transfer codes; expiry alerts; DNSSEC rollover runbook. Handle stale availability, TLD restriction, timeout after registrar success, duplicate order, rejected transfer, expired code, DNS propagation, invalid DNSSEC, provider outage and renewal failure.

**Acceptance:** provider authorization/contract and per-TLD evidence; price/renewal verification; state mapping; DNS/DNSSEC tests; audit/step-up tests; transfer/expiry runbooks. Tanzania .tz pathway requires current verification with authorized registry/regulator. **Classification:** search/DNS are candidates only after provider route is proven; advanced DNS/certificates partner-dependent.

## 02. Web Hosting, Application Hosting & Compute
**Product families:** shared/reseller hosting; managed CMS; static sites; app/runtime hosting; VPS/dedicated compute; staging/preview; website care; migration; backup/restore; deployment add-ons. Distinguish hosting from software development and cloud VM orchestration.

**Lifecycle:** plan/quota disclosure → order/payment authorization → tenant/account provisioning → domain/runtime/database/storage → TLS → credentials → health check → usage/billing → resize/upgrade/downgrade → backup/restore/migration → suspension/grace → export/deletion.

**Contract:** runtime/language versions, CPU/RAM/storage/inodes/process limits, bandwidth/egress, DB/email quotas, region, TLS, backup frequency/retention, deployment/SSH methods, support, acceptable use and patching responsibility.

**Controls/failures:** tenant isolation, hardened runtime, SSH key rotation, malware/WAF dependencies, secret protection, noisy-neighbour control, backup encryption and restore drills. Handle partial provisioning, DNS delay, quota exhaustion, compromised CMS, node outage, failed deploy, corrupt backup, restore mismatch and cancellation retention.

**Acceptance:** repeatable provisioning/deprovisioning, isolation, quota enforcement, TLS, restore evidence, rollback, capacity test and shared-responsibility statement. **Classification:** static/app/managed CMS MVP candidates only if operations and unit economics are proven.

## 03. Cloud Infrastructure & Virtualization
**Product families:** VM, bare metal, GPU, VPC/network, block/object storage, images, snapshots, firewall, load balancer, IP allocation, cloud governance, managed infrastructure and migration. Clarify broker/orchestrator versus actual infrastructure operator.

**Lifecycle:** project/environment → quota/region check → network/security design → approval → provision → verify → tag/meter → resize/snapshot/backup → maintain/incident → migrate → shutdown/delete/cost closure.

**Contract:** instance family/performance, region/zone, image provenance, network egress/IP costs, storage performance, GPU availability, quotas, maintenance, support and provider terms.

**Controls/failures:** project isolation, IAM/MFA, hardened images, metadata protection, encryption, policy-as-code, drift, quota/cost guardrails and audit. Handle capacity shortage, timeout after resource creation, duplicate resource, region outage, vulnerable image, quota race, runaway spend, failed resize and orphan resource.

**Acceptance:** provider/region/pricing matrix, lifecycle tests, IAM isolation, policy/drift checks, metering accuracy, recovery and cost controls. **Classification:** control plane/cost visibility are core; infrastructure offers partner-dependent until capacity and contracts verified.

## 04. Containers, Kubernetes & Runtime
**Product families:** registry, build/cache, container runtime, managed container apps, Kubernetes clusters/control plane, node pools, ingress, GitOps, secrets/config, policy and managed operations.

**Lifecycle:** project → registry → build/sign/scan → environment/cluster → policy/secrets → deploy → health gate/rollout → autoscale → patch/upgrade → backup/restore → incident/decommission.

**Contract:** supported versions, node types, CNI/CSI/ingress, upgrade cadence, control-plane responsibility, workload limits, storage, egress, registry retention and support.

**Controls/failures:** namespace/workload isolation, RBAC, admission policy, signed images/SBOM, network policy, secret injection, runtime detection, etcd backup and upgrade rehearsal. Handle image pull, bad rollout, node pressure, CNI/CSI failure, certificate expiry, control-plane outage, secret rotation and failed upgrade.

**Acceptance:** version matrix, secure baseline, conformance, image provenance, isolation, upgrade/rollback, restore and metering. **Classification:** managed app runtime candidate; Kubernetes advanced/partner-dependent until SRE capacity exists.

## 05. Networking & Connectivity
**Product families:** VPC/VNet, subnet/IPAM, firewall/security groups, site-to-site/remote VPN, private links, load balancing, DNS routing, traffic management, network monitoring and managed operations. Do not silently merge the separate Wi-Fi management project.

**Lifecycle:** topology discovery → requirements/risk → IP plan → change proposal → approval/window → deploy → connectivity tests → monitor → rollback/change → incident/decommission.

**Contract:** IP ranges, routing, throughput/latency assumptions, regions/PoPs, carrier/provider, VPN limits, encryption, redundancy, maintenance and support.

**Controls/failures:** segmentation, deny-by-default, route filtering, key rotation, management-plane isolation, config backup, flow logs and emergency rollback. Handle overlapping CIDR, route leak, expired tunnel key, asymmetric routing, DNS mismatch, MTU, saturation and partial config push.

**Acceptance:** topology/ownership diagrams, approved config diff, reachability/performance tests, failover, secure review and rollback evidence. **Classification:** inventory/change workflows core candidates; connectivity products geography/provider-dependent.

# Group B — Data, communications and financial rails

## 06. Database Services
Managed database products by explicitly supported engine/version/topology; provisioning; migration; backup/PITR; performance and DBA service. Lifecycle: choose engine/region/HA → capacity/security → provision → credentials/network → migrate → verify → monitor → scale/upgrade → restore/failover → export/decommission. Contract engine/extensions, compute/storage, connection limits, HA, backup/PITR window, maintenance, encryption and DBA/customer responsibility. Controls: private network, TLS, scoped identities, rotation, audit, patching, pooling and restore drills. Failures: connection exhaustion, lag, extension mismatch, migration drift, accidental deletion, corrupt backup, upgrade/failover failure. Acceptance: provisioning, least privilege, restore/PITR, failover, performance and migration evidence.

## 07. Storage, Backup & Disaster Recovery
Products: object/block/file/archive, lifecycle tiers, immutable backup, replication, restore orchestration and DR planning. Define storage class, durability claims source, egress/request costs, encryption, retention, immutability, legal hold, regions, measured RPO/RTO and restore limits. Lifecycle: discover → classify → approve policy → configure → first backup/integrity verify → monitor → restore drill → declare recovery → sequence restore → validate/failback → delete by policy. Protect backup credentials separately; test key recovery; use immutable copies where supported. Failure cases: silent backup failure, corruption, key loss, bad retention, replication lag, dependency unavailable, ransomware and egress shock. Acceptance requires restore proof and measured recovery, not merely a successful backup job.

## 08. Email Infrastructure
Products: business mailbox, domain setup, transactional API/SMTP, campaigns, inbound security, archive/retention, migration and deliverability advisory. Lifecycle: domain verification → SPF/DKIM/DMARC setup → sender/mailbox → consent/limits → test → send → bounce/complaint/suppression → reputation → renewal/offboarding. Define mailbox/storage/message quotas, sender requirements, retention, region and support. Controls include MFA, anti-spoofing, suppression/opt-out, abuse limits and credential rotation. Failures: DNS auth, throttling, reputation block, queue backlog, duplicate send, webhook delay, compromise and migration loss. No guaranteed inbox placement. Acceptance: authenticated test, event handling, suppression, security and export proof.

## 09. SMS, Voice & Omnichannel Communication
Products: SMS/OTP, transactional/bulk SMS, sender IDs, voice/IVR/virtual numbers, WhatsApp Business/push only after approval, unified routing/reporting. Lifecycle: eligibility → sender/channel approval → consent/templates → credentials → sandbox → live approval → send/call → delivery callback → retry/fallback → reconciliation/offboarding. Define country/destination, throughput, encoding/segments, sender approval, receipts semantics, number rental, template rules and price. Controls: OTP pumping/toll fraud protection, rate limits, consent/opt-out, signed callbacks, idempotency and destination restrictions. Failures: provider accepted but delivery failed, delayed/out-of-order receipt, sender rejection, duplicate retry, unsupported destination, outage, number reassignment. Acceptance: country/provider evidence, sandbox/live separation, event mapping, anti-abuse and reconciliation.

## 10. Payment Infrastructure, Billing & Fintech Integrations
Products: provider integrations, checkout, payment intents/status, invoices/receipts, subscriptions/usage billing, Control Number Management, refunds/reversals and reconciliation. TEKORA must not claim bank, licensed processor, custodian or government collection authority without proof.

Keep independent linked lifecycles for order, invoice, payment attempt/transaction, control number, subscription, entitlement, usage, refund/reversal, settlement and ledger. Control Number lifecycle: requested → provider-created/pending → assigned to bill/customer/expiry → active → paid/partial/overpaid/unmatched where provider supports → expired/cancelled/renewed → reconciled/closed. Store immutable internal ID, provider reference, payer/bill mapping, amount/currency, expiry and provenance. Do not invent universal control-number APIs.

Financial flow: quote → order → invoice → payment initiation → pending/confirmed/failed/expired/reversed → entitlement decision → receipt → settlement import → gross/fee/net reconciliation → exception/adjustment approval. Verify status via authenticated provider evidence, never screenshot. Controls: signed callbacks, replay protection, idempotency, provider query, secrets, audit, segregation of duties, dual approval and sandbox/live isolation. Failures: delayed/duplicate/out-of-order webhook, timeout after success, wrong mapping, partial/overpayment, expiry, renewal collision, reversal after activation, unmatched settlement and currency mismatch. Acceptance: contract/legal review, scenario tests, signature/replay/idempotency, lifecycle mapping and reconciliation proof. Tanzania provider, bank/mobile-money, control-number, tax and regulatory pathways require current authoritative validation. No live money without separate explicit approval.

# Group C — Developer, delivery, security, intelligence and media

## 11. Developer Tools & API Infrastructure
API catalogue, workspaces/projects, gateway, credentials/scopes, sandbox, webhook console, SDK/CLI, docs/versioning, usage/quotas. Journey: create project → select API/scopes → sandbox key → test → inspect request/error → webhook simulator → usage → live access request/approval. Define version, auth, scopes, rate/quota, idempotency, errors, pagination, signature/retry/replay and deprecation. Protect one-time secrets, rotate/revoke, isolate environments, redact PII. Test credential leakage, duplicate webhook, breaking schema, quota, provider timeout and replay. Acceptance: OpenAPI/contract tests, deterministic sandbox, webhook tests, tested SDK examples and secret lifecycle.

## 12. Software Development, DevOps & Deployment
Repository integration, CI/build/test, runners, preview environments, deployments, IaC, artifact registry and managed DevOps. Lifecycle: authorize repo → configure env → pipeline → build/test/scan → provenance → approval → deploy/health gate → monitor/rollback → release record. Define runner isolation, supported runtimes, minutes, artifact retention, regions, secrets, concurrency and ownership. Controls: minimal repo scopes, ephemeral runners, protected environments, signed artifacts, SBOM, secret/dependency scanning and IaC policy. Failures: malicious dependency/pipeline, runner escape, leaked secret, partial deploy, migration incompatibility and rollback failure. Acceptance: sample pipeline, runner isolation, signature verification and rollback rehearsal.

## 13. Cybersecurity & Information Security
Products: posture assessment, vulnerability management, authorized penetration testing, cloud/container/API security, WAF/endpoint/SIEM integrations, managed detection/response and governance advisory. Every engagement needs written authorization, asset scope/ownership, exclusions, test window, safe limits, emergency stop, contacts, evidence handling and retention. Secure evidence, minimize collection, preserve chain of custody, disclose severity rationale and escalation. Handle out-of-scope impact, instability, sensitive data exposure, scanner overload, false positives and evidence leakage. Acceptance: signed scope, reproducible evidence, impact-safe logs, remediation verification. Assessment is not certification.

## 14. Monitoring, Observability & SRE
Products: metrics/logs/traces, synthetic checks, uptime, alerts, incidents, SLO/error budgets, status page and managed SRE. Lifecycle: onboard → telemetry/PII policy → configure → validate → dashboards/alerts → test alert → incident/communications → resolve/postmortem → retention/decommission. Define sampling, retention, quotas, region, cardinality, escalation and SLO. Controls: tenant isolation, secret/PII scrubbing, RBAC, audit and secure agents. Failures: missing telemetry, noisy alerts, cardinality explosion, clock skew, ingestion lag, alert outage and false green. Acceptance: synthetic fault, alert delivery, redaction, isolation and runbooks. Observed availability is not contractual SLA.

## 15. AI, ML & Automation Infrastructure
Products: model gateway/catalogue, inference, embeddings/RAG, training/fine-tuning, evaluation/registry, agent/workflow runtime. Lifecycle: use-case/data review → provider/region/retention check → project/key/quota → model/prompt version → evaluation → sandbox → approval → deploy → quality/cost/safety monitor → rollback. Define model/version/modality/context/rate/price/region/retention/training terms/fallback. Controls: prompt-injection defense, retrieval ACL inheritance, secret isolation, output validation, tool allowlists, human approval for consequential actions and provenance. Failures: hallucination, stale retrieval, cross-tenant leakage, retention mismatch, model retirement, cost runaway and unsafe tool call. Acceptance: grounded-answer, ACL, adversarial, approval, budget and version-traceability tests.

## 16. Media, Video & Realtime Infrastructure
Products: upload/processing, image transforms, VOD/live, CDN, WebRTC rooms, TURN/SFU integration, recording/transcription/captions and QoE. Lifecycle: authorize/consent → upload/room allocation → process/connect → playback/participants → recording if enabled → retention/export/delete. Define codec, resolution, bitrate, concurrency, region, egress, latency, participant roles, provider responsibility and retention. Controls: signed uploads/playback, short-lived room tokens, consent/recording indicators, encryption and private storage. Failures: interrupted upload, transcode, playback stall, TURN capacity, network degradation, corrupt recording, token leak and egress spike. Acceptance: resume, playback matrix, network impairment, room authorization, recording integrity and consent tests.

# Group D — Data, business, connected systems, trust and distribution

## 17. Data Engineering & Analytics
Products: connectors, batch/stream/CDC, transforms, orchestration, warehouse/lake, data quality, catalogue/lineage and governed BI. Lifecycle: source authorization → classification/purpose → connector → schema map → ingest → validate/transform → publish → freshness/quality monitoring → replay/backfill → export/delete. Define source permissions, freshness, schema evolution, volume, retention, residency, cost and ownership. Controls: least-privilege source accounts, masking, row/column access, consent, tenant isolation and deletion propagation. Failures: schema drift, duplicate CDC, late data, checkpoint loss, stale dashboard and failed deletion. Acceptance: data contracts, lineage, quality, replay, permission and deletion tests.

## 18. Business Applications & Digital Productivity
Products: TEKORA-built apps, managed open-source, third-party SaaS/integrations; CRM/ERP/HRM/project/collaboration/document workflows. Lifecycle: publisher validation → tenant setup → license/seats → SSO/integration → migration/configuration/training → support/update → renewal → export/offboarding. Define publisher, rights, terms, seats, features, region, API limits, support owner, update and export. Controls: SSO/MFA, consent scopes, vendor access, audit and token revocation. Failures: publisher discontinuation, terms/price change, API retirement, incomplete export, seat overage and identity sync failure. Acceptance: rights evidence, license check, integration and offboarding rehearsal.

## 19. IT Consulting, Managed IT & Professional Services
Products: discovery/architecture, software delivery, cloud/network operations, managed IT, security advisory, migration, retainers and training. Lifecycle: lead → discovery → scope/assumptions → proposal/quote → contract/authorization → kickoff → milestones → change control → acceptance → handover → support/closure. Define deliverables, exclusions, milestones, staffing, support hours, customer dependencies, access, IP, confidentiality, subcontracting, warranty and expenses. Controls: time-bound access, customer approval, change windows, backup, peer review, evidence and revocation. Failures: scope creep, customer delay, access block, migration failure, change rollback and dispute. Acceptance: signed scope, milestone/test evidence, change approvals, handover and access revocation.

## 20. IoT, Smart Systems & Connected Infrastructure
Products: device registry/onboarding, MQTT, fleet, telemetry, OTA, rules/automation, digital twins and vertical solutions only after safety analysis. Lifecycle: claim → unique identity/certificate → provision → connect → validate telemetry → configure → staged OTA → monitor/maintain → transfer/decommission. Define models/firmware, protocols, carrier, offline behavior, OTA, power, safety and warranty. Controls: per-device identity/ACL, signed firmware, staged rollout/rollback, key revocation, command allowlists and human override. Failures: clone, credential compromise, offline device, duplicate telemetry, unsafe command, bricked OTA and broker outage. Acceptance: identity, ACL, offline, OTA rollback and safety tests.

## 21. Digital Trust, Compliance & Identity
Products: customer/workforce IAM, SSO/MFA, privileged access, verification integrations, PKI/certificates, signing, privacy requests and compliance evidence. Lifecycle: source/assurance selection → consent/legal basis → enrollment/proofing → authentication → authorization → review/renewal → suspension/recovery → export/deletion. Define assurance, source, jurisdiction, false-match process, certificate/key custody, signature status, retention and provider role. Controls: phishing-resistant MFA where possible, secure recovery, least privilege, key protection and lifecycle deprovision. Failures: false match, provider outage, recovery takeover, expired certificate, key compromise and deletion/retention conflict. Acceptance: source/assurance disclosure, authz/recovery/certificate/privacy tests. Proofing, authentication, authorization and legal signature are distinct.

## 22. Licensing, Software Distribution & Digital Products
Products: publisher onboarding, package/download distribution, trials, subscription/perpetual/seat/device/floating licensing, activation/renewal/revocation and updates. Lifecycle: rights verification → artifact security review → listing → purchase → entitlement → activation → renewal/seat change → transfer/revoke → offline grace/recovery → retirement/takedown. Define publisher rights, OS/version, license metric, activation limit, offline behavior, grace, support/update entitlement, territory, refund and privacy. Controls: signed artifacts, SBOM, malware scanning, token protection, activation abuse detection and privacy-minimal telemetry. Failures: duplicate activation, clock rollback, offline revocation limit, rights dispute, malicious update, key leakage and entitlement mismatch. Acceptance: rights evidence, signature verification, state tests, offline disclosure and takedown runbook.

# Cross-category platform contracts
1. One person/customer/organization/workspace/project/environment/resource ownership model and tenant isolation.
2. Separate category, product, SKU, provider offer, region and price version.
3. Order/provisioning orchestration with idempotency, compensation, retries, reconciliation and manual exception queue.
4. Separate linked order, invoice, payment, subscription, entitlement, usage, control-number, refund/reversal and settlement records.
5. Provider adapters expose capability, region, auth, quota, rate limit, sandbox/live, webhook semantics, contract and outage without pretending all providers are identical.
6. Central secrets lifecycle, rotation, revocation, masking and audit.
7. Versioned events with correlation/causation IDs, idempotency, ordering assumptions, retries, DLQ and safe replay.
8. Unified support/incident linking customer, resource, provider, severity, timeline and evidence.
9. Metering records source, unit, interval, late/corrected data, estimate/actual, price version and dispute.
10. Localization: Swahili/English, TZS and verified currencies, Africa/Dar_es_Salaam display where appropriate, UTC storage.
11. Data ownership, purpose, classification, region, retention, export, deletion and legal hold.
12. Distinguish observed provider state, TEKORA operational state and contractual SLA.

## Mandatory global failure tests
Duplicate order; timeout after upstream success; delayed/out-of-order webhook; provider outage/rate limit; expired/rotated credential; partial provisioning; resource exists; quota/capacity exhaustion; cancellation mid-provision; payment delay/reversal after entitlement; renewal failure; downgrade with overage; migration interruption; corrupt backup/restore failure; tenant breach; security incident; manual correction; provider contract termination; export/deletion failure; clock skew; event replay; price change mid-term.

## Remaining discovery deliverables
Customer demand evidence; country/provider/contract matrix; legal/tax review; SKU/price/cost/margin; state and sequence diagrams; API/event schemas; data model/retention; acceptance tests/runbooks; support/SLA capacity; UX prototypes/usability evidence; prioritized MVP and deferred scope.

**Conclusion: PARTIAL.** This deepens all 22 category baselines; it does not prove demand, provider access, prices, legal eligibility, capacity, SLAs or implementation. Discovery remains open and implementation is not authorized.
