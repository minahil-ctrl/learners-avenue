# Claude Code — project instructions for Learners' Avenue

> **If you are a new Claude instance reading this for the first time:** this file is your complete briefing. Read it fully before doing anything. Then read `DASHBOARD-STATE.md` for current sprint state and `PROJECT-BRIEF.md` for full business context. Do not ask Minahil to re-explain what the project is — it is all here.

---

## 1. What This Project Is

**Learners' Avenue** is an online tutoring agency built by Minahil Hamdani, a solo founder based in Pakistan. She currently teaches at Tutoronics (no non-compete clause) serving UAE and KSA students, and is building this agency in parallel.

**The business in one sentence:** A curated tutoring agency — not a marketplace — serving South Asian expat families in the UAE, specialising in Business Studies, Economics, and English Language at O and A-level (Cambridge CAIE and Edexcel IAL).

**Why curated, not marketplace:** Parents care about tutor credibility, not platform brand. A marketplace requires trust in ratings. A curated agency requires trust in the founder, which Minahil already has via her personal network.

**Acquisition model at launch:** Community-first only — WhatsApp groups, Facebook parent groups, warm personal outreach. No paid ads until 10+ students.

**Payment:** Payoneer is the primary method for receiving USD from UAE parents. Stripe does not support Pakistan. Wise Personal works for receiving but is not a proper business account.

**The Sep 15, 2026 target:** One UAE parent commits to a trial session by Sep 15. One tutor assigned. Payment method live. This is the only milestone that counts on that date — not a website, not 10 students, not a brand. One booking.

---

## 2. Current State (as of 2026-09-02)

### Git state
- Branch: `main`
- 5 commits ahead of `origin/main` (user may or may not have pushed)
- Remote: `https://github.com/minahil-ctrl/learners-avenue`
- No uncommitted changes as of last session

### What is built and working
- Full repo scaffold with all key files (see section 4 below)
- `ACTIVITY-BACKLOG.md` — fully populated: 17 P0 tasks (Sep 4–9), 13 P1 tasks (Sep 7–12), 7 P2 tasks
- `PROJECT-BRIEF.md` — master reference document covering everything discussed in founding sessions
- `dashboard/la-os.html` — full operating system dashboard: domain tabs, stage view, task tables with expandable rows, dependency linking, content approval queue, resource panels, localStorage persistence
- `DASHBOARD-STATE.md` — current sprint status updated
- All founding decisions approved and filed in `decisions/`
- 3 Instagram posts drafted and in content queue (GTM domain → Content tab in dashboard), awaiting Minahil's approval

### What is NOT done yet (the work)
- No market research has been conducted (MR-001 through MR-004 all [DRAFT])
- No positioning statement written (STR-001)
- No pricing locked (STR-003)
- No tutors sourced, screened, or signed (TUT-001 through TUT-005)
- Payoneer not set up (TECH-001) — Minahil must do this herself, Claude cannot
- WhatsApp Business not set up (TECH-002) — same
- No outreach sent to UAE contacts (GTM-001, GTM-002)
- Instagram profile not created (GTM-004)
- No content approved or posted

### Immediate blockers (Sep 4 deadline, 2 days from last session)
1. **MR-001** — Tutoronics intelligence. SA-1 session with Minahil: she answers structured questions from memory, Claude writes it up and commits.
2. **TECH-001** — Payoneer setup. Minahil does this alone at payoneer.com.
3. **TECH-002** — WhatsApp Business. Minahil does this alone.
4. **TUT-001** — Tutor spec. SA-4 session: draft the subject requirements, board knowledge, availability, home setup criteria.

---

## 3. Working Style with Minahil

- Direct, blunt, no filler. Skip clichés. Challenge assumptions, do not accept generic answers.
- Push back when the evidence is thin. Do not be reassuring.
- No emoji unless she uses one first. Applies to files and chat.
- Timezone: **PKT (UTC+5)**. All dates and deadlines are PKT unless stated otherwise.
- She does not have a CS background. Plain language in all files she reads.
- She is a solo founder working full-time elsewhere. Respect her attention. Be efficient.

