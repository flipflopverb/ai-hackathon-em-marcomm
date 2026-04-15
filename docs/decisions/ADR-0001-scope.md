---
title: ADR-0001-SCOPE
owner: team
status: canonical
last_updated: 2026-04-15
source_of_truth: true
---

# ADR-0001: v1 Scope Boundary

## Purpose

Record the scope decision for v1 so implementation and planning stay aligned across product, engineering, and agent work.

## Inputs

- [PLAN/PLAN.md](../../PLAN/PLAN.md)
- [docs/spec/DATA-CONTRACTS.md](../spec/DATA-CONTRACTS.md)
- [slate/field-dictionary.md](../../slate/field-dictionary.md)

## Decision

For v1, the product will ship a single shared discovery game flow with a college exploration branch, compute two primary outcomes (`profile`, `academic_interest`), and hand off to embedded Slate RFI using the defined hidden-field contract.

Out of scope for v1:

- Separate in-state and out-of-state game experiences
- Deep adaptive branching that rewrites the whole journey
- Full custom content for every profile x interest combination
- In-game PII form collection
- CRM routing/automation logic beyond Slate submission boundary

## Outputs

This decision establishes:

- A narrow v1 execution target
- A stable game-to-Slate handoff boundary
- Clear non-goals to reduce scope creep

## Constraints

- Keep median completion time in the 2-5 minute target
- Keep PII out of query parameters
- Preserve required hidden fields for Slate handoff
- Keep scope and field contract definitions canonical in `PLAN/PLAN.md` and `slate/field-dictionary.md`

## Consequences

Positive:

- Faster implementation and testing path
- Lower integration risk for first release
- Clear QA and demo boundary

Tradeoffs:

- Limited personalization depth in v1
- Deferred CRM sophistication and audience-specific journey versions

## Last Verified

- Verified against `PLAN/PLAN.md` and `slate/field-dictionary.md` on 2026-04-15.

## Examples

In-scope example:

- Student completes one shared game flow, sees `profile + academic_interest`, then submits Slate form with required hidden fields.

Out-of-scope example:

- Student is routed into a completely different game experience based on early state prediction.

## Open Questions

- What criteria will trigger ADR-0002 for expanding beyond the single-flow model?
- When should multi-version audience experiences be reconsidered?
- What minimum evidence is required to move CRM routing from out-of-scope to in-scope?
