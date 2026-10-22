# Runtime capabilities

Discover capabilities from exposed interfaces and governing instructions.
Do not assume specific namespaces, tool names, model rankings, concurrency,
filesystem isolation, cancellation, reuse, or structured-output enforcement.
Use the host's documented calling convention without adding custom tool rules.
Treat interface metadata as metadata, not executable agent definitions.

Record only capabilities relevant to the task: dispatch, messaging or reassignment,
status, process control, isolation, and capacity. Do not repeatedly rediscover
unchanged capabilities. If a limit is unknown, avoid claiming a numeric limit.

Use actual capacity; count the parent and active descendants if limits are shared.
Reserve capacity for dependent integration or review when needed. Reuse eligible
idle agents when useful. Inherit model and reasoning defaults; use overrides only
when authorized and supported, and record the reason.

Use isolated worktrees, copies, or equivalent mechanisms for parallel writers.
In shared workspaces, permit concurrency only when explicit ownership and command
side effects establish independence. Disjoint filenames alone do not establish
isolation: account for generated files, locks, shared metadata, and repository state.
Serialize conflicts if adequate isolation is unavailable.
If the implementation workflow requires separate working trees, provide them before concurrent writes.

Default to `<outermost-checkout-parent>/.worktree/<outermost-repository>/<module-path>/<task>` for new worktrees.
For standalone repositories, omit the module path. Preserve nested module paths beneath the outermost repository namespace.
For linked trees, resolve the original checkout first. Use verified checkout paths, not Git metadata directories.
Keep new worktrees outside existing checkouts.
Check project rules, path ownership, and branch occupancy before creation.
If the anchor is ambiguous or the default unavailable, stop before creation.
Before a deviation, explain its reason, proposed absolute path, scope, and effects.
Obtain explicit user confirmation unless an applicable confirmed exception exists.
Record durable rules in AGENTS.md and confirmed exceptions in MEMORY.md, with scope, reason, and source.

Keep reviewed artifacts stable. Use supported status and process mechanisms to
establish that modifying commands stopped. Report unknown process state. Do not
bypass host restrictions through alternate processes or fabricated agents.
