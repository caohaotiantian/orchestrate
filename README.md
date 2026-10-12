# Orchestrate

Orchestrate is a skill for coordinated work with native subagents: separate agents that execute assigned tasks within the host.
The parent agent owns the plan, task assignments, interface decisions, and final acceptance.
Subagents perform substantive investigation, implementation, integration, and repairs.

Use Orchestrate when a task needs delegated execution with clear ownership and evidence of completion.
It supports parallel work where the task permits it and one executor where the work cannot split.

## Why use it?

- **Clear ownership.** Each task has a responsible agent, defined outputs, and acceptance evidence.
- **Continuous execution.** Internal milestones do not require repeated user confirmation.
- **Controlled parallel work.** Writers use isolated resources or execute in sequence when resources conflict.
- **Evidence of completion.** Final acceptance covers the integrated result, required checks, and agent status.
- **Context continuity.** Repository records preserve essential state across context transitions.

The skill limits redundant checks while preserving required reviews, host permissions, and existing authorization boundaries.
It does not promise faster execution for every task.

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

The host must expose native subagent capabilities and permit delegation.
If delegation is unavailable, the skill requires a blocker report and actionable task briefs.
The parent must not silently replace delegated execution with its own implementation.

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
