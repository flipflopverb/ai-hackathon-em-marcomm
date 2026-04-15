# Branded Student Discovery Game for University Marketing

## 1) Product Goal and v1 Scope

Build a 2-5 minute branded discovery game that feels like a campus/city/student-life tour, not a form.

The game must produce two outcomes:
- `profile` (motivation type)
- `academic_interest` (college/field interest)

v1 uses one shared game flow with a college exploration branch:
- Tour choices across campus-life themes drive `profile`
- College branch selection sets `academic_interest`

After results, hand off to embedded Slate RFI and collect: `first`, `last`, `email`, `school`, `campus`, `contact_type`, `birthdate`.

Pass game metadata to Slate hidden fields via query parameters. Do not build separate in-state/out-of-state game versions in v1.

## 2) Non-Goals and v1 Boundaries

- Two separate game experiences for in-state and out-of-state audiences.
- Deep adaptive branching that rewrites the whole journey from early answers.
- Full custom content for every profile x interest combination.
- In-game contact form collection.
- PII in query parameters.
- Full program-level college depth at launch.
- Downstream CRM automation/routing implementation.

## 3) Canonical User Journey

- Student enters from campaign/site source.
- Student completes a unified campus/city/student-life tour (5-7 decisions).
- Student selects a college exploration branch to set `academic_interest`.
- Game computes and displays `profile + academic_interest`.
- Student proceeds to embedded Slate RFI form.
- Game passes non-PII metadata to Slate hidden fields.

## 4) Data Contracts

Define these objects before implementation to keep gameplay, personalization, and handoff aligned.

- `Question`
  - Required: `id`, `prompt`, `interaction_type`, `options[]`, `profile_weights`, `order`
  - Optional: `interest_weights`, `pillar_tags`, `confidence_weight`
- `Profile`
  - Required: `id`, `label`, `short_summary`
  - Optional: `result_headline`, `result_body`, `cta_set_id`
- `InterestTag`
  - Required: `id`, `label`, `college_group`
  - Optional: `description`, `learn_more_url`
- `ContentMapping`
  - Required: `profile_id`, `interest_tag_id`, `message_modules[]`, `cta_modules[]`
  - Optional: audience-specific copy variants
- `GameOutputContract`
  - Required: `game_profile`, `game_interest`, `game_version`, `game_session_id`, `game_completed_at`
  - Optional: `game_top_signals`, `game_predicted_segment`, `game_confidence`
- `LeadPayload` (conceptual final Slate record)
  - Required visible fields: `first`, `last`, `email`, `school`, `campus`, `contact_type`, `birthdate`
  - Required hidden fields: `game_profile`, `game_interest`, `game_version`, `game_session_id`, `game_completed_at`

## 5) CRM Handoff Boundary (Slate)

- The game scope ends at Slate RFI submission.
- Required hidden fields from game: `game_profile`, `game_interest`.
- Optional hidden metadata: `game_version`, `game_session_id`, `game_completed_at`, `game_top_signals`.
- Segmentation, routing, and downstream enrollment logic are owned by Slate/CRM (out of scope here).

## 6) Personalization Rules (In-Product Only)

- Personalization is limited to result presentation and handoff metadata.
- The game must compute and display `profile` and `academic_interest`.
- Results use predefined mapping keyed by `profile + academic_interest`.
- Keep modules concise: headline, short copy, and next-step CTA.
- No CRM routing or downstream communication logic in-game.

## 7) Slate Integration Contract

- Final step is embedded Slate RFI form submission.
- Required hidden fields: `game_profile`, `game_interest`.
- Optional hidden metadata: `game_version`, `game_session_id`, `game_completed_at`, `game_top_signals`.
- Student-entered Slate fields: `first`, `last`, `email`, `school`, `campus`, `contact_type`, `birthdate`.
- Field definitions and enums live in `slate/field-dictionary.md`.

## 8) Measurement and QA (Game + Handoff Only)

- Median completion time is 2-5 minutes on mobile.
- Every completed run outputs `profile` and `academic_interest`.
- Required hidden handoff fields reach Slate correctly.
- Optional metadata fields pass when available.
- No PII appears in query parameters.
- Incomplete/abandoned sessions fail gracefully.
- Accessibility baseline passes: keyboard navigation, contrast, reduced motion support, touch target usability.

## 9) Delivery Phase (Current)

Only Phase 0 is in scope.

- **Phase 0: Planning and Contracts**
  - Finalize this plan structure and scope.
  - Finalize data contracts for gameplay and handoff.
  - Finalize Slate field dictionary and hidden-field mapping in `slate/field-dictionary.md`.

Phases for implementation, personalization expansion, and launch execution are intentionally deferred.
