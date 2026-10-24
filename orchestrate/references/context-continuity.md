# Execution and context continuity

Use records to preserve the next useful action across work switches and context transitions.
Disk retention does not require context loading. A reference is available evidence, not an instruction to read it.
Do not request compaction or extra user review at internal milestones. Follow host-managed context transitions.

## Location and ownership

Use the record form selected in SKILL.md and the project's canonical task location.
Default durable records to `.agent/<task-id>/`. Reconcile the current task's existing records instead of creating competing sets.
The parent owns shared records and verifies executor reports against artifacts and evidence.
Keep executor evidence separate. Establish one successor before shared-record ownership changes.
If durable storage is unavailable, report the facts that cannot survive a context transition.

## Admission and field ownership

Before adding a fact, name the unfinished decision, action, acceptance check, or recovery condition it changes.
If none exists, omit the fact from working records.
Keep one authoritative location for each fact. Reference it from other records only when needed.

| Record | Admitted content | Exit condition |
| --- | --- | --- |
| STATE.md | Current scope, constraining decisions, acceptance state, blockers, ownership, revisions, and active or unknown commands | Replace changed state and remove constraints that no longer apply |
| TODO.md | Unfinished task IDs, owners, dependencies, next actions, blockers, and acceptance links | Remove accepted work when remaining dependencies no longer need its row |
| HANDOFF.md | Task status, next action, and the sections or artifacts needed for that action | Replace the recovery route when the next action changes |
| plan.md | Implementation goal, non-goals, acceptance, decisions, selected depth, and rollback | Retain for a named implementation or review decision, then as historical evidence |
| evidence/checks.md | Criteria, commands, revisions, environment, results, evidence paths, and invalidation conditions | Retain under project evidence policy, outside default recovery reads |
| evidence/review.md | Review scope, revision, reader, findings, triage, repairs, round count, and unresolved items | Retain under project evidence policy, outside default recovery reads |

For delegated work, keep plans and evidence beside each slice's plan.
Keep integrated evidence under the parent task root. Reference shared scope and acceptance instead of duplicating them.
Keep transcripts, chronological updates, completed task catalogs, and verbose logs outside working records.
Accepted dependency results may retain a short artifact and evidence reference while unfinished work still needs them.
Agent completion does not establish task acceptance. Track relevant agent IDs separately from acceptance.

## Replacement and exit

Update affected sections after scope, ownership, a material result, a blocker, acceptance, or process state changes.
Record dispatch before dependent work starts. Record results before another decision depends on them.
Replace the previous value in place. Do not append an event narrative or a second summary.
Preserve decision reasons only while they constrain unfinished work. Preserve detailed reasons in the owning plan or evidence.
If no relevant fact changes, leave the records unchanged, including review dates.
Before a work switch or context transition, reconcile the current records and recovery route.

Remove accepted TODO rows after the dependency condition in the table is satisfied.
Keep the final result and evidence reference in the closure receipt, not as a growing done list.
Cancellation ends a task only after its obligations and command state are resolved or explicitly transferred.

Close a task only after acceptance, required review, dependent work, and handoffs are complete.
Confirm that modifying commands have stopped. Unknown process state prevents closure and conflicting writes.
Resolve remaining obligations or transfer them to an identified owner and accessible task before closure.
Do not mark unfinished or merely inactive work closed.

At closure, replace STATE.md with a receipt: closed status, accepted result, evidence references, and remaining limitations.
Replace HANDOFF.md with a closed marker that has no automatic read route.
Empty TODO.md or remove it if project policy permits. Remove the task from active selectors.
Do not copy it into a growing closed-task index or create an automatic per-update archive.
Retain evidence in place when required. Reopen only through an explicit task need and artifact reconciliation.

## Selective reads and recovery

New work reads applicable instructions and the memory selector, if present. It does not read previous task records.
A selector contains only reuse conditions and section or artifact pointers.
Do not turn it into a lesson summary, complete artifact inventory, or task history.
If task identity is unclear, use current instructions or ask for the missing identity instead of reading every task directory.

