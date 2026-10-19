# Execution and context continuity

Use durable records to reduce memory load and preserve the objective across work switches and parallel execution.
Continue useful execution through internal milestones without extra user confirmation or review cycles.
Honor host progress-update requirements with concise material updates.
Do not proactively request compaction because of a milestone or apparent context pressure.
Do not interfere with runtime-managed automatic compaction.

## Record location and ownership

Use the record form selected in SKILL.md.
For durable records, keep STATE.md, TODO.md, and HANDOFF.md in one canonical task directory.
Follow the project location, or default to `.agent/<task-id>/`.
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
| STATE.md | Global objective, authorized scope, shared decisions, integrated acceptance, governing instruction paths, and execution mode |
| STATE.md | Accepted artifact revisions, evidence links, shared blockers, active or unknown modifying commands, resource conflicts, and uncertainties |
| TODO.md | Stable task IDs, deliverables, owners, dependencies, status, affected files or workspaces, and task blockers |
| TODO.md | Links to local plans, acceptance definitions, evidence, and the next ready tasks |
| HANDOFF.md | Resume entry point, canonical record paths, environment requirements, and the next task ID |
| HANDOFF.md | Ownership transfer details and links to process state and unfinished work |
| plan.md | Implementation Goal, Non-goals, local Accept, selected depth, implementation decisions, and required rollback |
| evidence/checks.md | Criterion, command or observation, artifact revision, environment, result, evidence path, and invalidation trigger |
| evidence/review.md | Review scope and revision, reviewer, findings, triage, repairs, round count, and unresolved items |

For integrated checks, use evidence files under the parent task root.
For slice checks and reviews, use evidence files beside that slice's plan.
A parent plan can define global scope and acceptance. In that case, STATE.md references those sections instead of copying them.
HANDOFF.md is a resume guide. The implementation's final change description reports delivery evidence and limitations.
Neither document replaces the other.

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
In HANDOFF.md, identify transferred task IDs and the next owner when known.
Link their completed and remaining work from TODO.md.
Reference existing decisions and evidence rather than reconstructing them from memory.

## Resume

1. Locate the canonical record. If promotion is required, create durable records before further execution.
   Read HANDOFF.md for the resume entry point.
2. Read STATE.md, TODO.md, applicable governing instructions, and project MEMORY.md when present.
3. Check the objective and scope against the latest user instructions.
4. Reconcile artifact revisions, task ownership, process state, and evidence needed for the next decision.
5. Update stale records before dependent work resumes.
6. Continue the next ready task without repeating accepted work.

Do not reload every reference or repeat passing checks unless their evidence became invalid or cannot be recovered.
If records conflict, inspect the relevant artifacts and evidence before resolving the conflict.
Do not treat an intended action or an executor report as an observed result.
Persisted records assist continuity but do not guarantee runtime context preservation.

## Retention and transfer

Follow the project's Git policy for task records and memory. Do not force-add ignored files.
If no policy exists, keep runtime records local and retain them until dependent work and handoffs finish.
Commit durable decisions and reusable evidence only through the project's established change process.
Before transfer, provide the required ignored or untracked records through explicit copies or accessible absolute paths.
Verify artifact revisions and record access in the receiving workspace before dependent work resumes.
Keep the completed task's acceptance, unresolved items, and evidence references until project cleanup policy permits removal.
Do not delete another task's records.

## Project memory maintenance

Use project-root MEMORY.md unless project instructions select another canonical location.
Keep one memory file per project, outside individual task directories.
At entry, read relevant memory before substantive work. A file alone does not ensure automatic discovery.
Use the project's agent entry instructions to identify its canonical memory path.
Pass that path or an accessible copy to agents and new workspaces.
If memory is unavailable, report the gap instead of claiming cross-session access.

After each completed task, review the full available session, including corrections, decisions, failures, and observed checks.
If earlier context is unavailable, consult durable records and disclose the limitation.
Do not invent details from missing context.
Extract useful preferences, user habits, project constraints, reusable methods, and lessons supported by the session.
Separate explicit user statements from observations. Do not infer a lasting habit from one incidental action.
Record each useful entry's date, scope, source, lesson, and conditions for reuse.
Exclude secrets, unnecessary personal details, raw transcripts, and temporary task status.
Memory does not grant permissions or override current instructions.

The parent is the sole memory writer during coordinated work.
Executors return candidate entries with sources. The parent checks them against evidence before inclusion.
Without a coordinator, the task owner maintains memory and serializes writes with other sessions.
Before an update, reread the current file and reconcile concurrent changes.
Merge duplicate entries, correct stale claims, and remove obsolete guidance while preserving relevant decision reasons.
When no useful new lesson exists, record the review date and that outcome without adding filler.
Keep memory concise. Preserve detailed evidence in its owning task record and link it when necessary.

## Worked example

A parent implements CSV export with one delegated parser slice.
The task uses this structure:

```text
MEMORY.md
.agent/csv-export/
  STATE.md
  TODO.md
  HANDOFF.md
  plan.md
  evidence/checks.md
  evidence/review.md
  tasks/parser/
    plan.md
    evidence/checks.md
    evidence/review.md
```

The parent defines shared CSV compatibility in STATE.md and assigns parser task P1 in TODO.md.
The parser owner defines local acceptance in tasks/parser/plan.md.
A quoted-field check fails. The owner records its revision and output in the slice's evidence/checks.md.
The parent marks P1 blocked in TODO.md and references that evidence.
HANDOFF.md points to P1 and the records needed to resume.
A fresh context reads those paths and MEMORY.md, then checks process state before repairs.
After repair and review, the parent accepts P1 and records integrated checks separately.
At completion, the parent reviews the session and records any reusable lesson in MEMORY.md.
