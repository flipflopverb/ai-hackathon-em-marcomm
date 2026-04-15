---
title: AGENT-RULES
owner: team
status: canonical
last_updated: 2026-04-15
source_of_truth: true
---

# Agent Rules

## Purpose

Define non-negotiable operating rules for agent contributions in this repository.

## Inputs

- [docs/agents/AGENT-START-HERE.md](AGENT-START-HERE.md)
- [PLAN/PLAN.md](../../PLAN/PLAN.md)
- [slate/field-dictionary.md](../../slate/field-dictionary.md)
- [CONTEXT.md](../../CONTEXT.md)

## Outputs

Agent work should produce:

- Changes that remain aligned with canonical scope and field contracts
- Explicit notes when assumptions are made
- Validation evidence for links, paths, and contract safety

## Constraints

## Canonical Source Rules

- Treat `PLAN/PLAN.md` as scope source of truth.
- Treat `slate/field-dictionary.md` as Slate field source of truth.
- Do not redefine canonical objects in secondary docs.
- Link to canonical definitions instead of duplicating them.

## Edit Boundary Rules

Safe without prior approval:

- `docs/**` except files explicitly marked approval-required
- `README.md`
- `CONTEXT.md`
- `SKILLS/**` for skill/documentation/asset organization work

Approval required before editing:

- `PLAN/PLAN.md`
- `slate/field-dictionary.md`
- Any file or change that modifies required handoff fields, enums, or field semantics

## Data and Privacy Rules

- Never place PII in query parameters.
- Keep game-to-Slate handoff payload limited to approved non-PII metadata fields.
- Preserve required hidden fields for submission contracts unless approval is granted.

## Documentation Rules

- Include YAML frontmatter in new docs.
- Prefer structured tables/code blocks for schema-like content.
- Include `Open Questions` in spec/decision docs.
- Add `Last verified` in docs that depend on live integration behavior.

## Change Safety Rules

- Make minimal, reversible edits.
- Do not silently change naming conventions or IDs used by contracts.
- If a planned edit conflicts with canonical docs, stop and request review.

## Examples

Allowed:

- Add `docs/team/QA-CHECKLIST.md` that references canonical handoff fields from `slate/field-dictionary.md`.
- Improve `SKILLS/uofu-enrollment-branding/references/asset-library.md` without changing contract IDs.

Not allowed without approval:

- Renaming `game_profile` to another field name.
- Changing required enum values for `campus` or `contact_type`.
- Expanding v1 scope boundaries in `PLAN/PLAN.md`.

## Open Questions

- Should we enforce these rules with automated checks (docs lint + link checks + contract diff checks)?
- Which future docs should be marked approval-required once `docs/spec/` expands?