### When to execute vs. when to ask

- **Execute without asking:** structural tasks — formatting, scaffolding, applying an existing template, restructuring prose into a table, renaming to match a convention.
- **Ask or flag first:** anything that encodes a judgment — a priority tag, a number, a recommendation, a claim about the market, a strategic call.
- When a task is both: execute the structure, leave judgment blank or marked `[NEEDS DECISION]`. Do not fill a judgment gap with a plausible default and mention it in passing.

---

## 4. Key Files — What Each Is and When to Read It

| File | What it is | Read when |
|---|---|---|
| `CLAUDE.md` | This file. Auto-loaded every session. | Always first. |
| `DASHBOARD-STATE.md` | Current sprint status: active work, blockers, recent completions. | Every session start. |
| `PROJECT-BRIEF.md` | Master reference: business overview, market, service model, sprint tasks, decisions log, resources inventory, content pipeline. 15 sections. | First session, or when context is needed. |
| `ACTIVITY-BACKLOG.md` | All 37 tasks (P0/P1/P2) with deadlines, statuses, notes. | When planning or updating task status. |
| `HOW-THIS-WORKS.md` | Plain-English explainer for Minahil. No jargon. | When a system or convention changes — update it. |
| `dashboard/la-os.html` | Full operating system dashboard (HTML). | Read to update; publish via Artifact tool. |
| `decisions/README.md` | Index of all decisions. | Before filing a new decision. |
| `decisions/2026-09-01-*.md` | Three founding decisions (APPROVED). | When architecture or subagent model is in question. |
| `subagents/<SA>/charter.md` | Job description for each role. | When adopting that role. |

---

## 5. Subagent Architecture

A subagent is a **role a Claude Code session adopts by reading a charter**. Not a process. Not an autonomous actor. One session, one role.

**Handoff:** SA-1 finishes work, commits a file. A later session reads that file as SA-2. The file is the only channel. There is no live message passing.

| Role | Charter | Status | Activates when |
|---|---|---|---|
| SA-0 — Chief of Ops | `subagents/SA-0-chief-of-ops/charter.md` | Always active | Default for every session |
| SA-1 — Market Research | `subagents/SA-1-market-research/charter.md` | Ready to activate | Minahil starts the session |
| SA-2 — Strategy | `subagents/SA-2-strategy/charter.md` | Dormant | After SA-1 delivers Tutoronics intel |
| SA-3 — Tech Build | `subagents/SA-3-tech-build/charter.md` | Ready to activate | Minahil starts the session |
| SA-4 — Tutor Pipeline | `subagents/SA-4-tutor-pipeline/charter.md` | Ready to activate | Minahil starts the session |
| SA-5 — GTM | `subagents/SA-5-gtm/charter.md` | Dormant | After SA-2 sets pricing |

SA-3 and SA-4 can activate in parallel immediately — they do not wait on research. SA-1 and SA-2 must run in sequence. SA-5 needs a positioning statement and pricing before it can operate.

### Session workflow (every session, in order)
1. State which role you are running as. Default: SA-0.
2. Read `DASHBOARD-STATE.md`.
3. Read the charter of the role you are adopting.
4. Do the work. Save outputs under `workstreams/<domain>/`.
5. Update `DASHBOARD-STATE.md` with what changed.
6. If a material decision was made: draft `decisions/YYYY-MM-DD-<slug>.md` with `**Status:** DRAFT`.
7. Commit with message format: `SA-X: <what changed>`.

---

## 6. Decisions Made and Why

### Subagents are roles, not processes (APPROVED 2026-09-01)
File: `decisions/2026-09-01-subagent-execution-model.md`

Previous scaffold described subagents "working overnight" and "handing off" to each other — a fiction. The honest model: session adopts a role, does work, commits files, session ends. Nothing happens while Minahil is away.

### Repo + Markdown as sole source of truth (APPROVED 2026-09-01)
File: `decisions/2026-09-01-architecture.md`

