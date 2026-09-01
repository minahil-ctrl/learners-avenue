# Learners' Avenue

Private repo for the build phase of Minahil's online tutoring agency.

## What this is

Source of truth for every rule, config, spec, charter, research output, and decision that goes into designing and building Learners' Avenue. Pre-launch. Every commit is a step in the build.

## Start here

New to this, or coming back after a break? Read [`HOW-THIS-WORKS.md`](HOW-THIS-WORKS.md) — the whole system in plain English, no jargon, no CS background assumed.

## Structure

- `HOW-THIS-WORKS.md` — plain-English explanation of the entire setup. Written for Minahil.
- `ACTIVITY-BACKLOG.md` — master list of every job across all six domains. Populated in workstream 1.
- `DASHBOARD-STATE.md` — current status: active work, blockers, decisions pending. SA-0 keeps this current.
- `CLAUDE.md` — instructions Claude Code reads on every session in this repo. Also the single definition of the status-tag system, the material-decision threshold, and commit conventions.
- `subagents/` — one folder per subagent, each containing `charter.md` and (on first use) `feedback.md`. SA-0 included. Sub-subagents nest inside as they emerge.
- `workstreams/` — outputs of each subagent, organized by domain.
- `decisions/` — log of every material decision. One file per decision, date-slugged. See `decisions/README.md` for the index.
- `dashboard/` — weekly reports and (deferred) any future visualization layer.

## How the subagents actually work

A subagent is a **role a Claude Code session adopts by loading a charter** — not a process, not a separate app, not an autonomous actor. Handoff between subagents happens through committed files, never through live message passing. See `decisions/2026-09-01-subagent-execution-model.md` (currently DRAFT).

## Status

Pre-launch. Build phase. First active workstream: activity discovery (populate `ACTIVITY-BACKLOG.md`).

Three decisions are open and block downstream work — see the top of `DASHBOARD-STATE.md`.

## Who reads what

- **Minahil:** `DASHBOARD-STATE.md` every morning. `decisions/` when reviewing. Subagent charters when adjusting scope.
- **Claude Code sessions:** `CLAUDE.md` (auto-loaded), plus any file relevant to the current task.
- **SA-0:** all files. Owns keeping `DASHBOARD-STATE.md` and `ACTIVITY-BACKLOG.md` current.

## First-run setup

1. `git init && git add . && git commit -m "SA-0: initial scaffold"`
2. Create the private GitHub repo, add as remote, push.
3. Open the repo in Claude Code. `CLAUDE.md` loads automatically.
4. Clear the open decisions at the top of `DASHBOARD-STATE.md`.
5. Start workstream 1: populate `ACTIVITY-BACKLOG.md`.
