---
title: AGENT-START-HERE
owner: team
status: canonical
last_updated: 2026-04-15
source_of_truth: true
---

# Agent Start Here

## Purpose

Provide the minimum required context for an agent to make safe, high-value changes in this repository.

## Inputs

Read these files in order before editing:

1. [PLAN/PLAN.md](../../PLAN/PLAN.md)
2. [slate/field-dictionary.md](../../slate/field-dictionary.md)
3. [CONTEXT.md](../../CONTEXT.md)
4. [README.md](../../README.md)

If working on brand/copy/design tasks, also read:

5. [SKILLS/uofu-enrollment-branding/SKILL.md](../../SKILLS/uofu-enrollment-branding/SKILL.md)

## Outputs

Every change should produce:

- A clear file-level update aligned to current scope
- Preserved data-contract compatibility with Slate handoff
- A concise summary of what changed and how it was verified

## Constraints

Safe to edit without prior approval:

- `docs/**` (except files marked otherwise later)
- `README.md`
- `CONTEXT.md`
- `SKILLS/uofu-enrollment-branding/**` for skill improvements

Requires explicit human approval before changing:

- `PLAN/PLAN.md` (scope source of truth)
- `slate/field-dictionary.md` (Slate field source of truth)
- Any file that changes required field names, enums, or handoff semantics

Must-not-break rules:

- Do not rename or redefine canonical handoff fields without approval.
- Do not introduce PII into query parameter mappings.
- Do not duplicate canonical definitions across multiple files.

## Validation

Before finalizing:

1. Confirm changed docs still match canonical sources (`PLAN/PLAN.md`, `slate/field-dictionary.md`).
2. Confirm links added/edited resolve to real files.
3. If contracts changed, flag explicitly and request review.

## Examples

Appropriate:

- Add a new docs file under `docs/team/` that references existing canonical scope.
- Improve `SKILLS/uofu-enrollment-branding/references/*` without changing Slate field names.

Not appropriate without approval:

- Changing required hidden fields in the Slate contract.
- Updating scope boundaries in `PLAN/PLAN.md`.

## Open Questions

- Which additional files should be treated as approval-required once `docs/spec/` and ADRs are created?
- Should we formalize a docs lint/check command for link and heading consistency?
