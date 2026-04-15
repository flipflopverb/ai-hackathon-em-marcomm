---
title: HANDOFF
owner: team
status: canonical
last_updated: 2026-04-15
source_of_truth: true
---

# Team Handoff

## Purpose

Define what must be true before handing off work between contributors and before moving from planning/assets phase to implementation planning.

## Inputs

- [docs/team/WORKFLOW.md](WORKFLOW.md)
- [docs/team/QA-CHECKLIST.md](QA-CHECKLIST.md)
- [PLAN/PLAN.md](../../PLAN/PLAN.md)
- [slate/field-dictionary.md](../../slate/field-dictionary.md)

## Outputs

- Consistent and reviewable handoff packets
- Fewer misunderstandings between team roles
- Clear phase-transition readiness signals

## Handoff Packet (Required)

Each handoff should include:

1. **What changed**
   - File paths changed
   - Brief summary of additions/updates

2. **Why it changed**
   - Scope/goal tie-back
   - Related context or requirement

3. **What to review**
   - Priority review points for the next person
   - Any sensitive/canonical impacts

4. **Open questions**
   - Explicit unresolved items
   - Suggested owner for decision

## Role-Based Handoff Guidance

Copywriter -> Developer/Reviewer:

- Include intended audience and message intent.
- Mark draft vs final status of copy blocks.

Photographer -> Designer/Developer:

- Include usage intent (hero, supporting, background, etc.).
- Include any constraints on usage/selection.

Graphic Designer -> Developer/Reviewer:

- Include asset pack location and intended channel (web/print/social).
- Call out if assets require vector fidelity or specific color space.

Developer -> Team:

- Confirm structure, path consistency, and canonical alignment.
- Flag any scope/contract risk immediately.

## Phase Transition Handoff (Planning -> Implementation Planning)

Before moving phases, confirm:

- `PLAN/PLAN.md` is stable for current review cycle.
- `slate/field-dictionary.md` is stable for current review cycle.
- `docs/spec/DATA-CONTRACTS.md` reflects current contract definitions.
- `SKILLS/uofu-enrollment-branding/references/asset-library.md` is current with asset packs.
- High-priority open questions are either resolved or clearly assigned.

## Constraints

- No handoff is complete if canonical-impacting changes are undocumented.
- No hidden assumptions: unresolved decisions must be written in `Open Questions`.
- Do not treat chat-only context as sufficient handoff documentation.

## Example Handoff Template

```text
Handoff Summary
- Changed:
  - path/to/file1
  - path/to/file2
- Reason:
  - aligns with [scope/goal]
- Review Focus:
  - verify [specific item]
- Open Questions:
  - [question] (owner: [name/role])
```

## Examples

- Copy handoff example: include audience intent, draft/final status, and target file paths for reviewer.

## Open Questions

- Should we enforce this handoff template via PR description format?
- Should we add a handoff log file for milestone checkpoints?
