# Decision: Repo + Markdown as sole source of truth

**Date:** 2026-09-01
**Status:** AWAITING RATIFICATION
**Approved by:** _not recorded — see note below_

> **SA-0 note (2026-09-01):** this file originally read `Approved by: Minahil` with no record of when or how that approval was given. The scaffold asserted it. Downgraded pending Minahil's explicit confirmation. If she approved this before the scaffold was generated, restore the line and set Status to APPROVED.

## Decision

The Build Dashboard is a private GitHub repo containing markdown files, subagent charters, and decision logs. No Notion. No visual Artifact dashboard. `DASHBOARD-STATE.md` is the human-readable status page; SA-0 keeps it current.

## Alternatives considered

1. **Notion as source of truth (like QWR)** — rejected. Duplicates the repo, introduces sync overhead, weak on versioning.
2. **Notion + repo hybrid** — rejected. Two sources of truth = drift.
3. **Repo + Artifact dashboard** — deferred. State is too small pre-launch to justify a visualization layer. GitHub already renders markdown; that's enough. Revisit in 3–4 weeks if information density grows.

## Rationale

- Repo already versions, diffs, and PR-ables everything for free.
- Claude Code operates natively on files, not on Notion.
- Markdown is portable — future migration to any dashboard tool is trivial.
- Single source of truth = no drift.

## Consequences

- No visual kanban until we (optionally) turn on GitHub Projects later.
- SA-0's dashboard maintenance is a text-editing job, not a UI job.
- Minahil reads status in a markdown file, not in a rendered UI.
- Every state change is a commit — full audit trail.

## Open questions

- `GTM-Dashboard/` (sibling directory, separate git repo) belongs to AgentFlo / Salesflo — Minahil's professional work, unrelated to Learners' Avenue. Confirmed 2026-09-01. No overlap with this repo. Item closed.

## Revisit if

- Information density grows past what one markdown file can show at a glance.
- Multiple people join and need shared visual views.
- A public status page becomes useful (mentors, co-founders, hires).
