---
title: SAMPLE-PROMPTS
owner: team
status: draft
last_updated: 2026-04-15
source_of_truth: false
---

# Sample Prompts

## Purpose
Provide reusable prompt starters for recurring team tasks.

## Inputs
- `../../CONTEXT.md`
- `../agents/AGENT-START-HERE.md`

## Outputs
- Reusable prompt set for common repo tasks.

## Examples

- Update question bank:
  - "Propose 5 new question variants that still map cleanly to existing profile IDs."
- Validate Slate mapping:
  - "Compare hidden-field mappings in docs/spec and slate/field-dictionary, then list mismatches."
- Organize assets:
  - "Review new files under SKILLS assets and suggest final folder placement + naming fixes."
- Draft result copy:
  - "Generate 3 short result variants for profile=achiever and interest=engineering_technology."

## Constraints
- Prompts must preserve canonical field names and scope boundaries.

## Open Questions
- Which prompts should become canonical templates in `codex/prompt-pack.md`?
