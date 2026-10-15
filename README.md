# Orchestrate

Orchestrate is a skill for coordinated work with native subagents: separate agents that execute assigned tasks within the host.
The parent agent owns the overall plan, task assignments, shared interfaces, and integrated acceptance.
Each implementer owns the assigned implementation plan, changes, evidence, review, and repairs.
The parent can implement an assigned slice or assign it to a subagent.

Invoke Orchestrate to select an execution structure with clear ownership and evidence of completion.
Simple tasks can remain with the parent, even when the skill is explicitly invoked.
Delegate only when the benefit justifies coordination cost or an explicit role requirement applies.

| Mode | Typical task | Ownership |
| --- | --- | --- |
| Direct | Small correction or focused investigation | The parent completes the work |
| Mixed | Main task with a useful independent investigation | The parent and executors own separate slices |
| Delegated | Substantial independent work or required context isolation | Executors complete assigned work |

Reassess the mode when scope or dependencies change.
Complexity alone does not require delegation when the work cannot split usefully.

## Use with three-loop-workflow

Orchestrate schedules work. When available and applicable, three-loop-workflow guides each implementation through Plan, Build, and Close.
It defines implementation depth, verification, review, and repair stop conditions.
Without that skill, Orchestrate uses the project's implementation workflow and checks.

Execution mode and implementation depth are separate decisions.
Direct execution can require Standard or Deep implementation gates, including independent review.
Assign the same implementation workflow to parent-owned and delegated changes.

Include scope, interfaces, workspace ownership, acceptance criteria, and the local plan path in each assignment.
Specify the starting revision and verify required uncommitted inputs before dependent implementation.
Executors return artifact revisions, evidence, review state, and unresolved requests.
The parent resolves scheduling requests and checks integrated acceptance.
Successful local checks alone do not establish that the combined result works.

```text
Use $orchestrate to schedule this change.
Use $three-loop-workflow for each implementation assignment.
Keep shared interface decisions with the parent.
Verify the integrated result before completion.
```

## Why use it?

- **Clear ownership.** Each task has a responsible agent, defined outputs, and acceptance evidence.
- **Continuous execution.** Internal milestones do not require repeated user confirmation.
- **Controlled parallel work.** Writers use isolated resources or execute in sequence when resources conflict.
- **Evidence of completion.** Final acceptance covers the integrated result, required checks, and agent status.
- **Context continuity.** Repository records preserve essential state across context transitions.

The skill limits redundant checks while preserving required reviews, host permissions, and existing authorization boundaries.
It does not promise faster execution for every task.

## Work records

Short parent-only work can use one compact record in the conversation or an existing task record.
Before delegation, deferred work, another session, a context transition, handoff, or ongoing background work, create durable records.
Preserve implementation plans and stronger project requirements.

For durable work, the parent maintains three files in the project task directory.
The default location is `.orchestration/<task-id>/`.

| File | Purpose |
| --- | --- |
| STATE.md | Current objective, scope, decisions, evidence, blockers, and next action |
| TODO.md | Task progress, owners, dependencies, and acceptance status |
| HANDOFF.md | Resume context, artifact locations, process state, and immediate next steps |

Update affected records after dispatch, material results, scope changes, blockers, and acceptance decisions.
For durable work, synchronize all three records before work switches or handoffs.
Executors use separate evidence files to prevent concurrent writes to the parent records.
Keep records brief and link evidence instead of copying transcripts.
Keep each implementation plan with its task. Reference it from the parent records.

## Example requests

Explicitly invoke the skill with `$orchestrate`, or request multi-agent orchestration.
Include the deliverable, constraints, and expected checks.

```text
Use $orchestrate to implement CSV export in this repository.
Preserve the existing API and package manager.
Run the project checks and report the final result.
```

```text
Use $orchestrate to investigate this failing build.
Delegate independent investigations where useful.
Integrate the required fixes and run the project checks.
```

Ordinary tasks and requests to inspect or edit this skill do not activate its orchestration workflow.

## Requirements and boundaries

Delegated execution requires native subagent capabilities and permission to delegate.
If delegation is unavailable, the parent can execute directly when host and user instructions permit it.
If a required role is unavailable, report the blocker and actionable task briefs.
Preserve explicit user role assignments and required independent review in every mode.

The skill uses only exposed host capabilities.
It does not provide an agent runtime or bypass host permissions.
Required reviews and checks take precedence over optional efficiency measures.

## Skill files

| File | Purpose |
| --- | --- |
| [SKILL.md](orchestrate/SKILL.md) | Activation rules, operating contract, and execution workflow |
| [Agent metadata](orchestrate/agents/openai.yaml) | Display name, short description, and default prompt |
| [Runtime capabilities](orchestrate/references/runtime-capabilities.md) | Delegation, resource isolation, and capacity |
| [Dispatch](orchestrate/references/dispatch.md) | Task slices, agent briefs, and result contracts |
| [Acceptance](orchestrate/references/acceptance.md) | Checks, reviews, and failure handling |
| [Context continuity](orchestrate/references/context-continuity.md) | State preservation and recovery after context transitions |

The skill loads references only when the next decision requires them.
The `metadata.version` field in [SKILL.md](orchestrate/SKILL.md) records the skill version.

## Version history

See [CHANGELOG.md](CHANGELOG.md) for dated changes and source commits.
When the skill version changes, update the changelog in the same change.
Keep entries in descending version order and describe changes that affect users.
If a version exists only during development, identify it without inventing a separate release.
Documentation-only edits do not require a skill version increase.
