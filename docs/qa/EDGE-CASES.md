---
title: EDGE-CASES
owner: team
status: draft
last_updated: 2026-04-17
source_of_truth: false
---

# Edge Cases

## Purpose
Track known edge cases that could break gameplay flow or handoff integrity.

## Inputs
- `TEST-MATRIX.md`
- `../spec/STATE-MACHINE.md`

## Outputs
- Prioritized edge-case list for validation and mitigation planning.

## Cases

- Page refresh during an active landmark interaction
- Page refresh after result resolution but before Slate handoff
- Session reaches results without enough valid trigger completions
- Missing or failed map, tileset, or sprite asset under the GitHub Pages base path
- Invalid or missing `game_academic_interest` during payload creation
- Player exits the Slate handoff and returns to results
- Mobile orientation change during map exploration
- Unsupported or older browser behavior

## Constraints
- Keep edge-case definitions tied to current v1 scope.

## Examples
- If `game_completed_at` is missing, the handoff payload should not be treated as valid.

## Open Questions
- Which of these edge cases are highest risk for the first deployed demo?
