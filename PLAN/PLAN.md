# Branded Student Discovery Game for University Marketing

## 1) Product Goal and v1 Scope

Build a 2-5 minute branded discovery game that feels like a campus/city/student-life tour, not a form.

The game must produce two outcomes:
- `profile` (motivation type)
- `academic_interest` (college/field interest)

v1 uses one shared game flow with a college exploration branch:
- Tour choices across campus-life themes drive `profile`
- College branch selection sets `academic_interest`

After results, the experience hands off to an embedded Slate RFI that collects `first`, `last`, `email`, `school`, `campus`, `contact_type`, and `birthdate`. The game passes non-PII metadata to Slate hidden fields via query parameters.

Do not build separate in-state/out-of-state game versions in v1.

## 2) Experience Definition

The intended experience is a guided University of Utah discovery tour for prospective students.

- The player is framed as `Swoop`, moving through a stylized topographical map of campus and the surrounding area.
- The experience should feel like exploring the university, not filling out a survey.
- Tour moments should blend student life, academics, place, and future opportunities into one cohesive journey.
- Questions should help students reflect on what fits them while also signaling likely motivation patterns and academic interests.
- The result should help the student better understand their fit with the University of Utah and point them to the next step through the Slate RFI.

This plan defines the product shape, scope, and handoff boundary. Exact question copy, profile taxonomy, and virtual tour design details can be finalized later by the team.

## 3) Non-Goals and v1 Boundaries

- Two separate game experiences for in-state and out-of-state audiences.
- Deep adaptive branching that rewrites the whole journey from early answers.
- Full custom content for every profile x interest combination.
- In-game contact form collection.
- PII in query parameters.
- Full program-level college depth at launch.
- Downstream CRM automation/routing implementation.

## 4) Canonical User Journey

- Student enters from campaign/site source.
- Student begins a guided exploration as `Swoop` on a stylized campus/area map.
- Student completes a unified campus/city/student-life tour (5-7 decisions).
- Student selects a college exploration branch to set `academic_interest`.
- Game computes and displays `profile + academic_interest`.
- Student proceeds to embedded Slate RFI form.
- Game passes non-PII metadata to Slate hidden fields.

## 5) Experience Structure (v1)

The tour should be structured around a small set of place-based or theme-based stops so the game reads as an exploratory journey instead of a sequence of disconnected prompts.

Recommended v1 tour pillars:
- Student life and community
- Academics and learning environment
- Belonging, identity, and support
- Opportunities, ambition, and career direction
- Campus and city context

Implementation notes for v1:
- Use 5-7 decisions total to preserve the 2-5 minute completion target.
- Each stop should contribute to `profile`; the college exploration branch sets `academic_interest`.
- Result content should explain both what kind of student the player seems to be and what academic area they may want to explore next.

## 6) Data and Result Contracts

Define these objects before implementation to keep gameplay, personalization, and handoff aligned. Field-level definitions live in `docs/spec/DATA-CONTRACTS.md`.

- `Question`
  - Drives player decisions and scoring.
- `Profile`
  - Defines the motivation-type outcome shown at results.
- `InterestTag`
  - Defines the college or field-interest outcome.
- `ContentMapping`
  - Maps `profile + academic_interest` to result content and calls to action.
- `GameOutputContract`
  - Carries the non-PII game metadata passed into Slate.
- `LeadPayload` (conceptual final Slate record)
  - Combines student-entered visible fields and hidden game-derived fields.

## 7) Slate Handoff Boundary

- The game scope ends at Slate RFI submission.
- Final step is embedded Slate RFI form submission.
- Required hidden fields at submit: `game_profile`, `game_interest`, `game_version`, `game_session_id`, `game_completed_at`.
- Optional hidden metadata: `game_top_signals`, `game_predicted_segment`, `game_confidence`.
- Student-entered Slate fields: `first`, `last`, `email`, `school`, `campus`, `contact_type`, `birthdate`.
- Field definitions and enums live in `slate/field-dictionary.md`.
- Segmentation, routing, and downstream enrollment logic are owned by Slate/CRM (out of scope here).

## 8) Personalization Rules (In-Product Only)

- Personalization is limited to result presentation and handoff metadata.
- The game must compute and display `profile` and `academic_interest`.
- Results use predefined mapping keyed by `profile + academic_interest`.
- Keep modules concise: headline, short copy, fit explanation, and next-step CTA.
- No CRM routing or downstream communication logic in-game.

## 9) Measurement and QA (Game + Handoff Only)

- Median completion time is 2-5 minutes on mobile.
- Every completed run outputs `profile` and `academic_interest`.
- Required hidden handoff fields reach Slate correctly: `game_profile`, `game_interest`, `game_version`, `game_session_id`, `game_completed_at`.
- Optional metadata fields pass when available.
- No PII appears in query parameters.
- Incomplete/abandoned sessions fail gracefully.
- Accessibility baseline passes: keyboard navigation, contrast, reduced motion support, touch target usability.

## 10) Delivery Phase (Current)

Only Phase 0 is in scope.

- **Phase 0: Planning and Contracts**
  - Finalize this plan structure and scope.
  - Finalize data contracts for gameplay and handoff.
  - Finalize Slate field dictionary and hidden-field mapping in `slate/field-dictionary.md`.

Phases for implementation, personalization expansion, and launch execution are intentionally deferred.
