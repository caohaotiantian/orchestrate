---
name: orchestrate
description: >
  Coordinate native subagents when the user explicitly invokes $orchestrate
  or requests multi-agent orchestration. Choose direct, mixed, or delegated
  execution from task complexity and coordination cost. Keep planning and
  final acceptance in the parent. Do not activate for ordinary tasks or merely to discuss,
  inspect, or edit this skill.
metadata:
  version: "1.2.0"
---

# Orchestrate

## Operating contract

Keep the parent responsible for the plan, execution choices, interface decisions,
acceptance, and user communication. Allow the parent to investigate, implement,
integrate, and repair within the selected execution mode.

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
2. Define deliverables, dependencies, ownership, and acceptance evidence.
   Initialize or reconcile STATE.md, TODO.md, and HANDOFF.md before substantive execution.
3. Execute parent-owned work directly. Dispatch assigned slices using self-contained briefs.
   Keep tightly coupled work together; split only when the benefit exceeds coordination cost.
4. Continue execution through meaningful implementation units. Treat milestones
   as internal progress markers, not user acceptance gates.
5. Integrate when needed. Run focused checks on stable outputs.
   Assign repairs to the relevant owner. Continue ready work after successful checks.
6. Perform final acceptance against the integrated result and close the task.

Prioritize useful execution over intermediate reviews.
Batch related changes; do not inspect or test after every minor edit.
Do not repeatedly summarize finished work or ask for confirmation. Request
input only for a consequential irreversible decision requiring approval,
missing requirements that prevent correct execution, or an applicable safety
constraint. Honor all host-required approvals and progress updates.

Avoid redundant inspections, tests, and status reports. Stop verification when
recorded criteria pass and no material uncertainty remains. Repeat checks only
for relevant changes, failures, unresolved uncertainty, or governing requirements.
Never substitute an agent's report for evidence or mark missing checks as passed.

Do not proactively request context compaction because a milestone was reached
or context usage appears high. Preserve essential state in repository records
before anticipated context transitions. Runtime-managed automatic compaction
and required safety checks remain authoritative.

## Durable work records

In every execution mode, keep STATE.md, TODO.md, and HANDOFF.md in one task directory.
Use the project location or default to `.orchestration/<task-id>/`.
Keep the parent responsible for timely updates and consistency across these records.

- STATE.md: Preserve the objective, scope, decisions, current state, evidence references, blockers, and next action.
- TODO.md: Track task IDs, status, owners, dependencies, acceptance criteria, and evidence references.
- HANDOFF.md: Preserve the minimum context, artifact locations, process state, and next steps needed to resume or transfer work.

Initialize these records before substantive execution, including direct execution.
Keep short tasks brief rather than omitting the records.
Update affected records after dispatch, material results, scope changes, blockers, ownership changes, and acceptance decisions.
Before a work switch, handoff, or anticipated context transition, synchronize all three records.
Do not wait until the final response to record progress.
Use references instead of duplicate narratives, logs, or transcripts.
Read [Context continuity](references/context-continuity.md) before the first record update or recovery.

## Resource and acceptance boundaries

Discover shared resources before parallel writes. Isolate writers or serialize
conflicts, including generated files, lockfiles, and repository metadata.
Assign integration ownership before parallel implementation. Integration may
reuse a qualified executor; independent review is a separate risk-based role.
Allow the parent to own integration unless a governing workflow requires another owner.

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

If a governing workflow such as `three-loop-workflow` is available and applicable,
read it and map its checks into one shared acceptance plan. Do not duplicate
reviews or tests already satisfied on the same artifact. Required checks and
role separation take precedence over optional efficiency heuristics.
