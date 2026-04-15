---
title: QA-CHECKLIST
owner: team
status: canonical
last_updated: 2026-04-15
source_of_truth: true
---

# QA Checklist

## Purpose

Provide a lightweight quality checklist for the current planning and asset-ingestion phase.

## Inputs

- [PLAN/PLAN.md](../../PLAN/PLAN.md)
- [slate/field-dictionary.md](../../slate/field-dictionary.md)
- [docs/team/WORKFLOW.md](WORKFLOW.md)
- [SKILLS/uofu-enrollment-branding/references/asset-library.md](../../SKILLS/uofu-enrollment-branding/references/asset-library.md)

## Outputs

- Fewer scope/contract regressions
- Cleaner asset organization
- Better readiness for implementation kickoff

## Constraints

- Keep checks aligned to current planning/assets phase.
- Do not treat this checklist as a replacement for canonical scope/contract docs.

## Scope and Contract Checks

- [ ] Changes remain within current v1 scope boundaries.
- [ ] No non-goal features were introduced by implication.
- [ ] Required handoff fields remain unchanged:
  - `game_profile`
  - `game_interest`
  - `game_version`
  - `game_session_id`
  - `game_completed_at`
- [ ] No new PII appears in query parameter examples.

## Documentation Checks

- [ ] New docs include frontmatter (`title`, `owner`, `status`, `last_updated`, `source_of_truth`).
- [ ] Links point to valid files.
- [ ] Canonical values are referenced, not duplicated inconsistently.
- [ ] `Open Questions` section exists where appropriate (spec/decision/process docs).

## Asset Checks

- [ ] New assets are placed in the correct pack under `SKILLS/uofu-enrollment-branding/assets/`.
- [ ] Filenames are descriptive and consistent.
- [ ] Duplicate/temporary names (`final-final`, `image1`, etc.) are removed.
- [ ] Added asset packs are documented in:
  - `SKILLS/uofu-enrollment-branding/references/asset-library.md`
  - `SKILLS/uofu-enrollment-branding/SKILL.md` (assets section)
- [ ] File formats match intended use (vector for editable/scalable outputs, PNG/JPG for quick placement as appropriate).

## Team Review Checks

- [ ] Lead developer reviewed canonical-sensitive changes.
- [ ] Copywriter/designer/photographer contributions are traceable to repo paths.
- [ ] Any unresolved decision is logged in `Open Questions` (not hidden in chat).

## Examples

- After asset intake, run this checklist before asking lead developer for final review.

## Readiness Signal (Current Phase)

Ready to move from planning/assets phase toward implementation planning when:

- [ ] Scope docs are stable for one review cycle.
- [ ] Slate field dictionary is stable for one review cycle.
- [ ] Asset library structure is stable and documented.
- [ ] No high-severity open contract questions remain.

## Open Questions

- Should this checklist split into phase-specific versions later (planning vs implementation vs launch)?
- Which checks should become automated first (link validation, missing file references, naming rules)?
