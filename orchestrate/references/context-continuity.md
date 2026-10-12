# Execution and context continuity

Keep implementation moving through internal milestones. In the parent this means
continuous dispatch, dependency decisions, integration coordination, and acceptance;
in executors it means continuous substantive work. It does not change role boundaries.

Do not turn each milestone into a user confirmation, summary, or review cycle.
Honor host progress-update requirements with short material updates: what changed,
what remains uncertain, and what action resolves it. Avoid transcript forwarding.

Do not proactively request compaction solely because of a milestone or apparent
context pressure. Do not interfere with runtime-managed automatic compaction.
Before an anticipated transition, preserve the minimum recoverable state in an
existing repository/task record. When no repository exists, use permitted durable
task-local storage; if unavailable, report the continuity limitation.

## Minimal state record

Use one canonical record, for example `.orchestration/state.md`, adapting the path
to project instructions. The parent may maintain this coordination record; give
each executor separate evidence paths. Avoid concurrent writes to the same record.

- Final objective, authorized scope, and governing instruction paths.
- Current artifact revision and owned workspaces.
- Slice IDs, exposed agent IDs, dependencies, and integration ownership.
- Agent status separately from accepted/delivered/rejected/blocked outputs.
- Decisions and interface contracts still relevant.
- Evidence/check ledger references and invalidation conditions.
- Active or unknown modifying commands.
- Concrete blockers and next ready action.

Update at meaningful state changes or before anticipated transitions, not after
every edit. Keep verbose logs separate. Do not write a second narrative recap
when the state record already captures what is needed.

## Resume

Read the canonical state record and governing instructions. Inspect only the
artifact, process state, or evidence needed for the next decision. Reconcile
stale status once when necessary. Continue from the next ready action; do not
restart completed research, reload every reference, or rerun passing checks
unless their evidence was invalidated or cannot be recovered.

Persisted records assist continuity; they do not guarantee that the runtime
will preserve context, avoid automatic compaction, or retain a remote session.