No Notion. No Trello. No parallel dashboards. Every previous attempt at Learners' Avenue (2023, 2024, 2025) built infrastructure that was never connected to execution. The repo is the forcing function: if it is not committed, it does not exist.

### Two active subagents at launch (APPROVED 2026-09-01)
File: `decisions/2026-09-01-subagent-taxonomy.md`

Writing detailed job descriptions for six roles before knowing what the jobs actually are is backwards. SA-0 and SA-1 are active. SA-2 through SA-5 are dormant stubs. They are refined after the backlog defines the work.

### Sep 15 as first-booking target (implicit — not yet filed)
The target is one confirmed booking from one UAE parent. Not a website. Not 10 students. One booking, because it is the only signal that the core thesis (someone will pay for this) is true.

**To do:** file `decisions/2026-09-02-sep15-milestone.md` at the start of the next SA-0 session.

### Payoneer, not Stripe (corrected 2026-09-02)
Stripe does not support Pakistan. Payoneer is the primary payment method. Wise Personal works for receiving but is not a proper business account. This correction is reflected in `ACTIVITY-BACKLOG.md`, `PROJECT-BRIEF.md`, and `dashboard/la-os.html`.

### Core failure pattern from previous attempts (diagnostic, not a decision)
Three previous attempts at Learners' Avenue (2023, 2024, 2025) all had the same failure mode: infrastructure was built before any customers were acquired. The Sales and GTM departments were never created — zero tasks, zero owners, zero deadlines across all three attempts. The 2025 marketing planner had every post status as "Pending" with no posts ever made. The Leadership Workspace had empty sheets for every department.

The fix: the Sep 15 target is a booking, not infrastructure. The backlog is ordered by what blocks a booking first.

---

## 7. Conventions and Patterns

### Status tags
Every output file carries a status block. Tags are plain text, bracketed, uppercase — greppable. No emoji.

```markdown
**Status:** [ITERATE]
**Owner:** SA-1
**Last touched:** 2026-09-02
```

| Tag | Meaning | Who sets it |
|---|---|---|
| `[ITERATE]` | Submitted, awaiting review. Default for everything new. | Any subagent |
| `[APPROVED]` | Minahil signed off. | Minahil only |
| `[REJECT]` | Needs resubmit. | Minahil only |
| `[FLAG]` | SA-0 has a concern. Escalated. | SA-0 |
| `[NOTE]` | Approved with a future note. | Minahil only |
| `[WAITING]` | Blocked by an upstream dependency. | SA-0 |
| `[DRAFT]` | Decision files only — not yet ratified. | Any subagent |

Committing a file is not the same as approving it. Only Minahil can set `[APPROVED]`. Never write her name as approver without her explicit sign-off in the current session.

### Commit format
```
SA-X: <what changed>
```
Examples: `SA-1: added Tutoronics intel` / `SA-0: updated dashboard state`. Group related changes. Never bundle unrelated changes. Never commit `.env`, credentials, or client PII.

### Versioning
Git is the diff layer. No `-v2`, `-final`, or dated copies of the same document. Revise in place. The only dated filenames are `decisions/YYYY-MM-DD-<slug>.md` and `dashboard/weekly-reports/YYYY-WW.md`.

### Material decision threshold
A decision needs a `decisions/` file if **either**: reversing it costs more than 1 hour of rework, OR a downstream subagent builds on it. Everything else is just work — do not log it.

### Never
- Mark work `[APPROVED]` or write Minahil's name as approver without her explicit sign-off.
- Silently rewrite subagent charters — propose, get approval, then edit.
- Copy content between files (creates drift). Link instead.
- Add a subagent or workstream without approval.
- Reassure or validate work Minahil has not seen.
- Cite a document that does not exist in this repo.

---

## 8. What the OS Dashboard Is

`dashboard/la-os.html` is a full operating system dashboard — not a static page. It was built and published as a Claude artifact.

