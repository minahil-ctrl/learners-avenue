# Learners' Avenue — Master Project Brief

**Status:** [ITERATE]
**Owner:** SA-0
**Last updated:** 2026-09-02 (PKT)
**Sprint target:** First booking confirmed by Sep 15, 2026

> This document is the single master reference for everything discussed, decided, and built during the founding sessions of Learners' Avenue. It is maintained by SA-0. Update it when strategy, scope, or architecture changes. Do not duplicate it — link to it.

---

## 1. What This Is

Learners' Avenue is an online tutoring agency serving South Asian expat families in the UAE. It is not a tutoring marketplace. It is a curated agency — Minahil selects, vets, and vouches for every tutor.

**Founder:** Minahil Hamdani (solo). Currently teaching at Tutoronics, UAE/KSA students. No non-compete clause.

**This is a personal venture built in parallel with full-time work.** The constraint is not money — it is time and attention. Every system in this repo exists to reduce coordination overhead so Minahil can run the agency without it running her.

---

## 2. Market & Positioning

### Target student
- South Asian expat families in the UAE (Pakistani, Indian, Bangladeshi, Sri Lankan)
- O-level and A-level students (Cambridge CAIE and Edexcel IAL)
- Subjects at launch: **Business Studies, Economics, English Language**
- Parents care about results and tutor credibility, not platform brand

### Why this market
- UAE has a large, established South Asian expat community with high educational aspiration
- O/A-level demand concentrated in UAE: CAIE and Edexcel IAL confirmed as dominant boards
- Community-first acquisition is viable: WhatsApp groups, Facebook parent groups, referrals
- Minahil is already inside this market via Tutoronics — she has direct insight into what parents want and what current providers fail at

