# Acceptance and bounded recovery

## Verification plan

Define integrated acceptance before execution, including a stopping condition.
Reference each implementation's required gates rather than inventing a second implementation review process.
For work without an implementation workflow, select evidence from impact, uncertainty, and governing requirements:

| Risk | Default evidence |
| --- | --- |
| Low: documentation, read-only research, non-behavioral edits | Inspect outputs, essential sources, and applicable lightweight checks |
| Medium: implementation or behavioral fixes | Inspect relevant complete diffs including new files; run focused behavior and interface checks |
| High: permissions, security, migration, destructive operations, cross-system contracts | Add applicable failure/regression, compatibility and data-integrity checks; independent review when feasible or required; required approvals |

If independent review is unavailable, follow the governing requirement's explicit fallback.
Without a permitted fallback, keep required review blocked.
Disclose any permitted self-review. Do not report it as independent review.
If review is optional, report the limitation and decide from concrete risk.
Risk does not weaken permissions, ownership, or isolation requirements.

## Check cadence and stopping rule

Treat a meaningful unit as a coherent behavior change, interface boundary, or
integration point whose failure could alter the next implementation decision.
Run focused verification there; reserve broad final checks for the integrated
artifact. Do not interrupt execution for ceremonial milestone reviews.

Use the context continuity evidence paths for durable work.
Maintain a compact check ledger: criterion, command or method, relevant artifact
revision, result, evidence path, and invalidation trigger. Reuse passing evidence
while relevant inputs and assumptions remain unchanged. A new task status or
context transition alone does not invalidate a check.
Keep required merged-result and clean-state checks distinct from local slice checks.
Reuse evidence only when its artifact and environment satisfy the governing requirement.

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

Return specific findings to the responsible owner.
Apply the implementation workflow's repair limits and escalation conditions to that assignment.
Preserve those conditions when an executor changes. Forward required user decisions instead of resetting repair counts.
For delegated work, use supported reassignment or provide a replacement with the complete brief and artifacts.
The parent may repair parent-owned work.
Before the parent assumes delegated repairs, transfer ownership under the execution-mode rules.

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

Before final closure, complete the project memory review defined in context continuity.
