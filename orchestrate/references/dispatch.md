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

## Brief template

- Task ID and objective:
- Expected deliverables:
- Background and source paths:
- Dependencies and interface contracts:
- Workspace and owned files/resources:
- Permitted operations and prohibited changes:
- Applicable instructions and skills:
- Acceptance criteria and focused checks:
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
- Checks, artifact revision, outcomes, and evidence paths:
- Remaining gaps, blockers, and required follow-up:
- Modifying commands still active or unknown:

Validate structured results; do not assume host schema enforcement.
Store verbose logs and intermediate evidence in task-local files when available.
Use one integration owner to combine accepted contributions; provide all changes,
contracts, and checks. The parent or a qualified executor may own integration unless a governing workflow
requires an independent owner. Assign independent review separately.

Revise affected slices when evidence changes dependencies or assumptions.
Continue unaffected ready work. Cancel obsolete work through supported mechanisms.
Do not expand authorized scope or relax acceptance criteria to disguise failure.
