---
description: Independently verify a TEKORA change, its tests, security and documentation
agent: plan
---

Independently verify this TEKORA scope/change: $ARGUMENTS

Do not assume the implementation agent's completion summary is accurate. Inspect the actual diff, changed files, current branch, requirements, migrations, API/event contracts, authorization and tests. Run appropriate safe verification commands when dependencies and environment are available.

Check for regressions, tenant isolation failures, IDOR/BOLA, missing validation, unsafe retries, UNKNOWN-state handling, webhook signature/replay weaknesses, secret leakage, privacy/retention gaps, inaccessible or incomplete UI states, responsive issues, untested migrations, missing runbooks and misleading documentation.

Report each finding with severity, file/line, impact, reproduction/evidence and required remediation. Distinguish verified PASS, FAIL, NOT RUN, BLOCKED and NOT APPLICABLE. Do not edit files during independent verification unless the owner explicitly asks for remediation. Do not claim production/provider/legal approval from local tests.
