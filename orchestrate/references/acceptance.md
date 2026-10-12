# Acceptance and bounded recovery

## Verification plan

Choose checks from impact, uncertainty, and governing requirements. Record what
would establish acceptance before execution, including a stopping condition.

| Risk | Default evidence |
| --- | --- |
| Low: documentation, read-only research, non-behavioral edits | Inspect outputs, essential sources, and applicable lightweight checks |
| Medium: implementation or behavioral fixes | Inspect relevant complete diffs including new files; run focused behavior and interface checks |
| High: permissions, security, migration, destructive operations, cross-system contracts | Add applicable failure/regression, compatibility and data-integrity checks; independent review when feasible or required; required approvals |

If required independent review is unavailable, keep acceptance blocked. If review
is optional but unavailable, report the limitation and decide from concrete risk.
Risk does not weaken permissions, ownership, or isolation requirements.

## Check cadence and stopping rule

Treat a meaningful unit as a coherent behavior change, interface boundary, or
integration point whose failure could alter the next implementation decision.
Run focused verification there; reserve broad final checks for the integrated
artifact. Do not interrupt execution for ceremonial milestone reviews.

Maintain a compact check ledger: criterion, command or method, relevant artifact
revision, result, evidence path, and invalidation trigger. Reuse passing evidence
while relevant inputs and assumptions remain unchanged. A new task status or
context transition alone does not invalidate a check.

Stop checking when all required criteria have sufficient evidence and no concrete
material uncertainty remains. Do not broaden tests merely because earlier tests
passed. Broaden only when changed scope, failures, new evidence, or governing
requirements justify it. Optional enhancements do not block acceptance.

For each deliverable, inspect actual outputs and relevant changes, compare criteria,
and independently validate critical evidence. For read-only research, validate
sources rather than requiring a diff. Avoid reproducing every executor command;
reproduce critical checks needed for acceptance and distinguish executor-reported
results from independently verified results. Report skipped or unavailable checks.

After repairs, repeat affected checks and justified regression checks. Use final
checks against stable integrated artifacts; establish relevant writers stopped.

## Recovery

Return specific findings to the responsible executor using supported reassignment.
Reuse useful context or provide a replacement with the complete brief and artifacts.
Delegate fixes; do not implement them in the parent.

Retry with actionable evidence or a revised hypothesis. After repeated similar
failures, reassess assumptions, dependencies, ownership, and task boundaries.
Do not repeat an unchanged failed approach indefinitely. Preserve accepted work,
continue independent work, and escalate only blockers needing user decisions.

## Closure

Track agent status and acceptance separately; use host-supported states rather
than inventing enforced lifecycle semantics. Confirm required outputs, integration,
verification, agent status, and stopped modifying commands. Report deliverables,
key evidence, delegated IDs when exposed, and remaining gaps concisely. Do not
repeat the entire work history or claim acceptance based on completion messages.
