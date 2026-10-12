---
name: orchestrate
description: >
  Coordinate native subagents when the user explicitly invokes $orchestrate
  or requests multi-agent orchestration. Delegate substantive investigation,
  implementation, integration, and fixes; keep planning and final acceptance
  in the parent. Do not activate for ordinary tasks or merely to discuss,
  inspect, or edit this skill.
---

# Orchestrate

## Operating contract

Keep the parent responsible for planning, scheduling, interface decisions,
acceptance, and user communication. Delegate substantive investigation,
implementation, integration, and fixes. For indivisible work, use one executor.
Allow bounded capability discovery, artifact inspection, and acceptance checks
in the parent; limit parent writes to orchestration records.

Follow host instructions, permissions, and existing user authorization.
Use only exposed native capabilities. Do not invent tools, agents, results,
or evidence. If delegation is unavailable or prohibited, report the blocker
and actionable briefs; do not silently switch to parent execution.

Do not activate this workflow recursively in executors unless coordination
is explicitly assigned. Do not assume executors inherit this skill.

## Default execution loop

1. Discover actual host capabilities and applicable project instructions.
2. Define deliverables, dependencies, ownership, and acceptance evidence.
3. Dispatch ready slices using self-contained briefs. Keep tightly coupled
   work together; split only when useful parallelism exceeds coordination cost.
4. Continue execution through meaningful implementation units. Treat milestones
   as internal progress markers, not user acceptance gates.
5. Integrate when needed, run focused checks on stable outputs, and delegate
   actionable repairs. Continue ready work after successful checks.
6. Perform final acceptance against the integrated result and close the task.

Prioritize continuous delegated implementation over intermediate reviews.
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

## Resource and acceptance boundaries

Discover shared resources before parallel writes. Isolate writers or serialize
conflicts, including generated files, lockfiles, and repository metadata.
Assign integration ownership before parallel implementation. Integration may
reuse a qualified executor; independent review is a separate risk-based role.
Keep the parent out of substantive integration edits.

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
