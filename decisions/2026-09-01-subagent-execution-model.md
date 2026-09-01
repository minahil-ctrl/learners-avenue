# Decision: Subagents are roles, not processes

**Date drafted:** 2026-09-01
**Status:** DRAFT — awaiting Minahil's approval
**Drafted by:** SA-0
**Approved by:** _not yet approved_

## Problem

The scaffold is architected around SA-1 through SA-5 handing work to each other and "inbound" arriving at SA-0 for review. Nothing anywhere defined what a subagent actually *is* operationally. Without that, "SA-0 receives inbound from a subagent" describes a mail room with no mail slot, and the first activation blocks.

## Decision

**A subagent is a role a Claude Code session adopts by loading a charter. It is not a running process, a separate app, or an autonomous actor.**

Concretely:

1. **One session, one role.** A session works as exactly one subagent at a time. It adopts the role by reading that subagent's `charter.md` before doing any work.
2. **SA-0 is the default role.** Any session not explicitly scoped to a domain runs as SA-0.
3. **Handoff is via files and git. Never via message passing.** SA-1 "delivering to SA-2" means SA-1 commits a file to `workstreams/market-research/`, and a later SA-2 session reads it. There is no live channel between subagents and there never will be.
4. **"Inbound" means an uncommitted or newly committed file in a `workstreams/` folder.** SA-0 reviews inbound at the start of its next session, not in real time.
5. **Claude Code's own subagent/Task tool is a worker, not a subagent.** A domain session may fan out parallel workers for search or reading. Those workers have no charter, produce no committed output of their own, and are invisible to this taxonomy. Do not confuse `Task`-spawned workers with SA-1 through SA-5.
6. **Role adoption is explicit and logged.** A session states which role it is running as, and its commits carry that role's prefix. A session may switch roles, but must say so and commit the prior role's work first.

## Alternatives considered

1. **True concurrent multi-agent via the Task tool** — rejected. Spawned agents start cold, do not persist across sessions, cannot reliably hold a charter's judgment standards, and each one that commits creates an audit trail nobody reviewed. The cost is real and the benefit here is near zero: this is a documentation repo, not a codebase with parallelizable builds.
2. **One Claude app project per subagent** — rejected. Creates five parallel states outside the repo. Directly violates the source-of-truth rule that `decisions/2026-09-01-architecture.md` was written to protect.
3. **Subagents as pure folder convention, no role adoption** — rejected as insufficient. It is what the scaffold implicitly does today, and it is why the charters read as fiction. If nothing adopts the charter, the charter constrains nothing.
4. **A scheduled/cron SA-0 that runs daily** — deferred, not rejected. Technically possible. Premature: there is no inbound volume to justify it, and it would produce dashboard churn with no reader.

## Consequences

- **The charters' "daily operations" language is fiction and has been rewritten.** SA-0 does not run on a clock. It runs when a session opens. Any metric with a wall-clock denominator (the 48-hour rule) is measured at session start, not continuously.
- **Sequencing is enforced by humans, not by the system.** Nothing mechanically prevents an SA-3 session from starting before SA-2's output is approved. The charter's "no subagent starts work whose inputs aren't approved" is a rule Minahil and the session must honour, not a gate.
- **Parallel work is possible but manual** — two terminals, two roles, two sets of commits. Collision risk is on the operator, not the architecture.
- **A charter is only as good as the session that reads it.** Step 2 of the session workflow in `CLAUDE.md` is load-bearing. Skipping it silently degrades the whole system.

## Revisit if

- Inbound volume grows past what one SA-0 session per day can review.
- A domain genuinely needs concurrent execution (most likely SA-3, once there is real code).
- Someone other than Minahil joins and roles need to map to people.
