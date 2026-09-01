# decisions/

Every material decision, one file, date-slugged `YYYY-MM-DD-<slug>.md`.

A decision is material — and belongs here — if **either** is true: reversing it later would cost more than an hour of rework, or a downstream subagent would build on it. Threshold defined in [`CLAUDE.md`](../CLAUDE.md). Everything else is just work and does not get logged.

## Index

Newest first. Keep this current — a decisions folder you have to `ls` to navigate is a decisions folder nobody reads.

| Date | Decision | Status |
|---|---|---|
| 2026-09-01 | [Subagents are roles, not processes](2026-09-01-subagent-execution-model.md) | DRAFT |
| 2026-09-01 | [Tentative 6-subagent taxonomy](2026-09-01-subagent-taxonomy.md) | AWAITING RATIFICATION |
| 2026-09-01 | [Repo + Markdown as sole source of truth](2026-09-01-architecture.md) | AWAITING RATIFICATION |

## Statuses

| Status | Meaning |
|---|---|
| `DRAFT` | Written by a subagent. Minahil has not seen it. |
| `AWAITING RATIFICATION` | Minahil has seen it, or the file claims she has, but no sign-off is recorded. |
| `APPROVED` | Minahil signed off. The `Approved by` line names her and the date. |
| `SUPERSEDED` | Replaced by a later decision. Link forward to it. Never delete. |

## Rules

- A decision file is not approved because it was committed. It is approved when Minahil says so and the `Approved by` line is filled in.
- Never write an approver's name into a file they have not seen.
- Superseded decisions stay in the folder. The audit trail is the point — deleting a reversed decision hides why it was reversed.
- Never cite a document that does not exist in this repo.
