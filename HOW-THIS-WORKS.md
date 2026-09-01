# How This Works — plain English

**Status:** [ITERATE]
**Owner:** SA-0
**Last touched:** 2026-09-01

For Minahil. No jargon. If a word needs explaining, it gets explained the first time it appears.

---

## 1. The one-sentence version

This is a **filing cabinet that remembers every version of everything you ever put in it**, and Claude reads from it and writes to it instead of keeping things in its head.

That's it. Everything below is detail.

---

## 2. Why a filing cabinet at all

Claude forgets. Every new conversation starts from zero.

So instead of you re-explaining the business every time, the explanation lives in files. Claude reads the files at the start of each session and picks up where it left off. The files are the memory.

**The consequence you need to internalise:** if something isn't written in a file here, it doesn't exist. A great idea in a chat window is gone when the window closes.

---

## 3. The words you'll keep seeing

You don't need to know how any of this works internally. You need to know what it *does*.

| Word | What it actually means |
|---|---|
| **Repo** (repository) | The folder. This whole thing. "The repo" = "all our files." |
| **Git** | The tool that saves a snapshot every time we change something. It never overwrites — it stacks. |
| **Commit** | One saved snapshot, with a note saying what changed. Like hitting Save, but the old version stays forever. |
| **Push** | Copying our snapshots up to GitHub, so they exist somewhere other than your laptop. |
| **GitHub** | The website that stores the copy. Private = only you can see it. |
| **Remote** | The address of that GitHub copy. Set once, never thought about again. |
| **Main** | The one official version of the files. We only use this one. There are no others. |
| **Markdown** | Plain text with light formatting. `**bold**` makes bold. That's the whole language. |
| **Diff** | The difference between two snapshots. "What changed since last time." |

**Why any of this matters to you:** because it means you can never lose work, and you can always see who changed what and when. That's the entire value proposition. Nothing else about git is your problem.

---

## 4. What's in the folder, file by file

### The four you'll actually open

| File | What it's for | How often you look at it |
|---|---|---|
| `DASHBOARD-STATE.md` | Where everything stands right now. Open decisions at the top. | Daily, 5 minutes |
| `ACTIVITY-BACKLOG.md` | The master list of every job the business needs done. Currently empty. | When we're planning |
| `HOW-THIS-WORKS.md` | This file. | When something confuses you |
| `decisions/` | Every significant choice, why we made it, what we rejected. | When you're second-guessing something |

### The ones that run in the background

| File / Folder | What it's for |
|---|---|
| `CLAUDE.md` | Claude's rulebook. Loads automatically every session. You don't read it; Claude obeys it. |
| `README.md` | The front page. Explains the structure to anyone new. |
| `subagents/` | Job descriptions. One folder per role. |
| `workstreams/` | Where the actual work output lands, sorted by topic. Currently empty. |
| `dashboard/weekly-reports/` | One summary per week. |
| `.gitignore` | A list of things git should never save — passwords, keys, private data. Safety net. |

---

## 5. The subagent thing, honestly

You'll see `SA-0`, `SA-1`, up to `SA-5`. Here's what they really are.

**They are not robots working in parallel.** Nobody is off doing market research while you sleep. There is no team.

**They are hats.** Each one is a written job description — priorities, rules, what it's allowed to decide, what it must escalate. When a session starts, Claude reads one job description and works as that role. One hat at a time.

| Role | Job | Status right now |
|---|---|---|
| **SA-0** — Chief of Ops | Keeps files organised, keeps the dashboard honest, brings you decisions. **Never decides anything itself.** | Active. This is me. |
| **SA-1** — Market Research | Finds evidence: competitors, demand, what people pay. | Asleep |
| **SA-2** — Strategy | Turns that evidence into decisions: which niche, what pricing, what the business model is. | Asleep |
| **SA-3** — Tech Build | Builds the website, booking system, automation. | Asleep |
| **SA-4** — Tutor Pipeline | Finds, screens and onboards tutors. | Asleep |
| **SA-5** — GTM (go-to-market) | Branding, content, getting the first clients. | Asleep |

**How they hand work to each other:** they don't talk. SA-1 finishes research and saves a file. Later, a session wearing the SA-2 hat opens that file. The handoff is the file. That's the only channel.

**Why split it up at all?** So the rules stay separate. The research role is required to cite a source for every claim. The strategy role is required to argue hard. The ops role is forbidden from having opinions. Mixing those in one prompt produces mush.

**My honest reservation, on record:** five of six roles are asleep, and their job descriptions were written *before* the backlog that's supposed to define them. That's backwards. I think we should have started with two. It's your call, and it's sitting in your decision queue.

---

## 6. Status tags — the traffic light

Every file has a tag at the top saying how finished it is. Six tags:

| Tag | Means | Who can set it |
|---|---|---|
| `[ITERATE]` | Done, but you haven't seen it. **Everything starts here.** | Claude |
| `[APPROVED]` | You've read it and signed off. | **You only** |
| `[REJECT]` | You've read it and it's wrong. Redo. | **You only** |
| `[FLAG]` | I have a concern. Read this one. | Me |
| `[WAITING]` | Blocked, waiting on something upstream. | Me |
| `[NOTE]` | Approved, but with a note to revisit later. | **You only** |

**The rule that matters most:** *saving a file is not the same as approving it.* Anything untagged is `[ITERATE]` by default. I can never mark something approved. Only you can.

This is the guardrail against the most likely failure mode of this whole setup — Claude writing something confident and plausible, it sitting in a file for three weeks, and everyone downstream treating it as settled fact when nobody ever checked it.

---

## 7. What a normal session looks like

