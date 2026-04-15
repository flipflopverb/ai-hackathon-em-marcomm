---
title: ADR-0003-SLATE-HANDOFF
owner: team
status: draft
last_updated: 2026-04-15
source_of_truth: false
---

# ADR-0003: Slate Handoff Boundary

## Purpose
Capture final decision rationale for where game scope ends and Slate responsibility begins.

## Inputs
- `PLAN/PLAN.md`
- `slate/field-dictionary.md`
- `docs/spec/DATA-CONTRACTS.md`

## Outputs
- Durable decision record on integration boundary and ownership.

## Constraints
- Must preserve required hidden-field contract.

## Examples
- Keep required hidden fields fixed while allowing optional metadata additions.

## Open Questions
- Which optional metadata fields are mandatory for launch analytics?
