# Dispatch and result contracts

Use this reference when the selected mode includes delegated slices.
Do not create slices or agent briefs for direct execution.

Define acceptance before dispatch. Use the smallest useful dependency plan;
avoid creating slices solely to increase utilization. Resolve critical shared
interfaces before dependent implementation. Dispatch ready independent work;
wait only when the next decision needs an outstanding result.

Use fresh, self-contained briefs when supported and useful. Pass necessary
context explicitly instead of assuming inherited history. Require executors
to read applicable project instructions and relevant skills.

For implementation assignments, identify the implementation workflow and its entry point.
When applicable, direct the implementer to use `three-loop-workflow` for its assigned change.
Let the implementer choose depth and report required roles before dependent work starts.
The brief's acceptance criteria remain constraints. Implementation detail may refine them without weakening them.

## Brief template

- Task ID and objective:
- Expected deliverables:
- Background and source paths:
- Dependencies and interface contracts:
- Workspace and owned files/resources:
- Required starting revision and uncommitted inputs, with verification before dependent implementation:
- Permitted operations and prohibited changes:
- Applicable instructions and skills:
- Implementation plan path and shared acceptance references:
- Acceptance criteria and focused checks:
- Required roles and capacity, with permitted review fallback:
- Integration owner, if needed:
- Canonical STATE.md, TODO.md, and HANDOFF.md paths (parent-owned):
- Separate executor evidence path and expected report format:
- Execution policy: batch related changes; continue through internal milestones;
  verify meaningful units, not individual edits; avoid repeated checks without
  a changed artifact, failure, or unresolved concern.
- Coordination boundary: do not recursively orchestrate unless assigned;
  report concise findings and evidence paths, not full transcripts.

## Result template

- Task ID; exposed agent ID; execution status:
- Produced or changed paths:
- Completed behavior or findings:
- Implementation depth, plan path, review state, and local acceptance:
- Checks, artifact revision, outcomes, and evidence paths:
- Requests for scope, interface, workspace, roles, or user decisions:
- Remaining gaps, blockers, and required follow-up:
- Modifying commands still active or unknown:

Validate structured results; do not assume host schema enforcement.
Store verbose logs and intermediate evidence in task-local files when available.
Use one integration owner to combine accepted contributions; provide all changes,
contracts, and checks. The parent or a qualified executor may own integration unless a governing workflow
requires an independent owner. Assign independent review separately.

Resolve executor requests before affected work continues. Revise dependent assignments when a shared interface changes.
An executor's local completion does not establish integrated acceptance.

Revise affected slices when evidence changes dependencies or assumptions.
Continue unaffected ready work. Cancel obsolete work through supported mechanisms.
Do not expand authorized scope or relax acceptance criteria to disguise failure.
