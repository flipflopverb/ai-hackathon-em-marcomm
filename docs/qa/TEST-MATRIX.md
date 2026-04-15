---
title: TEST-MATRIX
owner: team
status: draft
last_updated: 2026-04-15
source_of_truth: false
---

# Test Matrix

## Purpose
Outline key test scenarios for gameplay completion and Slate handoff.

## Inputs
- `../../PLAN/PLAN.md`
- `../spec/DATA-CONTRACTS.md`
- `../../slate/field-dictionary.md`

## Outputs
- Shared test scenario baseline for current and future validation.

## Matrix (Draft)

| Area | Scenario | Expected Result |
| --- | --- | --- |
| Completion | Student completes full flow | `profile` + `academic_interest` produced |
| Handoff | Required hidden fields passed | Slate receives required metadata |
| Privacy | URL inspection | No PII in query params |
| Failure | Abandon mid-flow | Graceful fallback / no bad handoff |

## Constraints
- Keep expected results aligned with canonical scope and field contracts.

## Examples
- Validate that `game_profile` and `game_interest` are present on completed handoff.

## Open Questions
- Which matrix rows should be automated first?
