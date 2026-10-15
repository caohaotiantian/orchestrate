# Changelog

This file records published skill versions, with the newest version first.
The version in `orchestrate/SKILL.md` identifies the current skill version.

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
