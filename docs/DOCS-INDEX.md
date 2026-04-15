---
title: DOCS-INDEX
owner: team
status: canonical
last_updated: 2026-04-15
source_of_truth: true
---

# Docs Index

## Purpose

Provide a single-table index of core documentation and reference files.

## Inputs

- `CONTEXT.md`
- Markdown frontmatter metadata in `docs/`, `slate/`, and `codex/`

## Outputs

- Fast navigation for team members and agents
- Clear visibility of canonical vs draft documents

## Index

| Path | Owner | Status | Source of Truth | Purpose |
| --- | --- | --- | --- | --- |
| `README.md` | n/a | n/a | n/a | Build a branded student discovery game experience and a reliable Slate handoff contract for enrollment marketing. |
| `CONTEXT.md` | team | canonical | true | Provide a single navigation file for project context across agent work, team execution, and stakeholder alignment. |
| `docs/agents/AGENT-START-HERE.md` | team | canonical | true | Provide the minimum required context for an agent to make safe, high-value changes in this repository. |
| `docs/agents/AGENT-RULES.md` | team | canonical | true | Define non-negotiable operating rules for agent contributions in this repository. |
| `docs/agents/AGENT-PRIORITIES.md` | team | canonical | true | Define execution priority order for agent work when constraints or tradeoffs conflict. |
| `docs/agents/AGENT-CONTEXT-MAP.md` | team | canonical | true | Map repository files to their intent, authority level, and usage timing for agent workflows. |
| `docs/team/ONBOARDING.md` | team | canonical | true | Provide a quick team-level understanding of project scope, goals, and current boundaries. |
| `docs/team/DEV-SETUP.md` | team | canonical | true | Document the practical local setup for this hackathon team so contributors can clone the repo and work in Codex. |
| `docs/team/WORKFLOW.md` | team | canonical | true | Define how the team collaborates in the current project phase, focused on context alignment and asset contribution. |
| `docs/team/QA-CHECKLIST.md` | team | canonical | true | Provide a lightweight quality checklist for the current planning and asset-ingestion phase. |
| `docs/team/HANDOFF.md` | team | canonical | true | Define what must be true before handing off work between contributors and before moving from planning/assets phase to implementation planning. |
| `docs/stakeholders/PROJECT-BRIEF.md` | team | draft | false | Describe the problem, target users, and value of the v1 discovery game. |
| `docs/stakeholders/SCOPE.md` | team | draft | false | Summarize what is in/out of v1 in plain language. |
| `docs/stakeholders/MILESTONES.md` | team | draft | false | Track delivery phases and completion criteria. |
| `docs/stakeholders/DEMO-SCRIPT.md` | team | draft | false | Provide a repeatable live demo narrative. |
| `docs/stakeholders/SUBMISSION-CHECKLIST.md` | team | draft | false | Track required materials before final hackathon submission. |
| `docs/spec/DATA-CONTRACTS.md` | team | canonical | true | Define the canonical data contracts for the v1 discovery game and the Slate handoff boundary. |
| `docs/spec/EVENT-FLOWS.md` | team | draft | false | Define key event sequences from entry to Slate handoff. |
| `docs/spec/STATE-MACHINE.md` | team | draft | false | Describe game states and transitions at a high level. |
| `docs/spec/API-CONTRACTS.md` | team | draft | false | Document any external/internal API boundaries once implementation interfaces are defined. |
| `docs/decisions/ADR-0001-scope.md` | team | canonical | true | Record the scope decision for v1 so implementation and planning stay aligned across product, engineering, and agent work. |
| `docs/decisions/ADR-0002-data-model.md` | team | draft | false | Capture the rationale for data model choices once IDs and structures are finalized. |
| `docs/decisions/ADR-0003-slate-handoff.md` | team | draft | false | Capture final decision rationale for where game scope ends and Slate responsibility begins. |
| `docs/qa/TEST-MATRIX.md` | team | draft | false | Outline key test scenarios for gameplay completion and Slate handoff. |
| `docs/qa/EDGE-CASES.md` | team | draft | false | Track known edge cases that could break user flow or handoff integrity. |
| `docs/qa/ACCESSIBILITY.md` | team | draft | false | Capture baseline accessibility expectations for the game experience. |
| `docs/examples/sample-prompts.md` | team | draft | false | Provide reusable prompt starters for recurring team tasks. |
| `docs/examples/sample-inputs.json` | n/a | draft | false | Example input payload for gameplay/session processing. |
| `docs/examples/sample-outputs.json` | n/a | draft | false | Example output payload for game-to-Slate handoff metadata. |
| `slate/field-dictionary.md` | n/a | canonical | true | Define Slate visible + hidden field contracts, enums, and query mapping for v1 handoff. |
| `slate/hidden-field-mapping.md` | team | draft | false | Provide a compact mapping reference for game metadata -> Slate hidden fields. |
| `codex/workspace-notes.md` | team | draft | false | Capture practical notes for Codex-based collaboration in this repo. |
| `codex/prompt-pack.md` | team | draft | false | Store reusable prompts for recurring repo tasks. |
| `codex/evals.md` | team | draft | false | Track simple evaluation notes for Codex-assisted outputs. |

## Constraints

- Canonical source definitions in this index must match file frontmatter and known project authority boundaries.

## Examples

- Use this file to quickly identify which docs are safe to revise (`draft`) versus high-governance (`canonical`).

## Open Questions

- Should this index be auto-generated from frontmatter in the future?
