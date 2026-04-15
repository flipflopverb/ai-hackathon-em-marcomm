---
title: WORKFLOW
owner: team
status: canonical
last_updated: 2026-04-15
source_of_truth: true
---

# Team Workflow

## Purpose

Define how the team collaborates in the current project phase, focused on context alignment and asset contribution.

## Inputs

- [docs/team/ONBOARDING.md](ONBOARDING.md)
- [docs/team/DEV-SETUP.md](DEV-SETUP.md)
- [PLAN/PLAN.md](../../PLAN/PLAN.md)
- [CONTEXT.md](../../CONTEXT.md)

## Outputs

- Team-aligned understanding of project scope and goals
- Organized asset and content additions in the repository
- Clear review loop before implementation work begins

## Current Phase Workflow

1. Review context first.
2. Add assets/content to the repo in the correct location.
3. Notify the lead developer of changes for review.
4. Resolve feedback and finalize placement/naming.

## Context Review Workflow

Each team member should review:

1. `README.md`
2. `CONTEXT.md`
3. `PLAN/PLAN.md`
4. `slate/field-dictionary.md` (high level only for non-developer roles)

Goal:

- Everyone can explain what v1 is, what is out of scope, and what the handoff contract means.

## Asset Contribution Workflow

Use these contribution lanes:

- Copywriter: add/edit messaging drafts and copy docs under `docs/` or designated copy files.
- Photographer: add approved photos/source files to the appropriate `SKILLS/.../assets/` pack.
- Graphic designer: add design assets/elements to `SKILLS/.../assets/` with clear naming.
- Developers: organize structure, validate references, and keep canonical docs aligned.

### Asset Placement Rules

- Keep assets under `SKILLS/uofu-enrollment-branding/assets/` unless instructed otherwise.
- Use existing asset packs when possible (`campaign-badge`, `patterns`, `textures`, `typography`, etc.).
- If a new asset type is needed, create a clearly named folder and document it in:
  - `SKILLS/uofu-enrollment-branding/references/asset-library.md`
  - `SKILLS/uofu-enrollment-branding/SKILL.md` (assets section)

### Naming Rules

- Use descriptive, consistent filenames.
- Avoid vague names like `final.png` or `image1.jpg`.
- Include color space or channel markers when relevant (`RGB`, `CMYK`, `print`, `web`).

## Review and Approval Workflow

- Lead developer reviews:
  - file placement
  - naming consistency
  - alignment to scope and brand references
- Changes to canonical files (`PLAN/PLAN.md`, `slate/field-dictionary.md`) require explicit approval before merge.

## Constraints

- Do not introduce PII into query-parameter examples or metadata docs.
- Do not change scope boundaries without approval.
- Do not change required Slate handoff fields without approval.

## Examples

- Photographer adds approved images to the correct asset pack, then lead developer reviews naming and placement before merge.

## Open Questions

- Should we require branch-per-contributor now, or keep direct commits during planning phase?
- Do we want a weekly “asset intake and cleanup” pass led by the design/development pair?
- Should we add role-specific intake folders (`incoming/copy`, `incoming/photo`, `incoming/design`)?
