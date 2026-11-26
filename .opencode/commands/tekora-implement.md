---
description: Implement only a bounded TEKORA scope that has explicit approval
agent: build
---

Implement only this explicitly approved TEKORA work package: $ARGUMENTS

Before editing:
1. Read AGENTS.md and all relevant requirements, ADRs, phase reports and acceptance criteria.
2. Verify the exact approval and phase status in the repository/issue context. If approval is not recorded or the scope is ambiguous, stop and ask; do not infer approval from a previous unrelated task.
3. Re-audit the working tree and current branch. Preserve unrelated and uncommitted work.
4. Create/use a scoped feature branch; never force-push or rewrite shared history.
5. Plan file-level changes and identify migrations, external effects and rollback.

Implement the smallest complete vertical slice that satisfies the approved requirements. Follow existing conventions, add tests, update documentation, preserve module boundaries, enforce server-side tenant authorization and use mocks/sandboxes for external integrations unless live use is separately authorized.

Never spend money, create paid resources, register domains, modify production DNS, send real customer messages, process real payments, deploy publicly, change permissions or delete production data without separate explicit approval.

After implementation run formatting, lint/type/compiler checks, unit/integration/contract/E2E tests relevant to the change, security checks and diff review. Record exact commands and truthful outcomes. Update README, Blueprint requirement status and a dated report under docs/reports/. Do not mark a feature DONE when tests or required evidence are missing. Do not merge, push or release unless explicitly included in the approval.
