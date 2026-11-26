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


## Original-intent reconciliation

The Blueprint now includes **Section 24 — Original-idea reconciliation and completeness requirements**. It explicitly preserves the originating service proposition (hosting, web/software development, server/website essentials, payment gateway provisioning, email and SMS), the company-as-platform-operator distinction, all-22-category long-term scope, candidate audiences, full service lifecycle, Tanzania control-number safeguards, OpenCode/v0/Figma responsibilities, discovery-before-specification sequence and deferred Wi-Fi/ownership topics.

This is a documentation reconciliation against the planning context available to this session, not a verbatim transcript or a claim that every future requirement has been discovered. See Blueprint Sections 21 and 24 for pending validation and open decisions.

## Additional recovered planning requirements

Blueprint Section 25 records additional requirements from the earliest planning context: secure/feasible technology breadth; connected control-plane engines and service dependencies; organization/project/environment IAM and secrets; developer API/sandbox/webhook/SDK experience; safe automated provisioning; provider abstraction and realistic failover/portability; full internal operations and professional-service project tracking; commercial and Tanzania localization requirements; and candidate differentiators such as visual infrastructure mapping, AI diagnostics, cost optimization and automation.

These are not all approved MVP features. Explicit requirements, assistant proposals and pending validation remain separately classified. Implementation must not start until the traceability and approval gate in Blueprint Section 25.11 is satisfied.

## Category implementation depth

The authoritative Blueprint now includes Section 26, an implementation-oriented specification for each of the 22 service categories. It defines product families, functional scope, workflows, data/integration boundaries, security/operations and acceptance expectations, plus an 18-point mandatory specification contract, cross-category dependency rules and category implementation exit gate. Read Section 26 before planning any category implementation; the short catalog is not sufficient on its own.

## Second-pass category analysis

The Master Blueprint Section 27 expands the 22 categories into candidate product workstreams and adds platform-wide consistency checks, failure/edge-case analysis, release classification and evidence standards. Section 27.8 explicitly records the current outcome as PARTIAL: final SKUs, provider/legal validation, detailed state machines, API/data contracts, pricing and product acceptance remain discovery work. Do not describe these as completed or start implementation based on the catalog alone.


## Full 22-category deep dive

See [Category Deep Dive — All 22 Services](docs/CATEGORY_DEEP_DIVE_22_SERVICES.md). It expands each category into candidate product families, lifecycle, data/contracts, security, failure modes and acceptance evidence. This is still a discovery baseline; providers, legal eligibility, prices, demand, SLAs and operational capacity remain to be verified.

## Global design system, color and UX

See [Design System — Color, Typography & UX](docs/DESIGN_SYSTEM_COLOR_TYPOGRAPHY_UX.md). The global design system is mandatory across the public marketplace, customer portal, developer hub and internal operations. It covers the proposed palette, category accents, Light/Dark/System themes, typography candidates and specimen tests, information architecture, components, interaction states, WCAG 2.2 AA target and design approval gates. Color values and font candidates are provisional until contrast, licensing, language and performance checks pass.


## Further discovery deliverables

- [Provider, Country & Integration Due Diligence](docs/PROVIDER_COUNTRY_INTEGRATION_DUE_DILIGENCE.md) — public evidence, Tanzania-specific gates, candidate providers and required commercial/legal checks.
- [Product Catalogue, SKU & Pricing Framework](docs/PRODUCT_CATALOGUE_SKU_PRICING_FRAMEWORK.md) — catalogue hierarchy, SKU contract, billing/metering models and MVP hypotheses.
- [Architecture, API, Event & Data Contracts](docs/ARCHITECTURE_API_EVENT_DATA_CONTRACTS.md) — bounded contexts, API conventions, independent financial state machines, event envelope and data governance.
- [Color, Typography & UX Validation](docs/COLOR_TYPOGRAPHY_UX_VALIDATION.md) — preliminary light-theme contrast calculation, teal warning, font evaluation, prototype scope and usability acceptance.

All are discovery baselines. Provider approval, commercial terms, legal opinions, final pricing, final font selection, full theme contrast and user testing remain open.


## Comprehensive discovery addendum — preserved and expanded scope

The additive register in [Comprehensive Discovery Addendum](docs/COMPREHENSIVE_DISCOVERY_ADDENDUM.md) establishes shared platform requirement IDs (PLT-001–PLT-024), parent requirement IDs for **all 22 categories (CAT-01–CAT-22)**, a child-ID convention, mandatory traceability fields, independent order/provisioning/payment/control-number/invoice/subscription/entitlement/usage/settlement/resource/incident state machines, cross-category workflow catalogue, shared API/data contract baseline, logical entity inventory, provider evidence classes (E0–E5), candidate provider due-diligence matrix, UX information architecture and screen acceptance inventory, MVP scoring method, 35 mandatory test scenarios, risk register (RSK-001–RSK-026), and open decisions (DEC-001–DEC-014).

**Additive preservation rule:** this addendum does not replace or shorten the existing Blueprint, category deep dive, provider research, SKU/pricing, architecture, design-system or validation documents. All 22 categories remain in long-term scope even if a future MVP excludes some. Requirements and decisions must be versioned; do not silently delete or rewrite user-originated scope.

**Current state remains discovery only.** Requirement child mappings, approved MVP SKUs, provider E2–E5 evidence, legal classification, final data/API schemas, prototypes, usability research, executable tests and formal phase approvals remain incomplete. No implementation or production capability is claimed.