For an identified active task:

1. Read HANDOFF.md for status and the next action.
2. Read only the sections it names that affect that action.
3. Check current user scope, relevant artifact revisions, ownership, and process state before dependent work.
4. Resolve conflicts from the relevant artifacts and evidence.
5. Replace stale facts and continue the next ready action.

Use STATE.md for a scope or execution-condition question and TODO.md for scheduling or dependency questions.
Read plans for implementation or review decisions. Read check evidence only for acceptance, invalidation, failure, or audit questions.
A closed handoff stops recovery. Inspect its receipt only for an explicit historical or reopening question.
Locate a named section through its heading, then extract that section instead of reading the whole file.
Do not follow links recursively. Required project checks and whole-change reviews still read their complete required artifacts.
Do not repeat passing checks unless relevant inputs changed or the evidence cannot be recovered.
Records assist recovery but do not guarantee runtime context preservation.

## Transfer and retention

Before ownership transfer, establish that the previous owner's modifying commands have stopped.
Record unknown process state and prevent conflicting writes until it is resolved.
Give the successor task IDs, the next action, relevant record sections, and required inputs with their revisions.
Provide ignored or untracked inputs through explicit copies or accessible paths. Verify receiving-workspace access before dependent work.
Do not copy transcripts or every project record into a brief.

Follow project Git, evidence, and deletion policies. Do not force-add ignored files.
Without a deletion policy, retain historical evidence locally but exclude closed tasks from default reads.
Do not delete another task's records or perform bulk historical cleanup without authorization.
Retention is not a requirement to reload history. Physical deletion is separate from leaving the active read route.

## Project memory lifecycle

Use project-root MEMORY.md unless the project selects another location. Keep task state outside project memory.
At entry, inspect only its selector or relevant headings. Read a detail section when its reuse condition matches the task.
Pass relevant sections or accessible references to executors. A memory path does not require a whole-file read.
If relevant memory is unavailable, report the gap. Do not claim knowledge from missing context.

Admit an entry only when all these conditions hold:

- A user statement or observed artifact supports it.
- It can change a concrete decision in future work beyond this task.
- Current instructions and authoritative project documentation do not already provide it.
- Its scope, reuse condition, source, and invalidation condition are identifiable.

Use dates for sourced decisions or observations, not as a task-completion diary.
Place permanent project rules in the governing instructions and maintained operational facts in their authoritative documentation.
Keep memory for otherwise missing exceptions, preferences, and lessons. Exclude unsupported habits, secrets, transcripts, and temporary status.
Memory never grants authorization or overrides current instructions.

At completion, review the available session for qualifying additions, corrections, and removals.
If missing context prevents a decision, inspect the specific relevant record and disclose the gap.
Do not reload every old record to perform the review. Do not invent missing facts.
A useful review may produce no change. Do not append a review outcome or update a date merely to prove review occurred.

Before writing, reread affected entries and the selector. Reconcile concurrent changes and preserve one writer at a time.
If another writer changes the file, reread it before saving. Do not overwrite conflicting evidence silently.
With a coordinator, executors return sourced candidates and the parent alone writes shared memory.
Without a coordinator, the task owner serializes updates with other sessions.
Merge duplicates and replace corrected facts. Remove an entry and its selector when superseded, invalidated, or covered by authoritative documentation.
If only an explicit historical question still needs it, retain its source outside default memory reads.
Do not keep a copied superseded entry or a deletion log in MEMORY.md.

## Recovery example

A CSV parser task remains blocked after a quoted-field check fails.
TODO.md retains its owner and blocker. Check evidence holds the failing revision and output.
HANDOFF.md names the parser task, next diagnostic action, and specific check section.
A new context reads that route, then checks relevant ownership and process state before repair.
After acceptance, the parser row leaves TODO.md when no unfinished dependency needs it.
The closed task keeps an evidence receipt. An unrelated new task reads none of these records.
