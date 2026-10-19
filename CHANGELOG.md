# Changelog

This file records published skill versions, with the newest version first.
The version in `orchestrate/SKILL.md` identifies the current skill version.
Unreleased entries describe changes before a tagged release.

## 1.4.0 — 2026-10-19

Release: [v1.4.0](https://github.com/caohaotiantian/orchestrate/releases/tag/v1.4.0)

- Share new task records under `.agent/<task-id>/` and preserve existing canonical directories.
- Define canonical fields, check and review evidence paths, retention, transfer, and a recovery example.
- Read project memory at entry and maintain sourced lessons after each completed task.

## 1.3.0 — 2026-10-16

Release: [v1.3.0](https://github.com/caohaotiantian/orchestrate/releases/tag/v1.3.0)

### Changed

- Keep task scheduling, dependencies, shared interfaces, and integrated acceptance with the parent.
- Assign implementation plans, changes, checks, review, and repairs to each implementer.
- Use three-loop-workflow when available and applicable, including for parent-owned implementation.
- Separate execution mode from implementation depth and preserve required role allocation.
- Connect task briefs, local results, and global records through artifact and acceptance references.
- Apply explicit review fallbacks and preserve repair limits across ownership changes.
- Distinguish local evidence from required integrated and clean-state checks.
- Allow a compact coordination record for short parent-only work and require promotion before durable coordination becomes necessary.
- Specify the starting revision and required uncommitted inputs in each implementation assignment.

## 1.2.0 — 2026-10-15

Commit: [3662bdd](https://github.com/caohaotiantian/orchestrate/commit/3662bdd)

### Changed

- Select direct, mixed, or delegated execution from task complexity, dependencies, and coordination cost.
- Allow the parent to investigate, implement, integrate, and repair assigned work.
- Permit direct execution when delegation is unavailable and no required role prevents it.
- Preserve explicit user role assignments and required independent review.
- Align the README, agent metadata, and references with adaptive delegation.

### Added

- Require parent-owned STATE.md, TODO.md, and HANDOFF.md in every execution mode.
- Define record responsibilities, update events, ownership transfer, and recovery steps.
- Use separate executor evidence paths to prevent concurrent writes to canonical records.

The working version 1.1.0 introduced adaptive delegation during development.
It had no separate Git commit or release entry.
Version 1.2.0 includes those changes and the durable work records.

## 1.0.0 — 2026-10-12

Commit: [c4939af](https://github.com/caohaotiantian/orchestrate/commit/c4939af)

### Added

- Add the explicit skill version and introduction README.
- Retain native delegation, parent acceptance, isolated resources, and checks based on risk.
- Include references for dispatch, runtime capabilities, acceptance, and context continuity.

The initial source package entered the repository in commit
[57443ff](https://github.com/caohaotiantian/orchestrate/commit/57443ff), before the explicit version field.
