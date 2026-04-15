# Slate Field Dictionary (v1)

This document defines the Slate fields for the student discovery game handoff.

## Visible Student-Entered Fields

| Field | Type | Required | Allowed Values / Format | Example | Notes |
| --- | --- | --- | --- | --- | --- |
| `first` | string | yes | free text | `Jordan` | First name |
| `last` | string | yes | free text | `Lee` | Last name |
| `email` | string (email) | yes | valid email | `jordan@email.com` | Email address |
| `school` | string (or school lookup ID) | yes | school name or configured lookup value | `Skyline High School` | Used to derive in-state vs out-of-state segment |
| `campus` | enum | yes | `asia`, `main`, `online` | `main` | Campus preference |
| `contact_type` | enum | yes | `transfer`, `freshman` | `freshman` | Student type |
| `birthdate` | date | yes | `YYYY-MM-DD` | `2008-04-03` | Used for dedupe support |

## Hidden Game-Derived Fields

| Field | Type | Required | Allowed Values / Format | Example | Notes |
| --- | --- | --- | --- | --- | --- |
| `game_profile` | string | yes | profile ID | `achiever` | Derived from game result |
| `game_interest` | string | yes | interest tag ID | `engineering_technology` | Derived from game result |
| `game_top_signals` | string | no | comma-separated signal IDs | `career_readiness,challenge` | Optional compact signal list |
| `game_version` | string | yes | semantic-like version string | `v1.0.0` | Contract version |
| `game_session_id` | string | yes | UUID or equivalent unique ID | `550e8400-e29b-41d4-a716-446655440000` | Session traceability |
| `game_completed_at` | datetime | yes | ISO-8601 UTC timestamp | `2026-04-15T18:24:31Z` | Completion timestamp |
| `game_predicted_segment` | enum | no | `in_state`, `out_of_state`, `unknown` | `in_state` | Pre-form prediction only |
| `game_confidence` | enum | no | `high`, `medium`, `low` | `medium` | Confidence in predicted segment |

## Query Parameter to Hidden Field Mapping

| Query Parameter | Slate Hidden Field |
| --- | --- |
| `game_profile` | `game_profile` |
| `game_interest` | `game_interest` |
| `game_top_signals` | `game_top_signals` |
| `game_version` | `game_version` |
| `game_session_id` | `game_session_id` |
| `game_completed_at` | `game_completed_at` |
| `game_predicted_segment` | `game_predicted_segment` |
| `game_confidence` | `game_confidence` |

## Validation Rules (Recommended)

- Require visible fields at submit: `first`, `last`, `email`, `school`, `campus`, `contact_type`, `birthdate`.
- Require hidden game fields at submit: `game_profile`, `game_interest`, `game_version`, `game_session_id`, `game_completed_at`.
- Enforce enums exactly as listed for `campus`, `contact_type`, `game_predicted_segment`, and `game_confidence`.
- Keep PII out of query parameters; only pass non-sensitive game-derived metadata in URL params.
