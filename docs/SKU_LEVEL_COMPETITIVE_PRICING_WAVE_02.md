# TEKORA SKU-Level Competitive Pricing — Wave 02 (Categories 03–08)
**Snapshot:** 26 November 2026 · **Status:** Provisional research and pricing hypotheses; not an approved price list.

## 03 — Cloud Infrastructure & Virtualization
**Tanzania public anchors:** Moinfo: 1 GB/25 GB/1 TB TZS 19,500/mo; 2 GB/50 GB/2 TB TZS 47,000; 4 GB/80 GB/4 TB TZS 94,000; 8 GB/160 GB/5 TB TZS 187,500; 16 GB/320 GB/8 TB TZS 374,500 (https://moinfo.co.tz/vps). Mamdali: 1 GB/25 GB/1 TB TZS 35,000; 2 GB/50 GB/2 TB TZS 45,000; 4 GB/80 GB/4 TB TZS 60,000 (https://mamdali.co.tz/vps-hosting/). Continuum: cloud tiers from TZS 60,000 for 4 GB/50 GB/4 TB, TZS 100,000 for 8 GB/100 GB/8 TB, TZS 150,000 for 16 GB/200 GB/16 TB (https://continuum.co.tz/). Lineserve cloud entry from TZS 27,780/month for 1 vCPU, 1 GB, 20 GB SSD and IPv4 (https://www.lineserve.co.tz/pricing).
| SKU | Spec/unit | Provisional target hypothesis |
|---|---|---|
| CLOUD-VM-1G | 1 vCPU, 1 GB, 20–25 GB, ~1 TB | TZS 19k–27k/mo subject to exact parity |
| CLOUD-VM-2G | 1 vCPU, 2 GB, 50 GB, 2 TB | TZS 42k–46k/mo |
| CLOUD-VM-4G | 2 vCPU, 4 GB, 80 GB, 4 TB | TZS 56k–90k/mo; compare allocation/location |
| CLOUD-VM-8G | 4 vCPU, 8 GB, 160 GB, 5–8 TB | TZS 90k–120k/mo hypothesis |
| CLOUD-VM-16G | 6 vCPU, 16 GB, 200–320 GB | TZS 150k–340k/mo hypothesis |
| CLOUD-DEDICATED-CPU | dedicated CPU | premium/quote |
| CLOUD-IPV4 | IP/month | validated pass-through |
| CLOUD-EGRESS | GB | allowance + metered overage |
| CLOUD-SNAPSHOT | GB-month | cost-based |
| CLOUD-MANAGED | instance/month | management/support priced separately |
Free: limited sandbox credits/instance with expiry, not unrestricted compute. Compare CPU contention, region, IP, egress, backups, licensing, VAT and support.

## 04 — Containers, Kubernetes & Runtime
SKU list: K8S-CONTROL-PLANE (cluster/month); K8S-WORKER (node-hour); K8S-CPU (vCPU-hour); K8S-MEMORY (GB-hour); K8S-REGISTRY (GB-month+ops); K8S-BUILD (runner-minute); K8S-EGRESS (GB); K8S-MANAGED (cluster/month). Provider cost plus management/operations, region/topology explicit. Free build/preview quotas only, not production clusters. Quotes needed for network/load balancers, storage, egress, security and support/on-call.

## 05 — Networking & Connectivity
| SKU | Basis |
|---|---|
| NET-INTERNET-ACCESS | site/month by technology, bandwidth, contention, SLA, installation |
| NET-DEDICATED-INTERNET | committed Mbps/month, IPs, installation |
| NET-VPN-SITE | tunnel/site/month |
| NET-SD-WAN | site/month + hardware |
| NET-FIREWALL-MANAGED | device/month + licenses/operations |
| NET-WIFI-MANAGED | AP/site/month + installation |
| NET-CABLING | scoped materials/workmanship quote |
| NET-ONSITE | engineer visit/day + travel |
| NET-IP | authorized provider schedule |
Quote-only: geography, operator coverage, last-mile, regulatory status, SLA, installation and hardware. Free assessment/lab only, not connectivity.

## 06 — Database Services
SKU: DB-DEV (sandbox); DB-STARTER/STANDARD (instance-month compute+storage); DB-HA (primary/replica); DB-BACKUP/PITR (storage/retention); DB-MIGRATION (scope); DB-MANAGED (support). Benchmark: Supabase Free 500 MB DB/5 GB egress and Pro from $25/month (https://supabase.com/pricing). Normalize engine, vCPU/RAM, storage, IOPS, backup, PITR, connections, HA, region, egress. Free development tier only; no production SLA. Validate restore, security, data residency, maintenance and support.

## 07 — Storage, Backup & Disaster Recovery
SKU: OBJ-STANDARD (GB-month+ops); OBJ-ARCHIVE (GB-month+retrieval); BLOCK-STORAGE (GB-month+IOPS); FILE-STORAGE (GB-month+throughput); BACKUP-PROTECTED (GB protected/month); BACKUP-RETENTION (GB-month); RESTORE (job/GB); DR-ESSENTIAL (workload/month with RPO/RTO); DR-TEST (engagement). Cloudflare R2 Standard published $0.015/GB-month and 10 GB-month free; operations separate (https://www.cloudflare.com/products/r2/). Price by retention, restore performance, egress and recovery objective. No backup promise without tested recovery.

## 08 — Email Infrastructure
SKU: MAILBOX-STARTER/BUSINESS (seat/month); MAIL-ARCHIVE (seat/GB-month); MAIL-TRANSACTIONAL (1k sends); MAIL-MARKETING (contacts+sends); MAIL-DEDICATED-IP (IP/month+warmup); MAIL-MIGRATION (project); MAIL-DNS-SETUP (domain); MAIL-SECURITY (seat/month). Zoho pricing is regional/term-specific (https://www.zoho.com/workplace/plan-comparison.html); Amazon SES first Essentials tier $0.16/1,000 emails (https://aws.amazon.com/ses/pricing/). Separate mailbox from transactional sending. Sandbox only; no unlimited sending/storage or deliverability SLA. Validate region, reseller rights, reputation, tax and support.

## Approval gates
Written supplier quotes; exact specification normalization; dated price capture; tax/FX; fully loaded cost/margin floor; security/operational responsibility; quota alerts; invoice tests; effective-dated approval. **Wave 02 status:** categories 03–08 mapped; networking, Kubernetes, managed DB, DR and email details remain quote-dependent.
