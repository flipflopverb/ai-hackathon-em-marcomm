---
title: ONBOARDING
owner: team
status: canonical
last_updated: 2026-04-15
source_of_truth: true
---

# Team Onboarding

## Purpose

Provide a quick team-level understanding of project scope, goals, and current boundaries.

## What “Canonical” vs “Supporting” Means

- **Canonical files**: final source of truth for a topic. If there is conflict, these win.
- **Supporting files**: helpful guidance/organization docs that should align to canonical files.

Current canonical files:

- [PLAN/PLAN.md](../../PLAN/PLAN.md) for scope and v1 boundaries
- [slate/field-dictionary.md](../../slate/field-dictionary.md) for Slate field contract

## Outputs

After onboarding, a contributor should be able to:

- Explain v1 scope and non-goals
- Describe the game -> Slate handoff contract
- Explain what phase the project is currently in

## Inputs

- [README.md](../../README.md)
- [CONTEXT.md](../../CONTEXT.md)
- [PLAN/PLAN.md](../../PLAN/PLAN.md)
- [slate/field-dictionary.md](../../slate/field-dictionary.md)

## Read First

1. [README.md](../../README.md)
2. [CONTEXT.md](../../CONTEXT.md)
3. [PLAN/PLAN.md](../../PLAN/PLAN.md)
4. [slate/field-dictionary.md](../../slate/field-dictionary.md)
5. [docs/team/DEV-SETUP.md](DEV-SETUP.md)

## Current Project Focus

At this point, the team should focus on:

- Locking scope and non-goals
- Locking game output and Slate handoff contract
- Aligning around what is explicitly out of scope for v1

There is no formal implementation task list in `docs/` yet; that can be added once planning artifacts are finalized.

## Scope Snapshot

- Product goal: 2-5 minute branded discovery game
- Required outcomes: `profile`, `academic_interest`
- Handoff: embedded Slate RFI with required hidden game metadata
- Current phase: planning/contracts (Phase 0)

## Constraints

- Do not change v1 scope boundaries without team approval.
- Do not change required Slate field definitions without team approval.
- Keep PII out of query parameter examples and contracts.

## Examples

- New teammate can describe v1 in one sentence and identify canonical files without looking at chat history.

## Open Questions

- When should we create the team task backlog file (for example `docs/team/WORKFLOW.md` or `docs/team/TASKS.md`)?
- What milestone definitions should be locked first for implementation kickoff?
