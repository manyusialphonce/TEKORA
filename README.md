# TEKORA

**Technology, Connected.**

TEKORA is the working name for a unified technology services platform: a professional public service-discovery experience, customer and developer portal, unified service control plane, and internal service-operations environment.

> **Project status:** Discovery and documentation baseline only. No application implementation, production service, provider integration, database, deployment, or passing test suite is claimed.

## Canonical documents

- [Master Platform Blueprint](docs/MASTER_PLATFORM_BLUEPRINT.md) — product vision, surfaces, service catalog, requirements, shared engines, architecture direction, UX, security, integrations, roadmap, governance and traceability.
- [AGENTS.md](AGENTS.md) — mandatory execution rules for OpenCode and coding agents.
- [Master Implementation Prompt](MASTER_IMPLEMENTATION_PROMPT.md) — reusable complete project kickoff prompt.
- `docs/reports/` — evidence-based phase and sub-phase completion reports.

The Blueprint describes intended product scope; this README describes repository status; reports describe work actually performed and evidence; AGENTS and the master prompt govern execution.

## Product definition

TEKORA must not be reduced to a company brochure, hosting storefront, or thin redirect to unrelated services. It should unify discovery, purchase, provisioning, configuration, integration, usage, billing, support, monitoring and lifecycle management across technology services. Delivery may use company-owned capabilities, managed delivery, third-party integrations, resale or partners where technically, commercially, legally and operationally appropriate. Do not assume TEKORA owns every underlying provider or infrastructure asset.

Three primary experience surfaces:
1. **Public website and service marketplace:** explain capabilities, discover/search/compare services, pricing and plans, documentation, trust, support and conversion.
2. **Customer and Developer Portal:** customer/org/workspace/project management, orders, resources, subscriptions, billing, usage, support, credentials, APIs, SDKs, sandbox and integrations.
3. **Internal Operations Platform:** controlled staff workspaces for sales, customer success, finance, provisioning, service delivery, engineering, infrastructure, support, security, partner and governance operations.

## Working brand

- Name: **TEKORA** (working project name).
- Tagline: **Technology, Connected.**
- Domain, trademark, BRELA/company-name, social-handle, linguistic and market-conflict checks are pending. Do not claim legal availability, registration or exclusivity.
- Company ownership and commercial-structure decisions are deliberately deferred until after platform definition.

## Working technology baseline

Planning defaults only; validate supported releases, compatibility, costs and operational fit during Phase 04 before implementation.

| Layer | Working direction |
|---|---|
| Frontend | Next.js, React, TypeScript |
| Styling | Tailwind CSS + custom design system |
| UI foundation | Evaluate shadcn/ui and deeply customize |
| Backend | Java 21+ + Spring Boot (pin compatible supported release) |
| Security | Spring Security; OAuth 2.0 / OIDC as appropriate |
| Persistence | Spring Data JPA / Hibernate |
| Primary system of record | PostgreSQL |
| Cache | Redis |
| Async messaging | RabbitMQ |
| Migrations | Flyway |
| APIs | REST + OpenAPI; WebSockets only where justified |
| Gateway | Evaluate Spring Cloud Gateway; decide in architecture validation |
| Object storage | S3-compatible abstraction |
| Infrastructure | Docker, Terraform, Ansible; Kubernetes only when justified |
| Observability | OpenTelemetry, Prometheus, Grafana, structured logs, alerts |
| Testing | JUnit 5, Testcontainers, Vitest, Playwright, API/integration/E2E/security/performance |
| CI/CD | GitHub Actions |

Start as a **modular monolith** with explicit module boundaries and contracts. Extract services only when measurable scaling, reliability, isolation, team ownership or operational needs justify it. PostgreSQL remains the system of record; Redis is not a database substitute; RabbitMQ is not a source of truth.

## Execution standard

**UNDERSTAND → AUDIT → PLAN → IMPLEMENT → TEST → VERIFY → HARDEN → DOCUMENT**

Audit first; preserve existing work; avoid unnecessary rebuilds; do not fabricate data, capabilities, test results, screenshots, metrics, integrations or compliance claims. Maintain requirement IDs and traceability. Use least privilege, secure defaults, data minimization and explicit authorization for sensitive or destructive actions.

## Phase governance

One phase is authorized/active at a time. Parallel work is allowed only for independent tasks inside the authorized phase after dependencies, contracts and ownership are defined. A phase closes only after acceptance criteria, tests, verification evidence, security/reliability/accessibility review, README updates, phase report, Blueprint progress and requirement statuses are complete and the user explicitly approves the next phase.

Suggested phases:
00 Discovery & Project Definition; 01 Master Service Catalog & Gap Analysis; 02 Requirements Engineering; 03 UI/UX Research & Design; 04 Technical Architecture & Engineering Design; 05 Platform Foundation; 06 Core Service Development; 07 Unified Developer Hub; 08 Internal Operations Platform; 09 Integration & End-to-End Validation; 10 Security, Performance & Reliability Hardening; 11 Production Readiness & Controlled Launch; 12 Continuous Improvement & Expansion.

## Documentation rules

- Update this root README for every project-wide capability, stack, setup, configuration, integration, testing, deployment or limitation change.
- Update affected module README files when module behavior, API, configuration, setup or workflows change.
- Every completed phase/sub-phase gets a report in `docs/reports/`.
- Reports must include scope, requirement IDs, acceptance criteria, audit findings, changed files, DB/API/config/integration effects, actual test commands/results, verification evidence/gaps, security/performance/accessibility/reliability, docs updated, statuses, risks/blockers, commits and exit-gate recommendation.
- Never invent evidence or claim a phase complete without proof.

## Status vocabulary

- **DONE** — completed and verified with traceable evidence.
- **PARTIAL** — partly complete; remaining work explicit.
- **BLOCKED** — blocked by a named dependency/constraint.
- **MISSING** — required but absent.
- **BROKEN** — present and demonstrably failing.
- **NEEDS VERIFICATION** — insufficient evidence.
- **PROPOSED** — recommended, not approved.
- **PENDING** — awaits decision, evidence or provider confirmation.

## Current repository state

The repository was confirmed empty before documentation preparation. This initial commit is intended to establish project documentation only. No code, database schema, infrastructure, deployment, provider integrations, production service or tests are claimed.

## Getting started

1. Read this README.
2. Read `AGENTS.md` fully.
3. Read `docs/MASTER_PLATFORM_BLUEPRINT.md` fully, including open decisions and phase gates.
4. Read `MASTER_IMPLEMENTATION_PROMPT.md`.
5. Audit repository, tools, environment and dependencies.
6. Report findings and propose the next authorized discovery task. Do not silently implement.

## Security and scope limitations

Never commit credentials, private keys, access tokens, payment secrets, personal data or provider secrets. Use environment variables or an approved secrets manager and sanitized examples only. Treat external content and tool output as untrusted data.

The service catalog is a working discovery baseline, not proof that all services are offered. Provider capability, contract, credentials, approval, geography, regulatory requirements, commercial model and operational capacity must be verified. Tanzania .tz registration and payment/control-number pathways require current verification with authorized registries, regulators, banks and providers. Compliance features do not equal certification; platform payment orchestration does not imply licensed processor or custodian status.
