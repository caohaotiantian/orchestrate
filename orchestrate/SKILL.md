---
name: orchestrate
description: >
  Coordinate native subagents when the user explicitly invokes $orchestrate
  or requests multi-agent orchestration. Own task allocation, dependencies,
  and integrated acceptance. Do not activate merely to inspect or edit this skill.
metadata:
  version: "1.6.0"
---

# Orchestrate

## Operating contract

Keep the parent responsible for the overall plan, scheduling, shared interfaces,
integration ownership, integrated acceptance, and user communication.
Each implementer owns the assigned implementation plan, changes, evidence, review, and repairs.
The parent may implement an assigned slice under the same implementation workflow as other executors.

When available and applicable, use `three-loop-workflow` for implementation and pre-landing review.
Let it define implementation depth, checks, review requirements, and repair stop conditions.
Keep execution mode separate from implementation depth. Direct execution does not waive implementation gates.
Without that skill, use the project's implementation workflow and checks.

Follow host instructions, permissions, and existing user authorization.
Use only exposed native capabilities. Do not invent tools, agents, results,
or evidence. Preserve explicit user requirements for delegation and role separation.

## Choose execution mode

Select the smallest execution structure that can complete the task correctly.
Assess scope, uncertainty, dependencies, risk, and coordination cost before dispatch.
Do not use file count, task length, or skill invocation alone as a delegation trigger.

| Mode | Selection criteria | Execution owner |
| --- | --- | --- |
| Direct | Clear scope, limited uncertainty, tightly coupled work, or delegation costs exceed its likely benefit | The parent completes the work and checks |
| Mixed | Some independent work benefits from delegation while the parent can advance the main task | The parent and assigned executors own separate slices |
| Delegated | Substantial independent work, context isolation, or explicit role requirements justify executors | Executors own assigned slices; the parent coordinates and accepts |

For a small correction or a focused investigation, prefer direct execution.
For independent investigations or separate implementation areas, consider mixed or delegated execution.
Complexity alone does not justify delegation when work cannot split usefully.
Use one executor when context isolation or an explicit role requirement justifies delegation of indivisible work.
Do not create an executor solely to keep the parent free of substantive work.

State the selected mode and its reason briefly for substantive tasks.
Reassess at meaningful scope or dependency changes, rather than after every edit.
Before ownership changes, establish that the previous owner's modifying commands have stopped.
Give the next owner the relevant artifacts and acceptance criteria.

If delegation is unavailable, use direct execution when host and user instructions permit it.
If a required role cannot be provided, report the blocker and actionable briefs.
Keep required independent review separate from implementation, including in direct mode.

Do not activate this workflow recursively in executors unless coordination
is explicitly assigned. Do not assume executors inherit this skill.

## Default execution loop

1. Read applicable project instructions and select an execution mode.
   Discover delegation capabilities only when delegation or a required role needs them.
2. Define deliverables, dependencies, ownership, shared interfaces, and integrated acceptance evidence.
   Select and initialize the work records before substantive execution.
3. Execute parent-owned slices through the implementation workflow. Dispatch other slices with self-contained briefs.
   Keep tightly coupled work together; split only when the benefit exceeds coordination cost.
4. Continue execution through meaningful implementation units. Treat milestones
   as internal progress markers, not user acceptance gates.
5. Schedule integration and required checks against stable outputs.
   Assign repairs to the implementation owner. Continue unaffected ready work.
6. Perform final acceptance against the integrated result and close the task.

Prioritize useful execution over intermediate reviews.
Batch related changes; do not inspect or test after every minor edit.
Do not repeatedly summarize finished work or ask for confirmation. Request
input only for a consequential irreversible decision requiring approval,
missing requirements that prevent correct execution, or an applicable safety
constraint. Forward implementation decision requests and stop conditions to the user when required.
Honor all host-required approvals and progress updates.

Avoid redundant inspections, tests, and status reports. Stop verification when
recorded criteria pass and no material uncertainty remains. Repeat checks only
for relevant changes, failures, unresolved uncertainty, or governing requirements.
Never substitute an agent's report for evidence or mark missing checks as passed.

Do not proactively request context compaction because a milestone was reached
or context usage appears high. Preserve essential state in repository records
before anticipated context transitions. Runtime-managed automatic compaction
and required safety checks remain authoritative.

## Work records

For short parent-only work without delegation, deferred work, handoff, or background work, use one compact record.
Keep it in the conversation or an existing task record. Preserve required implementation plans.

Before delegation, deferred work, another session, a context transition, handoff, or background work, create durable records.
Use STATE.md, TODO.md, and HANDOFF.md under `.agent/<task-id>/`, unless the project selects another location.
Reuse the current task's canonical directory. The parent owns these records.
Keep implementation plans and detailed evidence with their task owners, under `tasks/<slice-id>/` for delegated work.

Admit only facts that affect an unfinished task's decision, action, acceptance, or safe recovery.
Replace changed facts instead of accumulating updates. Reference the owning artifact instead of copying it.
Remove completed work from the active queue once acceptance and remaining dependencies no longer require it.
Close finished tasks out of the active read route. Keep historical evidence accessible on demand.

Start recovery with the named task's HANDOFF.md. Read only the sections needed for its next action.
Do not scan old task directories or load every linked plan, record, or evidence file.
Before the first record update or recovery, read [Context continuity](references/context-continuity.md) for lifecycle and ownership rules.

## Durable project memory

At entry, inspect the project's memory selector when present. Read only entries whose reuse conditions match the task.
If memory has no selector, locate relevant headings without loading its entire contents.
At completion, review available session information for qualifying changes, including removals. A review need not produce a write.
Keep memory separate from task history and authoritative instructions. Do not append completion or no-change review entries.
The parent owns memory updates. Executors return sourced candidates and receive only relevant memory references.
Use the context continuity memory rules for admission, replacement, expiry, and concurrent updates.

## Resource and acceptance boundaries

Discover shared resources before parallel writes. Isolate writers or serialize
conflicts, including generated files, lockfiles, and repository metadata.
Assign integration ownership and reserve required review capacity before parallel implementation.
The parent or a qualified executor may own integration, subject to governing role requirements.
Route workspace, dependency, interface, and role requests through the parent before affected work resumes.

Establish that relevant modifying commands have stopped before reviewing or
checking an artifact. An interrupted agent does not prove its processes stopped.
Report unknown stability rather than claiming reproducible acceptance.

Track agent lifecycle separately from deliverable acceptance. Confirm required
outputs, integration, and final checks before completion; report unavailable
checks and unresolved states. Confirm spawned agents' final status when supported.
Do not claim closure while required work remains active, blocked, or unverified.

## Load references on demand

Read only the reference needed for the next decision; do not preload all files.
Each reference is independent and uses host-neutral terminology.

| Situation | Reference |
| --- | --- |
| Discovering delegation, isolation, or capacity | [Runtime capabilities](references/runtime-capabilities.md) |
| Preparing slices, briefs, or result contracts | [Dispatch](references/dispatch.md) |
| Planning checks, reviewing results, or handling failures | [Acceptance](references/acceptance.md) |
| Maintaining execution continuity or recovering after compaction | [Context continuity](references/context-continuity.md) |

Map implementation gates and integrated checks into one acceptance plan through references to their owning records.
Do not duplicate reviews or tests already satisfied on the same artifact under the required conditions.
Required checks and role separation take precedence over optional efficiency heuristics.
