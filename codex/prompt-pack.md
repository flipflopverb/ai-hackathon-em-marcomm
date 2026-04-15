---
title: PROMPT-PACK
owner: team
status: draft
last_updated: 2026-04-15
source_of_truth: false
---

# Prompt Pack

## Purpose
Store reusable prompts for recurring repo tasks.

## Inputs
- `../CONTEXT.md`
- `../docs/examples/sample-prompts.md`

## Outputs
- Team-approved prompt templates for repeated workflows.

## Prompt Templates

1. Contract consistency check:
   - "Compare PLAN, data contracts, and Slate dictionary; list mismatches."
2. Asset organization pass:
   - "Review new assets and propose final pack placement + naming cleanup."
3. Copy alignment pass:
   - "Rewrite draft copy to align with campaign voice and selected profile/interest."
4. Context drift check:
   - "Identify docs that conflict with canonical scope or field definitions."

## Constraints
- Prompts must preserve canonical naming and scope constraints.

## Examples
- Use the contract consistency prompt before merging spec or slate mapping edits.

## Open Questions
- Which prompts should be role-specific (developer vs design vs copy)?
