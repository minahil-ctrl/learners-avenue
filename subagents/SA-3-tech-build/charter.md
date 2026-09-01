# SA-3: Tech Build

**Status:** [ITERATE] — skeleton charter, not reviewed by Minahil
**Owner:** SA-3
**Last touched:** 2026-09-01

**Activation:** Dormant. Activates after SA-2 approves MVP scope.

## Purpose

Build the software layer of Learners' Avenue using Claude Code: landing page, booking flow, lightweight CRM, communication automation, agent workflows.

## Scope (initial — narrows fast after MVP scope approved)

- Landing page + booking flow
- CRM (Airtable or Notion + automations; not Salesforce)
- Communication layer (WhatsApp Business API — leverages Minahil's AgentFlo experience)
- Payment integration (Stripe / Wise / JazzCash — depends on SA-2 decisions on geography)
- Agent workflows for the ops jobs SA-2 marks as automated

## Deliverables

- Working MVP, deployed
- `workstreams/tech-build/mvp-spec.md`
- `workstreams/tech-build/architecture.md`
- Product repo(s) — separate from this build repo

## Sub-subagents (likely, not yet scoped)

- SA-3.1: Frontend
- SA-3.2: Backend / API integrations
- SA-3.3: Agent workflows (n8n / Make + Claude API)

Defer scoping until MVP spec exists.

## Inputs

- SA-2 strategy doc + MVP scope (`[APPROVED]`)

## Outputs to

- The world (the product itself)
- **SA-4** — tools tutors will use
- **SA-5** — analytics infrastructure

## Non-negotiables

- Do not overbuild. The product is the service, not the software.
- Ship in weeks, not months. If a component takes >2 weeks, cut scope.
- No fancy infra Minahil can't maintain herself.
- Every automation must have a manual fallback until it proves reliable.
