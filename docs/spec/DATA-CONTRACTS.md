---
title: DATA-CONTRACTS
owner: team
status: canonical
last_updated: 2026-04-15
source_of_truth: true
---

# Data Contracts

## Purpose

Define the canonical data contracts for the v1 discovery game and the Slate handoff boundary.

## Inputs

- [PLAN/PLAN.md](../../PLAN/PLAN.md)
- [slate/field-dictionary.md](../../slate/field-dictionary.md)

## Outputs

- Game contract models for internal gameplay and results
- Handoff contract models for Slate submission integration
- Required vs optional field definitions and validation expectations

## Constraints

- Keep v1 aligned to one shared flow + college exploration branch.
- Keep PII out of query parameters.
- Keep Slate field semantics consistent with `slate/field-dictionary.md`.

## Examples

- Example contract objects and handoff payloads are provided below under `Example Payloads`.

## Contract Objects

## `Question`

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `id` | string | yes | Stable question identifier |
| `prompt` | string | yes | Student-facing question text |
| `interaction_type` | enum | yes | Interaction mode for response capture |
| `options` | array | yes | Answer options |
| `profile_weights` | object | yes | Weight map from option -> profile scoring |
| `order` | integer | yes | Display order in flow |
| `interest_weights` | object | no | Optional interest scoring support |
| `pillar_tags` | array[string] | no | Strategic messaging tags |
| `confidence_weight` | number | no | Weighting influence for confidence signals |

## `Profile`

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `id` | string | yes | Profile identifier used in results and handoff |
| `label` | string | yes | Human-readable profile label |
| `short_summary` | string | yes | Brief student-facing summary |
| `result_headline` | string | no | Optional headline override |
| `result_body` | string | no | Optional supporting result copy |
| `cta_set_id` | string | no | Optional CTA mapping reference |

## `InterestTag`

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `id` | string | yes | Interest identifier used in results and handoff |
| `label` | string | yes | Human-readable interest label |
| `college_group` | string | yes | College/group classification |
| `description` | string | no | Optional student-facing description |
| `learn_more_url` | string | no | Optional destination URL |

## `ContentMapping`

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `profile_id` | string | yes | Profile foreign key |
| `interest_tag_id` | string | yes | Interest foreign key |
| `message_modules` | array | yes | Content modules for the result state |
| `cta_modules` | array | yes | CTA modules for the result state |
| `audience_variants` | object | no | Optional audience-specific copy variants |

## `GameOutputContract`

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `game_profile` | string | yes | Final profile result ID |
| `game_interest` | string | yes | Final interest result ID |
| `game_version` | string | yes | Contract/game version |
| `game_session_id` | string | yes | Unique game session identifier |
| `game_completed_at` | datetime | yes | ISO-8601 UTC completion timestamp |
| `game_top_signals` | string | no | Optional compact signal list |
| `game_predicted_segment` | enum | no | Optional pre-form segment hint |
| `game_confidence` | enum | no | Optional prediction confidence |

## `LeadPayload` (Conceptual Slate Record)

| Field Group | Fields |
| --- | --- |
| Visible student-entered fields | `first`, `last`, `email`, `school`, `campus`, `contact_type`, `birthdate` |
| Hidden game-derived fields | `game_profile`, `game_interest`, `game_version`, `game_session_id`, `game_completed_at` |
| Optional hidden metadata | `game_top_signals`, `game_predicted_segment`, `game_confidence` |

## Handoff Contract (Game -> Slate)

Required hidden fields at submit:

- `game_profile`
- `game_interest`
- `game_version`
- `game_session_id`
- `game_completed_at`

Optional hidden fields:

- `game_top_signals`
- `game_predicted_segment`
- `game_confidence`

Source of truth for enum/value constraints:

- [slate/field-dictionary.md](../../slate/field-dictionary.md)

## Example Payloads

### Example `GameOutputContract`

```json
{
  "game_profile": "achiever",
  "game_interest": "engineering_technology",
  "game_version": "v1.0.0",
  "game_session_id": "550e8400-e29b-41d4-a716-446655440000",
  "game_completed_at": "2026-04-15T18:24:31Z",
  "game_top_signals": "career_readiness,challenge",
  "game_predicted_segment": "in_state",
  "game_confidence": "medium"
}
```

### Example query parameter handoff (non-PII only)

```text
?game_profile=achiever
&game_interest=engineering_technology
&game_version=v1.0.0
&game_session_id=550e8400-e29b-41d4-a716-446655440000
&game_completed_at=2026-04-15T18%3A24%3A31Z
&game_top_signals=career_readiness%2Cchallenge
&game_predicted_segment=in_state
&game_confidence=medium
```

## Open Questions

- Should `game_version` track the gameplay schema version, content version, or both?
- What are the final canonical `profile` and `interest` ID lists for launch?
- Should `game_top_signals` remain comma-separated text or move to a stricter encoded structure?
