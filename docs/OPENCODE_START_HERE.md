# TEKORA — OpenCode Start Here

**Purpose:** One unambiguous entry point for an OpenCode session. This is a navigation and execution guide; canonical product requirements remain in the linked source documents.

## Before anything else

1. Open repository root and confirm branch, HEAD, remotes and working-tree status.
2. Read `AGENTS.md` completely.
3. Read `README.md` completely.
4. Read `MASTER_IMPLEMENTATION_PROMPT.md` completely.
5. Read `docs/MASTER_PLATFORM_BLUEPRINT.md` completely.
6. Read `docs/IMPLEMENTATION_EXECUTION_PLAYBOOK.md`, `docs/TECHNICAL_DECISION_REGISTER.md` and `docs/ENGINEERING_ENVIRONMENT_AND_OPENCODE_RUNBOOK.md`.
7. Read the relevant category deep dives, architecture contracts, design system, provider due diligence, discovery addendum and all linked reports.
8. For catalogue/pricing work, read `docs/MASTER_SKU_PRICING_CATALOGUE.md`, `docs/PRODUCT_CATALOGUE_SKU_PRICING_FRAMEWORK.md`, `docs/COMPETITOR_PRICING_BENCHMARK_MATRIX.md`, `docs/SKU_LEVEL_COMPETITIVE_PRICING_WAVE_01.md`, `docs/SKU_LEVEL_COMPETITIVE_PRICING_WAVES_02_04.md`, plus Wave 02 and Wave 03 summaries.

## Required first command

Run `/tekora-start`. It is the canonical first-session bootstrap: it reads this guide and the mandatory project documents, then performs the read-only Phase 00 audit. If you intentionally start without the bootstrap command, run `/tekora-audit` manually. The audit must inspect the actual full repository tree and current working tree; do not rely on historical claims. The 26 November 2026 GitHub tree snapshot was documentation/configuration only (no application source, package/build manifests, migrations, tests or CI workflow). Re-check because the checkout may have changed.

The audit must produce an evidence-based Phase 00 report. It must identify existing work, missing source/runtime prerequisites, documentation conflicts, security risks and exact next actions. It must not implement code.

## Controlled progression

- Use `/tekora-prepare Phase 01` only after the owner accepts the Phase 00 audit.
- Prepare and execute only one approved phase at a time.
- Do not begin Phase 01 or implementation solely because the docs are ready. Obtain explicit owner approval for the next phase and bounded scope.
- Within an approved phase, parallelize only independent tasks with file/module ownership, contracts and dependency boundaries.
- Use `/tekora-implement <approved work package>` only after the approval is recorded.
- Use `/tekora-verify <scope>` independently after implementation.

## Non-negotiable preservation and safety

- Do not delete, overwrite, simplify or silently replace existing requirements or user work.
- No fabricated data, test results, supplier costs, prices, screenshots, commits, provider approvals or production claims.
- Never treat proposed architecture or a market benchmark as an approved decision.
- No real payment, control-number collection, production provider provisioning, paid cloud resource, domain registration, DNS change, bulk customer message, public deployment or external security test without separate explicit approval.
- No force push, destructive migration, secret exposure or production data modification.
- Use sandbox/test providers first and record exact evidence.
- Update README (actual state), Blueprint (requirement traceability), module documentation and a dated report after each approved phase.
- Distinguish DONE, PARTIAL, MISSING, BROKEN, BLOCKED and NEEDS VERIFICATION.
- A phase is not complete until acceptance criteria, tests, security, documentation and evidence are verified and the owner accepts its gate.

## Definition of a good first session

Deliver a Phase 00 audit report and a prioritized Phase 01 preparation recommendation. Do not start implementation in the first session unless the owner explicitly approves it after reviewing the audit.