### Geography at launch
- UAE (primary) — Abu Dhabi, Dubai, Sharjah
- KSA (secondary, organic only — Minahil's existing student base)
- Not targeting Pakistan market at launch

### Future markets (post-pilot, P2)
- Nigeria (27 O-level demand data points from archive)
- South Africa (20 data points)
- Kenya
- Timing: only after UAE pilot proves the model

### Acquisition strategy (Sep 2–15)
1. Warm outreach to 3 UAE contacts — personal network, conversations not pitches
2. WhatsApp Business for inbound
3. South Asian parent Facebook groups (join, observe, then participate)
4. No paid ads until 10+ students and unit economics are confirmed

### Positioning statement (draft — needs STR-001)
Not yet written. Will reference: who (South Asian O/A-level students in UAE), for whom (parents who want credibility assurance, not just availability), why different (every tutor passes a subject test and live teaching demo before being recommended).

---

## 3. Service Model

**Curated agency.** Minahil selects and vets tutors. Parents book through the agency. Minahil is the quality guarantee — not an algorithm, not reviews.

This was confirmed as the right model over a marketplace because:
- A marketplace requires trust in the platform's rating system, which a new entrant cannot build quickly
- A curated model requires trust in the founder, which Minahil already has with her personal network
- It is operationally simpler for a solo founder — fewer moving parts
- It commands a premium price point

### Subjects at launch
- Business Studies (O and A-level, CAIE + Edexcel IAL)
- Economics (O and A-level, CAIE + Edexcel IAL)
- English Language (O and A-level, CAIE + Edexcel IAL)
- Business and Economics often covered by the same tutor

### Expansion subjects (post-pilot)
- Other social sciences
- STEM subjects (only once tutor pipeline model is proven)

---

## 4. Pricing (draft — needs STR-003 to lock)

Starting point from archive financial plan: **$25/session** for 1-on-1 tutoring.

To validate against:
- Tutoronics pricing intelligence (MR-001)
- Competitor pricing (MR-003)

Package model: per-session + monthly packages at a slight discount.

Trial rate: discounted first session ($15 or free 30 min) to reduce barrier to first commitment.

Currency: USD for international parents, PKR for Pakistan-side accounting.

Tutor payout: per session, within 48 hours of session completion.

---

## 5. Payment Infrastructure

**Stripe (Pakistan registration)** or **Wise** — whichever goes live first. Both are being set up in parallel (TECH-001).

Flow:
```
Parent → Stripe/Wise → Minahil (platform) → Tutor payout (within 48h)
```

The platform's margin is the spread between what parents pay and what tutors receive. Exact split to be confirmed in STR-003 / FIN-001.

---

## 6. Sprint: Sep 2–15, 2026

**Goal:** One UAE parent has committed to a trial session by Sep 15. Payment method is live. One tutor is assigned.

This is the only milestone that counts on September 15.

### Why Sep 15
13 days from today (Sep 2). Short enough to force prioritisation. Long enough to set up the minimum infrastructure. The Sep 15 target is a forcing function — it defines what is P0 and what is P2.

### P0 — Do first, these block everything (17 items, Sep 4–9)

| ID | Domain | Task | Due |
|---|---|---|---|
| MR-001 | Market Research | Document Tutoronics intelligence | Sep 4 |
| MR-002 | Market Research | Confirm UAE exam board split | Sep 4 |
| TECH-001 | Tech Build | Set up Stripe or Wise | Sep 4 |
| TUT-001 | Tutor Pipeline | Define tutor spec | Sep 4 |
| MR-003 | Market Research | Map 3 competitor agencies | Sep 5 |
| STR-001 | Strategy | Write positioning statement | Sep 5 |
| STR-002 | Strategy | Confirm service model (curated agency) | Sep 5 |
| TECH-002 | Tech Build | Set up WhatsApp Business | Sep 5 |
| TUT-002 | Tutor Pipeline | Source 8–10 candidates | Sep 6 |
| STR-003 | Strategy | Set pricing (USD + PKR) | Sep 6 |
| GTM-001 | GTM | Identify 3 UAE contacts for outreach | Sep 6 |
| FIN-001 | Finance | Finalize pricing model | Sep 6 |
| TUT-003 | Tutor Pipeline | Screen candidates | Sep 8 |
| TUT-004 | Tutor Pipeline | Set tutor rates and payout schedule | Sep 8 |
| FIN-002 | Finance | Update tutor agreement template | Sep 8 |
| TUT-005 | Tutor Pipeline | Sign agreements with 3 tutors | Sep 9 |
| GTM-002 | GTM | Send first warm outreach | Sep 9 |

### P1 — By Sep 15, launch infrastructure (13 items, Sep 7–12)

| ID | Domain | Task | Due |
|---|---|---|---|
| MR-004 | Market Research | Identify 5 South Asian parent groups in UAE | Sep 7 |
| TECH-003 | Tech Build | Set up Calendly for booking | Sep 7 |
| GTM-003 | GTM | Design trial session offer | Sep 8 |
| GTM-004 | GTM | Create Instagram profile | Sep 8 |
| TECH-004 | Tech Build | Invoice template | Sep 8 |
| STR-004 | Strategy | Design referral mechanic | Sep 9 |
| GTM-005 | GTM | Join 2 UAE parent Facebook groups | Sep 9 |
| TECH-005 | Tech Build | One-page landing (Carrd or Notion) | Sep 10 |
| TECH-006 | Tech Build | Student/session tracker spreadsheet | Sep 10 |
| FIN-003 | Finance | Draft student terms of service | Sep 10 |
| FIN-004 | Finance | Document payment flow | Sep 10 |
| FIN-005 | Finance | Payment tracker spreadsheet | Sep 10 |
| GTM-006 | GTM | Post first 3 content pieces | Sep 12 |

### Sep 15 Milestone
First booking confirmed. One parent. One tutor assigned. Payment live.

### P2 — Post-launch, first 30 days (do not touch before Sep 15)
- Validate name "Learners' Avenue" for Gulf market
- Africa market exploratory scan (Nigeria, South Africa, Kenya)
- Full website build (only after 5 students)
- Content calendar weeks 3+
- Paid ads (only after organic baseline)
- Second tutor cohort (only after student volume justifies it)

---

## 7. Subagent Architecture

### What a subagent is
A role that a Claude Code session adopts by loading a charter file. Not a process. Not an autonomous actor. One session, one role, one hat.

**Handoff between subagents happens through committed files only.** SA-1 finishes research, saves and commits a file. A later session loads the SA-2 charter and reads that file. The file is the only channel.

### Active subagents (Sep 2, 2026)

| Role | Who | Status | What it does |
|---|---|---|---|
| SA-0 — Chief of Ops | Claude Code session | Active | Keeps files organised, dashboard current, escalates decisions. Never makes strategic decisions. |
| SA-1 — Market Research | Claude Code session | Ready to activate | Finds evidence: competitors, demand, pricing, market data. Every claim cites a source. |
| SA-2 — Strategy | Claude Code session | Dormant (waits for SA-1) | Turns evidence into decisions: positioning, pricing, service model. |
| SA-3 — Tech Build | Claude Code session | Ready to activate | Stripe/Wise setup, WhatsApp, Calendly, landing page, spreadsheets. |
| SA-4 — Tutor Pipeline | Claude Code session | Ready to activate | Spec, sourcing, screening, agreements. |
| SA-5 — GTM | Claude Code session | Dormant (waits for SA-2) | Outreach, Instagram, content, trial offer. |

### Sequencing for Sep 15 sprint
SA-3 and SA-4 can activate in parallel immediately — payment setup and tutor spec do not wait on research. SA-1 activates for market research P0s (Sep 4 deadline). SA-2 activates after SA-1 delivers Tutoronics intel. SA-5 activates after pricing is set.

### Session workflow
1. State which role you are running as. Default SA-0.
2. Read `DASHBOARD-STATE.md`.
3. Read the charter of the role you are adopting.
4. Do the work. Save outputs under `workstreams/<domain>/`.
5. Update `DASHBOARD-STATE.md`.
6. If a material decision was made: draft `decisions/YYYY-MM-DD-<slug>.md`.
7. Commit.

---

## 8. Repository Structure

```
learners-avenue/
├── CLAUDE.md                    — Claude's rulebook, auto-loaded every session
├── README.md                    — Entry point, structure guide
├── HOW-THIS-WORKS.md            — Plain-English explainer for Minahil
├── PROJECT-BRIEF.md             — This file. Master reference for everything.
├── DASHBOARD-STATE.md           — Current sprint status, active subagents, recent completions
├── ACTIVITY-BACKLOG.md          — All tasks across all domains, P0/P1/P2
├── dashboard/
│   ├── la-os.html               — Full operating system dashboard (visual)
│   └── weekly-reports/          — One file per week, SA-0 writes at session start Sunday+
├── decisions/
│   ├── README.md                — Decision index (newest first)
│   ├── 2026-09-01-subagent-execution-model.md   — APPROVED
│   ├── 2026-09-01-architecture.md               — APPROVED
│   └── 2026-09-01-subagent-taxonomy.md          — APPROVED
├── subagents/
│   ├── SA-0-chief-of-ops/charter.md
│   ├── SA-1-market-research/charter.md
│   ├── SA-2-strategy/charter.md
│   ├── SA-3-tech-build/charter.md
│   ├── SA-4-tutor-pipeline/charter.md
│   └── SA-5-gtm/charter.md
└── workstreams/                 — Output files from each domain (populates as work happens)
```

---

## 9. Key Decisions Log

### Decision: Subagents are roles, not processes (APPROVED 2026-09-01)
Subagents do not run continuously or in parallel. They are roles adopted by sessions. Nothing happens while Minahil is away. Handoff is via committed files only.

**Why:** The alternative (treating subagents as autonomous agents) created a fiction — files described them "working overnight" and "handing off" to each other via mechanisms that do not exist. The honest model is simpler and more reliable.

### Decision: Repo + Markdown as sole source of truth (APPROVED 2026-09-01)
No Notion. No Trello. No Airtable. No parallel state anywhere. Everything lives in this repo. The dashboard is a view of the repo state, not a separate source.

**Why:** Every previous attempt at Learners' Avenue (2023 attempts, 2024 tutor agreements, 2025 marketing planner) had the same failure pattern — activity in spreadsheets and docs that was never connected to actual execution. The repo is the forcing function.

### Decision: Two active subagents at launch; SA-2 through SA-5 dormant (APPROVED 2026-09-01)
Only SA-0 and SA-1 are active on Sep 2. Others activate as the sprint progresses.

**Why:** Writing job descriptions for six roles before knowing what the jobs actually are is backwards. Let the backlog define the roles, not the other way around.

### Decision: Sep 15 as first-booking target (IMPLICIT — not yet filed as a decision file)
The target is not "launch the website" or "have 10 students." It is one confirmed booking from one UAE parent. This is the only signal that the core thesis (someone will pay for this) is true.

**Status:** This should be filed as a decisions file. To do: `decisions/2026-09-02-sep15-milestone.md`.

---

## 10. Resources Inventory

### Archive files (from previous attempts — read and catalogued Sep 2)

| File | Year | What it contains | Usefulness |
|---|---|---|---|
| Student Registration | 2023 | 5 students, Pakistani, Business/Biology/Islamiat | Market profile reference |
| Timetable | 2023 | 8 tutors, Rs. 6000/3 sessions/week | Rate baseline |
| Business Model Analysis | 2023 | TutorBoss YouTube notes, unanswered questions | Reference for failure modes |
| Operations.docx | 2023 | O/A-level Biology, Chemistry, English, Econ, Law, Math, Accounting | Original subject scope |
| Financial Plan | Archive | $25/session, 25% platform cut, 15–30% commission | Pricing baseline |
| Digital Marketing Planner | 2025 | 5-phase campaign Jul–Aug 2025, all statuses = Pending | What not to do |
| Tutor Agreements | May 2024 | 5 signed: Daniyal, Manahil, Shahzaib, Shamoon, Umer Imran | Agreement template source |
| Leadership Workspace | Archive | All department sheets empty — no tasks, no owners, no deadlines | Failure mode evidence |
| Locations doc | Archive | UAE 13, Nigeria 27, South Africa 20 O-level demand points | Market prioritisation |
| Academic Dashboard | Archive | Exam board research by country — UAE uses CAIE + Edexcel IAL confirmed | Tutor spec input |

### Core failure pattern from previous attempts
Every previous attempt built infrastructure before acquiring customers. The Sales and GTM departments were never created — they had zero tasks across all three attempts. The Leadership Workspace had empty sheets for every department. The 2025 marketing planner had every post status as "Pending" with no posts ever made.

**The fix:** Sep 15 target is a booking, not infrastructure. The backlog is organised by what blocks a booking first, not by what is easiest to build.

---

## 11. Content Pipeline (Instagram — Sep 10–12)

Three posts drafted and queued for Minahil's approval. She approves; SA-0 posts.

| ID | Title | Type | Due | Status |
|---|---|---|---|---|
| C1 | Tutor Intro — Business & Economics | Single Image | Sep 10 | Draft |
| C2 | Subject Tip — Economics: PED vs PES | Carousel (3 slides) | Sep 11 | Draft |
| C3 | Founder Story — Why I Started This | Single Image + Caption | Sep 12 | Draft |

Full captions and visual direction are in the operating system dashboard (GTM domain → Content tab).

---

## 12. Operating System Dashboard

The visual dashboard lives at `dashboard/la-os.html` in this repo and is published as a Claude artifact.

**Features:**
- Domain view (sidebar) with task tables, resource panels, content queue, urgency strip
- Stage view showing all 36 tasks grouped P0 / P1 / P2
- Expandable task rows with full detail, blocker field, dependency chips (click to navigate)
- Content approval workflow for Instagram posts
- Status cycling (click any status badge to update)
- Persistent state via localStorage

**GitHub repo:** https://github.com/minahil-ctrl/learners-avenue

---

## 13. What Minahil Reads Every Day

1. **`DASHBOARD-STATE.md`** — 5 minutes. Open decisions at top, active work, blockers.
2. **OS Dashboard** — scan the urgent strip for each domain, check content queue.
3. **`decisions/`** — only when reviewing a specific decision.

Everything else is background infrastructure that SA-0 maintains.

---

## 14. The Rule That Matters Most

> If it is not in a file here, it does not exist.

A great idea in a chat window is gone when the window closes. A committed file is permanent. This is the only rule that prevents the failure mode of every previous attempt.

---

## 15. Appendix: Things That Were Wrong in the Scaffold (Fixed Sep 1)

| Problem | Fix |
|---|---|
| Two rules contradicted each other (execute vs. escalate) | Drew a clear line: structure = execute; judgment = flag |
| Subagents described as processes running continuously | Rewritten as session roles; handoff via committed files only |
| Decision files claimed approval with no record of sign-off | Downgraded to AWAITING RATIFICATION; properly ratified after explicit sign-off |
| SA-0 banned from creating domain content but assigned the backlog | Bounded exception: SA-0 can suggest activities, not set priority |
| Status tags only in the dashboard (parallel state) | Tags moved into each file's header |
| Emoji used as status markers in a file that banned emoji | Replaced with bracketed text — greppable |
| Dashboard restated metrics table word-for-word | Dashboard links to it instead |
| No definition of "material decision" | Defined: >1 hour to reverse, OR downstream subagent builds on it |
| No timezone on any deadline | PKT (UTC+5) set globally |
