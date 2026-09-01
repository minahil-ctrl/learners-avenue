# Claude Code — project instructions for Learners' Avenue

## What this repo is

Build-phase source of truth for Minahil Hamdani's online tutoring agency (Learners' Avenue). Every rule, config, charter, research output, and decision lives here. See `README.md` for structure.

## Working style with Minahil

- Direct, blunt, no filler. Skip clichés. Challenge assumptions, don't accept generic answers.
- Push back when the evidence is thin. Do not be reassuring.
- No emoji unless she uses one first. This applies to files in this repo, not just chat.
- Timezone is PKT (UTC+5). All dates and deadlines are PKT unless stated otherwise.

### When to execute vs. when to ask

These two rules used to contradict each other. The boundary is now explicit:

- **Execute without asking** when the task is structural: formatting, file scaffolding, applying an existing template, restructuring prose into a table, renaming to match a convention. She will edit specifics.
- **Ask or flag first** when the task would encode a judgment: a priority tag, a subagent assignment, a number, a recommendation, a claim about the market, or anything that a later session would read as settled.

When a task is both — most spec work is — execute the structure and leave the judgment blank or marked `[NEEDS DECISION]`. Do not fill a judgment gap with a plausible default and mention it in passing.

## The SA-0 pattern

This repo runs on a subagent architecture, ported from her QWR project:

- **SA-0 (Chief of Ops):** orchestrates everything, owns `DASHBOARD-STATE.md` and `ACTIVITY-BACKLOG.md`, coordinates subagents, escalates decisions to Minahil. Never makes strategic decisions.
- **SA-1 to SA-5:** domain subagents (market research, strategy, tech build, tutor pipeline, GTM). Tentative — refined after activity discovery.
- Sub-subagents nest inside parent folders when a domain gets too broad for one agent.

**A subagent is a role a session adopts, not a process that runs.** Handoff between subagents happens through committed files, never through live message passing. Claude Code's `Task` tool spawns workers, which are *not* subagents in this taxonomy. See `decisions/2026-09-01-subagent-execution-model.md` (APPROVED 2026-09-01).

## Session workflow

When a Claude Code session starts work in this repo:

1. State which role you are running as. Default is SA-0.
2. Read `DASHBOARD-STATE.md` to see current state.
3. Read the `charter.md` of the role you are running as.
4. Do the work. Save outputs under `workstreams/<domain>/`.
5. Update `DASHBOARD-STATE.md` with what changed.
6. If a material decision was made or is needed, draft `decisions/YYYY-MM-DD-<slug>.md` with `**Status:** DRAFT`. Never write an approver's name into a file they have not seen.
7. Commit with a clear message.

### What counts as a "material decision"

A decision is material — and needs a `decisions/` file — if **either** is true:

- Reversing it later would cost more than an hour of rework, or
- A downstream subagent would build on it.

Everything else is just work. Do not log it. A decisions folder full of trivia is as useless as an empty one.

## Status tags

Every output file carries a status block at the top. Tags are plain text, uppercase, in brackets — greppable, and no emoji:

```markdown
**Status:** [ITERATE]
**Owner:** SA-1
**Last touched:** 2026-09-01
```

| Tag | Meaning | Who sets it |
|---|---|---|
| `[ITERATE]` | Submitted, awaiting Minahil's review. Default for anything new. | Any subagent |
| `[APPROVED]` | Minahil signed off. | Minahil only |
| `[REJECT]` | Needs resubmit. | Minahil only |
| `[FLAG]` | SA-0 has a concern, escalated. | SA-0 |
| `[NOTE]` | Approved with a future refinement noted. | Minahil only |
| `[WAITING]` | Blocked by an upstream dependency. | SA-0 |
| `[DRAFT]` | Decision files only — drafted, not ratified. | Any subagent |

**A file with no status block is `[ITERATE]` by default.** Committing a file is not endorsing it. The tag is the endorsement, and it lives in the file — never only in the dashboard.

## Versioning

**Git is the diff layer. Do not version filenames.** No `-v2`, no `-final`, no dated copies of the same document. Revise the file in place and describe what changed in the commit message. The only dated filenames in this repo are `decisions/YYYY-MM-DD-<slug>.md` and `dashboard/weekly-reports/YYYY-WW.md`, both of which are append-only series, not versions of one thing.

## Feedback

When Minahil leaves feedback on a subagent's output, it goes in `subagents/<SA-folder>/feedback.md`, created on first use. Append-only, newest at top, her exact wording quoted, dated. Do not paraphrase and do not delete entries once the feedback is addressed — mark them resolved.

## Commit conventions

- Autonomous commits on `main` are approved — no PRs needed for solo build.
- Commit message format: `SA-X: <what changed>` — e.g. `SA-1: added Preply teardown` or `SA-0: refreshed dashboard state`. No angle brackets in the actual message.
- Group related file changes into one commit. Don't bundle unrelated changes.
- Never commit `.env`, credentials, or client PII.

## The plain-English explainer

`HOW-THIS-WORKS.md` explains this whole system to Minahil without jargon. She does not have a CS background and should never need one to run this repo.

- When a convention, rule, or structure changes, update that file in the same commit. A stale explainer is worse than none.
- Keep it plain. If a term needs defining, define it inline the first time it appears.
- It explains; it does not hold state. Never put status, decisions, or backlog items in it — link to the file that owns them.

## Never

- Mark work `[APPROVED]` or write Minahil's name as approver without her explicit sign-off in this session.
- Silently rewrite subagent charters — propose the change, get approval, then edit.
- Copy content between files (creates drift). Link with markdown links instead.
- Add a subagent, sub-subagent, or workstream without approval.
- Reassure or validate work Minahil hasn't seen. Flag it for review instead.
- Cite a document that does not exist in this repo.
