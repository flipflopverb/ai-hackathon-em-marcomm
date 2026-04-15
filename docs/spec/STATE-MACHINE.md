---
title: STATE-MACHINE
owner: team
status: draft
last_updated: 2026-04-15
source_of_truth: false
---

# State Machine

## Purpose
Describe game states and transitions at a high level.

## Inputs
- `PLAN/PLAN.md`
- `DATA-CONTRACTS.md`
- `EVENT-FLOWS.md`

## Outputs
- Draft state map for implementation planning.

## Constraints
- Keep state names aligned to user journey.

## Examples
- `ENTRY` -> `IN_GAME` -> `RESULTS` -> `SLATE_HANDOFF` -> `SUBMITTED`

## Open Questions
- What are terminal and recovery states for abandoned sessions?