1. You open Claude Code in this folder.
2. Claude reads its rulebook and the dashboard automatically.
3. Claude says which hat it's wearing.
4. You give it work.
5. It saves output into the right folder, tagged `[ITERATE]`.
6. It updates the dashboard.
7. It commits — takes a snapshot with a note.
8. Next session, it reads the dashboard and knows exactly where things stood.

Step 7 is the one that makes step 8 possible. A session that doesn't commit effectively didn't happen.

---

## 8. The rules, and the reason behind each

The rules aren't bureaucracy. Each one exists to stop a specific failure.

| Rule | The failure it prevents |
|---|---|
| The repo is the only source of truth | Two places holding "the plan," slowly disagreeing, and nobody noticing which is current |
| Only you can approve | Claude's guesses hardening into facts because nobody flagged them |
| Never copy text between files | You update one, forget the other, and now they contradict each other |
| Every decision gets logged with alternatives | In six weeks you won't remember *why* you rejected the other option, and you'll re-litigate it |
| Never claim a source that doesn't exist | Reasoning that can't be checked is reasoning that can't be trusted |
| Escalate, don't fix | If I quietly patch a broken job description, the job description stays broken |
| Cite every factual claim | Confident, well-written, entirely made-up numbers are the number one risk with this technology |

---

## 9. What I changed today, in plain terms

I audited the starting files and found genuine problems. Here's each one without the jargon.

| # | What was wrong | Why it mattered | What I did |
|---|---|---|---|
| 1 | **Two rules contradicted each other.** One said "just execute, don't ask." Another said "never guess, always flag." | Claude would follow whichever suited it. In practice the "just execute" one wins, and guesses slip through. | Drew a clear line: formatting and structure — just do it. Anything involving judgment, a number, or a priority — stop and ask. |
| 2 | **Nobody had defined what a subagent actually is.** The files described them handing work to each other, with no mechanism for that. | The whole design rested on something that didn't exist. It would have broken the moment we activated the first one. | Wrote it down properly: they're roles, handoff is via files. Filed as a draft decision for you to approve. |
| 3 | **Two decision files claimed you had approved them.** No record of when or how. | That's a fake signature in the permanent record, on day one, in a system whose main rule is "nothing is approved without her sign-off." | Changed both to "awaiting your confirmation" and left a note explaining why. **You need to tell me if you actually approved these.** |
| 4 | **The files described me as working every morning and evening.** | I don't run on a schedule. I exist when you open the app. Any promise about daily updates was fiction. | Rewrote it as "start of session / end of session." Honest about what I can actually do. |
| 5 | **I was banned from writing domain content, but also assigned the backlog** — which spans every domain. | The very next task you asked for was blocked by a rule contradiction. | Gave myself a narrow exception: I can *suggest* activities, but I can't set priority or assign owners. Those stay blank for you. |
| 6 | **Status tags lived only in the dashboard, not in the files.** | The dashboard becomes a second source of truth about file state — the exact drift the whole system is designed to prevent. | Moved the tag into each file's header. Dashboard now just points at them. |
| 7 | **Emoji were used as status markers**, in a file that says "no emoji." | Beyond the contradiction — you can't reliably search for an emoji. You can search for `[FLAG]` and instantly see every open concern. | Swapped to bracketed text. Searchable. |
| 8 | **The dashboard restated the weekly metrics table word for word.** | Two copies of the same table = guaranteed to disagree eventually. | Dashboard now links to it instead. |
| 9 | **"Log every material decision" with no definition of "material."** | Either we log everything (useless) or nothing (useless). | Defined it: over an hour to undo, **or** something else gets built on top of it. Otherwise it's just work — don't log it. |
| 10 | **A decision file cited a planning document that isn't in this folder.** | Reasoning you can't verify. | Flagged it. **Do you still have that document?** |
| 11 | **No timezone anywhere**, but a "48-hour" rule. | 48 hours from when? Unmeasurable. | Set everything to PKT. |
| 12 | **No index of decisions**, and SA-0's file was shaped differently from every other role's. | Small now. Annoying at thirty files. | Added an index. Made the folder structure consistent. |

---

## 10. The two things I still think are wrong

I fixed what I could fix. These two need you.

**The 48-hour response rule doesn't work.** It promises that nothing waits more than two days for your decision. But I can't check anything while you're away — I only exist when you open the app. If you don't open it for four days, something waits four days and nothing catches it. Right now that rule is decoration. Either we drop it, or we set up a genuine scheduled reminder. I'd rather drop it than keep a metric that reports a comforting number.

**Six roles is probably too many for a pre-launch business run by one person.** Five are asleep, and their job descriptions were written before we knew what the work actually is. When the backlog is populated, we'll almost certainly rewrite them. That's work we're choosing to redo. I'd start with two — ops and research — and let the rest emerge from evidence. Your call entirely.

---

## 11. What's waiting on you right now

Full list is at the top of `DASHBOARD-STATE.md`. The three that block everything else:

1. **Approve or reject the subagent execution model** (the "roles, not robots" decision). Nothing downstream is safe until this is settled.
2. **Did you actually approve the architecture and taxonomy decisions?** If yes, I restore the sign-off. If no, we review them properly.
3. **The "pre-scaffold plan, steps 1–10"** — do you have it? If it exists, it goes in the folder. If not, the reasoning that cites it comes out.

---

## 12. Things you can safely ignore forever

- Anything git prints in red that isn't the word `error`
- `.gitignore`, once it's set up
- The `dashboard/` folder until we've been running a week
- Any suggestion to add tools, dashboards, or integrations before the backlog exists

---

## 13. If you only remember four things

1. **If it's not in a file here, it doesn't exist.**
2. **`[ITERATE]` means nobody checked it. Only you can make it `[APPROVED]`.**
3. **Subagents are hats, not robots. Nothing happens while you're away.**
4. **When I flag something, it's because I'd rather be annoying than wrong.**
