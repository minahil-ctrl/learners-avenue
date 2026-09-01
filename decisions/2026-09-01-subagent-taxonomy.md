# Decision: Tentative 6-subagent taxonomy

**Date:** 2026-09-01
**Status:** APPROVED
**Approved by:** Minahil Hamdani, 2026-09-01

## Decision

The build runs on six subagents:

- **SA-0** Chief of Operations
- **SA-1** Market Research
- **SA-2** Strategy & Positioning
- **SA-3** Tech Build
- **SA-4** Tutor Pipeline
- **SA-5** GTM

Sub-subagents nest inside parent folders as domains prove too broad. Taxonomy is tentative — refined after `ACTIVITY-BACKLOG.md` is populated.

## Rationale

- Six is a working structure, not a derived number. The pre-scaffold plan originally cited here did not exist in this repo and has been removed per Minahil's instruction (2026-09-01). The six-subagent count is tentative and subject to revision after the backlog is populated.
- **Sequencing** is the point: SA-5 dormant until pilot, SA-4 until unit economics, SA-3 until MVP scope. Prevents wasted work on unvalidated assumptions.
- Nesting sub-subagents inside folders (not renamed files) makes expansion cheap.

## Refinement — 2026-09-01

After audit: taxonomy approved at six roles, but only two roles are **active** until the backlog reveals what the work actually is:

- **SA-0** — Active
- **SA-1** — Active (first activation pending backlog completion)
- **SA-2 through SA-5** — Dormant stubs. Charters exist but are provisional. Structure derived from the backlog, not imposed before it.

SA-5 exception: SA-1 will gather channel evidence (where the ICP spends time online) as part of its research scope. That output feeds SA-2 strategy, not SA-5 — SA-5 stays dormant until post-strategy.

## Open questions

- **Finance & legal:** SA-6 or workstream under SA-2? Decide after backlog surfaces the volume of work.
- **GTM sub-subagents** likely: branding, content, posting, referrals. Confirm after backlog.
- **Tech build sub-subagents** likely: frontend, backend, agent-workflows. Confirm after MVP scope.

## Revisit

After `ACTIVITY-BACKLOG.md` is populated end-to-end. Update this file with the final assignments and log a follow-up decision if the taxonomy changes materially.