**Features:**
- Domain view (sidebar): task tables per domain with expandable rows, urgency strip (3 most urgent tasks), resource panel, content queue (GTM only)
- Stage view: all 36 sprint tasks grouped P0 / P1 / P2, domain-tagged
- Task table: ID, title, deadline, priority, status (click to cycle), blocker indicator, dependency chips (click navigates to that task's domain)
- Content queue: 3 Instagram posts drafted, each with caption and visual direction, approve/request-edit/post workflow
- Status persists via localStorage

**To update the dashboard:**
1. Edit `dashboard/la-os.html` in the repo
2. Publish via the Artifact tool with `url: "https://claude.ai/code/artifact/330791f9-4ac3-467f-8408-004a90dcaf6d"`
3. Commit the updated file

**Content queue — 3 posts awaiting approval (as of 2026-09-02):**
- C1: Tutor Intro — Business & Economics | Single Image | Sep 10
- C2: Subject Tip — Economics: PED vs PES | Carousel | Sep 11
- C3: Founder Story — Why I Started This | Single Image | Sep 12

Minahil approves in the dashboard. Once approved, SA-0 posts. This is the agreed workflow.

---

## 9. Exact Next Steps (in order)

These are the things to do at the next session. Run in this order.

### SA-0 session (file the missing decision)
1. File `decisions/2026-09-02-sep15-milestone.md` — the Sep 15 first-booking target has been operating as an implicit decision. Make it explicit.
2. Update `DASHBOARD-STATE.md` to reflect session start.
3. Commit.

### SA-1 session (Minahil must be present — she provides the intel)
Ask Minahil structured questions about Tutoronics. She answers from memory. Output: `workstreams/market-research/MR-001-tutoronics-intel.md`. This unblocks STR-001 (positioning) and STR-003 (pricing), both due Sep 5–6.

Questions to ask:
- What do parents most commonly complain about at Tutoronics?
- What is the standard rate per session and what do tutors actually receive?
- Which subjects have the longest waitlists?
- What do students say they wish their tutor did differently?
- What is the typical session length and format?
- Which UAE emirates have the most students?

### SA-4 session (can run in parallel with SA-1)
Write the tutor spec (`workstreams/tutor-pipeline/TUT-001-tutor-spec.md`). Fields: subject requirements, board knowledge (CAIE vs Edexcel IAL), level (O vs A), availability minimum, home setup requirements, deal-breakers. This is needed before sourcing begins Sep 6.

### What Minahil must do herself (Claude cannot do these)
- Set up Payoneer at payoneer.com — TECH-001
- Set up WhatsApp Business app with a dedicated number — TECH-002

---

## 10. Resources Inventory (brief)

Key archive files already read and catalogued (at `C:\Users\HP\Downloads\TutorsLearner Avenue archive\`):

| File | What it has | Used for |
|---|---|---|
| Student Registration (2023) | 5 students, Pakistani, Business/Biology/Islamiat | Market profile |
| Academic Dashboard | UAE: CAIE + Edexcel IAL confirmed | Tutor spec (MR-002) |
| Tutor Agreement (May 2024) | 5 signed agreements: Daniyal, Manahil, Shahzaib, Shamoon, Umer Imran | Agreement template (FIN-002) |
| Financial Plan | $25/session, 25% platform cut baseline | Pricing starting point |
| Locations doc | UAE 13, Nigeria 27, South Africa 20 demand points | Market prioritisation |
| Timetable (2023) | Rs. 6000 / 3 sessions / week | Rate baseline |

Full inventory with descriptions is in `PROJECT-BRIEF.md` section 10.

---

## 11. How to Orient a New Session Quickly

A new Claude instance reading this file can get fully operational with:

1. Read this file (CLAUDE.md) — done.
2. Read `DASHBOARD-STATE.md` — current sprint state, blockers, recent completions.
3. Read the charter of the role being adopted — e.g. `subagents/SA-1-market-research/charter.md`.
4. State the role aloud. Begin.

For full business context: `PROJECT-BRIEF.md`. For all tasks: `ACTIVITY-BACKLOG.md`. For past decisions: `decisions/README.md`.

Do not ask Minahil to re-explain the project. Everything is in these files.
