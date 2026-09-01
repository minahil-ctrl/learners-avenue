# Dashboard — Learners' Avenue

**Last updated:** 2026-09-01 (PKT)
**Phase:** Pre-launch / Build
**Active workstream:** Activity discovery (populating `ACTIVITY-BACKLOG.md`)

> Confused by anything below? [`HOW-THIS-WORKS.md`](HOW-THIS-WORKS.md) explains the whole system in plain English.

---

## Awaiting Minahil's decision

| # | Item | Raised | Waiting | Blocks |
|---|---|---|---|---|
| 1 | Ratify or reject `decisions/2026-09-01-subagent-execution-model.md` (DRAFT) | 2026-09-01 | New | SA-1 activation |
| 2 | Confirm the two pre-existing decision logs were actually approved by you — both asserted your approval with no evidence, now downgraded to `AWAITING RATIFICATION` | 2026-09-01 | New | Clean audit trail at commit 1 |
| 3 | Locate or discard the "pre-scaffold plan (steps 1–10)" cited by the taxonomy decision — not present in this repo | 2026-09-01 | New | Taxonomy decision is unverifiable without it |
| 4 | Decide whether `GTM-Dashboard/` (sibling directory, live git repo, Supabase + Netlify) holds any Learners' Avenue state | 2026-09-01 | New | The no-parallel-state rule |
| 5 | Confirm or replace the `≥40 backlog items` target — currently an arbitrary number with no basis | 2026-09-01 | New | Nothing. Cosmetic but it is a fake metric. |
| 6 | Confirm strict subagent sequencing vs. running SA-1 and SA-5 in parallel on channel evidence | 2026-09-01 | New | SA-5 timing |

---

## Active this week

| Subagent | Current focus | Status | Blocker |
|---|---|---|---|
| SA-0 | Repo scaffolding, charter repair, dashboard maintenance | `[ITERATE]` | Items 1–3 above |
| SA-1 | Dormant — activates after activity backlog populated | `[WAITING]` | `ACTIVITY-BACKLOG.md` |
| SA-2 | Dormant — activates after SA-1 delivers research pack | `[WAITING]` | SA-1 |
| SA-3 | Dormant — activates after niche + MVP scope approved | `[WAITING]` | SA-2 |
| SA-4 | Dormant — activates after unit economics approved | `[WAITING]` | SA-2 |
| SA-5 | Dormant — activates during pilot | `[WAITING]` | Pilot |

---

## Recent completions

- **2026-09-01** — Repo scaffolded: SA-0 charter, SA-1 to SA-5 skeleton charters, backlog + dashboard templates.
- **2026-09-01** — Scaffold audited by SA-0. Charter contradictions repaired, status-tag system made greppable and emoji-free, decision-file approval fields corrected. All changes `[ITERATE]`.

> Architecture and taxonomy decisions are **not** listed as completions. Both are logged as `AWAITING RATIFICATION` pending item 2 above. See `decisions/`.

---

## Next up (in order)

1. Clear items 1–3 in the decision queue. Nothing downstream is safe until the execution model is settled.
2. Populate `ACTIVITY-BACKLOG.md` — every job across all six domains, before subagent scoping finalizes.
3. Refine SA-1 through SA-5 charters based on the backlog.
4. Identify sub-subagents actually needed (e.g. GTM branding, posting) and nest them.
5. Decide whether Finance & Legal becomes SA-6 or stays under SA-2.
6. Activate SA-1 with a scoped market research plan.

---

## Weekly metrics

Metrics live in the weekly report, not here — see [`dashboard/weekly-reports/`](dashboard/weekly-reports/). Duplicating them in two files creates exactly the drift this repo exists to avoid.

**Current week:** 2026-W36. First report due at the first SA-0 session on or after Sunday 2026-09-06.

---

## Status legend

Defined once in [`CLAUDE.md`](CLAUDE.md). Not restated here.
