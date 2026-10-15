# Execution and context continuity

Use durable records to reduce memory load and preserve the objective across work switches and parallel execution.
Continue useful execution through internal milestones without extra user confirmation or review cycles.
Honor host progress-update requirements with concise material updates.
Do not proactively request compaction because of a milestone or apparent context pressure.
Do not interfere with runtime-managed automatic compaction.

## Record location and ownership

Use the record form selected in SKILL.md.
For durable records, keep STATE.md, TODO.md, and HANDOFF.md in one canonical task directory.
Follow the project location, or default to `.orchestration/<task-id>/`.
Use separate directories for separate tasks and retain stable task IDs.
If records already exist, reconcile them instead of creating a competing set.
When promotion is required, transfer essential facts and evidence references from the compact record into the durable records.
If durable storage is unavailable, report the continuity limitation and the state that cannot be preserved.

The parent owns the canonical records and reconciles executor reports with actual artifacts and evidence.
Give executors separate evidence paths and identify the canonical records in each brief.
Do not permit concurrent writes to the canonical records.
If the parent role transfers, establish one successor before record writes resume.

## Record responsibilities

A compact record preserves the objective, scope, result or next action, and evidence references.
For durable records, use the responsibilities below.

Store each fact in its responsible record and reference it from the others.
Keep global scope, assignments, dependencies, and integrated acceptance in parent-owned records.
Keep implementation plans, selected depth, review findings, and detailed evidence in the assigned task's artifacts.
For parent-owned implementation, preserve the same distinction between global records and the local plan.
Give each task a plan path under its task directory or the project's established convention.
Keep current facts concise and replace stale summaries.
Preserve decisions that still constrain the work, with their reasons.
Keep verbose logs and transcripts outside these records.

| Record | Required information |
| --- | --- |
| STATE.md | Objective, authorized scope, acceptance criteria, governing instruction paths, and current execution mode |
| STATE.md | Current artifacts and revisions, relevant decisions, accepted results, evidence references, blockers, and next action |
| STATE.md | Active or unknown modifying commands, resource conflicts, and facts that remain uncertain |
| TODO.md | Stable task IDs, deliverables, status, owners, dependencies, and affected files or workspaces |
| TODO.md | References to local plans and acceptance criteria, evidence, blockers, and the next ready tasks |
| HANDOFF.md | Resume entry point, relevant record and artifact paths, environment requirements, and immediate next steps |
| HANDOFF.md | Last completed action, unfinished work, process and resource state, and ownership transfer details when applicable |

Include the last update time and relevant artifact revision in each record.
In TODO.md, distinguish pending, active, blocked, and done tasks.
Track agent lifecycle separately from task acceptance, including exposed agent IDs when available.
A completed agent does not make its task done until the acceptance criteria pass.
Link acceptance criteria to their canonical definition instead of copying them into every record.
Keep HANDOFF.md usable by a fresh context without the conversation transcript.
When no transfer is pending, maintain a concise resume snapshot rather than inventing a recipient.

## Update events

Update only the affected sections after each meaningful event:

- The objective, authorized scope, acceptance criteria, or a relevant decision changes.
- Work starts, an executor receives a task, or ownership changes.
- A material result arrives, a check completes, or an artifact becomes accepted.
- A dependency, blocker, process state, or resource conflict changes.
- A task completes, fails, or needs a different next action.

Record dispatch and ownership before dependent or conflicting work starts.
Record material results before another decision depends on them.
For durable work, synchronize all three records before a work switch, handoff, or anticipated context transition.
At closure, record final acceptance, unresolved items, and process state.
Do not delay updates until the final response.
Do not record every tool call or minor edit.

## Parallel work and handoff

Assign each parallel slice a stable task ID, owner, workspace, and evidence path in TODO.md.
Record shared interfaces and resource conflicts in STATE.md before parallel writes.
Executors report task IDs, changed artifacts, checks, blockers, and active or unknown commands.
The parent reconciles these reports at meaningful events while independent work continues.
Do not copy each executor transcript into the canonical records.

Before ownership transfers, establish that the previous owner's modifying commands have stopped.
If process state remains unknown, record that uncertainty and prevent conflicting writes.
In HANDOFF.md, identify the transferred task IDs, completed work, remaining work, and next owner when known.
Reference existing decisions and evidence rather than reconstructing them from memory.

## Resume

1. Locate the canonical record. If promotion is required, create durable records before further execution.
   Read HANDOFF.md for the resume entry point.
2. Read STATE.md, TODO.md, and applicable governing instructions.
3. Check the objective and scope against the latest user instructions.
4. Reconcile artifact revisions, task ownership, process state, and evidence needed for the next decision.
5. Update stale records before dependent work resumes.
6. Continue the next ready task without repeating accepted work.

Do not reload every reference or repeat passing checks unless their evidence became invalid or cannot be recovered.
If records conflict, inspect the relevant artifacts and evidence before resolving the conflict.
Do not treat an intended action or an executor report as an observed result.
Persisted records assist continuity but do not guarantee runtime context preservation.
