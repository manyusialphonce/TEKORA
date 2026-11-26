---
description: Audit the TEKORA repository and produce an evidence-based baseline without modifying application code
agent: plan
---

Perform the TEKORA Phase 00 repository and documentation audit.

Read AGENTS.md and all mandatory documents listed in docs/ENGINEERING_ENVIRONMENT_AND_OPENCODE_RUNBOOK.md. Inspect the actual Git working tree, current branch, remote refs, full recursive file inventory, recent commits, manifests, source files, tests, migrations, CI workflows, infrastructure and secret exposure risks. Compare the live checkout with the documentation-only baseline described in the runbook; do not assume it is still accurate.

Do not edit application code, install dependencies, change external services, create cloud resources, modify DNS, run production requests or delete/overwrite files. Do not infer missing content from filenames. If the audit needs a remote GitHub fetch, use read-only operations.

Create docs/reports/2026-11-26-PHASE-00-REPOSITORY-AUDIT.md only after collecting evidence. If a report with that exact name already exists, do not overwrite it; choose a new date/time suffix. Include inventory, branch/commit snapshot, docs review, source/build/test/CI status, gaps, security findings, decisions required, recommendations, exact commands and outputs, and statuses DONE/PARTIAL/BLOCKED/MISSING/BROKEN/NEEDS VERIFICATION. Do not claim tests were run if they were not.

Finish with a concise gate recommendation. Do not begin Phase 01 or implementation without owner approval.
