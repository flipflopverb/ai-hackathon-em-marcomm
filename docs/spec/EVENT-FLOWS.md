---
title: EVENT-FLOWS
owner: team
status: draft
last_updated: 2026-04-15
source_of_truth: false
---

# Event Flows

## Purpose
Define key event sequences from entry to Slate handoff.

## Inputs
- `PLAN/PLAN.md`
- `DATA-CONTRACTS.md`
- `../../slate/field-dictionary.md`

## Outputs
- Event flow definitions for gameplay and submission events.

## Constraints
- Keep naming consistent with contract fields.

## Examples
- `game_started` -> `question_answered` (repeat) -> `game_completed` -> `slate_handoff_started` -> `slate_handoff_submitted`

## Open Questions
- Which analytics event names should be canonicalized first?
