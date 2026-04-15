---
title: HIDDEN-FIELD-MAPPING
owner: team
status: draft
last_updated: 2026-04-15
source_of_truth: false
---

# Slate Hidden Field Mapping (Draft)

## Purpose
Provide a compact mapping reference for game metadata -> Slate hidden fields.

## Inputs
- `field-dictionary.md`
- `../docs/spec/DATA-CONTRACTS.md`

## Outputs
- Quick mapping table for hidden-field handoff implementation.

## Mapping

| Game Output Key | Slate Hidden Field | Required |
| --- | --- | --- |
| `game_profile` | `game_profile` | yes |
| `game_interest` | `game_interest` | yes |
| `game_version` | `game_version` | yes |
| `game_session_id` | `game_session_id` | yes |
| `game_completed_at` | `game_completed_at` | yes |
| `game_top_signals` | `game_top_signals` | no |
| `game_predicted_segment` | `game_predicted_segment` | no |
| `game_confidence` | `game_confidence` | no |

## Notes

- Canonical enum/value constraints remain in `slate/field-dictionary.md`.
- Keep PII out of URL/query mappings.

## Constraints
- Must remain consistent with `slate/field-dictionary.md` canonical definitions.

## Examples
- `game_profile=achiever` maps to Slate hidden field `game_profile`.

## Open Questions
- Should this file remain a quick reference or be merged into `field-dictionary.md` later?
