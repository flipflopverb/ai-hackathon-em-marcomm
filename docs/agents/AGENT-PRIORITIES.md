---
title: AGENT-PRIORITIES
owner: team
status: canonical
last_updated: 2026-04-17
source_of_truth: true
---

# Agent Priorities

## Purpose

Define execution priority order for agent work when constraints or tradeoffs conflict.

## Inputs

- [docs/agents/AGENT-START-HERE.md](AGENT-START-HERE.md)
- [docs/agents/AGENT-RULES.md](AGENT-RULES.md)
- [PLAN/PLAN.md](../../PLAN/PLAN.md)
- [docs/spec/DATA-CONTRACTS.md](../spec/DATA-CONTRACTS.md)
- [slate/field-dictionary.md](../../slate/field-dictionary.md)

## Outputs

- Consistent decision-making during edits
- Reduced ambiguity when speed and safety compete

## Priority Order

1. **Contract integrity**
Keep gameplay scope, data contracts, and Slate payload definitions valid.

2. **Data safety and privacy**
Never introduce PII leakage or unsafe query-parameter behavior.

3. **Canonical consistency**
Keep all changes aligned with canonical sources and naming.

4. **Correctness over completeness**
Prefer shipping accurate partial progress over broad but risky changes.

5. **Maintainability**
Choose structures that reduce future drift and duplication.

6. **Delivery speed**
Move quickly only after the above priorities are satisfied.

## Decision Rules

When priorities conflict:

- Higher-priority rule wins.
- If conflict touches canonical files or required field semantics, stop and request approval.
- If conflict is documentation-only and non-canonical, choose the simpler reversible change.

## Examples

Example A:

- Option 1: add extra gameplay metadata to the Slate payload for convenience.
- Option 2: keep the minimal payload and preserve contract stability.
- Decision: choose Option 2.

Example B:

- Option 1: build a second map before the first loop is validated.
- Option 2: finish one complete playable slice first.
- Decision: choose Option 2.

## Constraints

- Do not override canonical files by implication.
- Do not optimize for speed at the expense of contract stability.

## Open Questions

- Should we formalize “stop and request approval” triggers in a checklist format?
