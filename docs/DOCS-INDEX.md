---
title: DOCS-INDEX
owner: team
status: canonical
last_updated: 2026-04-17
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
| `README.md` | n/a | n/a | n/a | Introduce the repo as a campus exploration game and runtime scaffold. |
| `CONTEXT.md` | team | canonical | true | Provide a single navigation file for project context across agent work, team execution, and stakeholder alignment. |
| `PLAN/PLAN.md` | team | canonical | true | Define product scope, gameplay loop, phases, and success criteria. |
| `PLAN/stack.md` | team | canonical | true | Define the implementation stack and GitHub Pages deployment direction. |
| `PLAN/hackathon-info.md` | team | supporting | false | Capture external hackathon logistics and submission context. |
| `docs/agents/AGENT-START-HERE.md` | team | canonical | true | Provide the minimum required context for an agent to make safe changes. |
| `docs/agents/AGENT-RULES.md` | team | canonical | true | Define non-negotiable operating rules for agent contributions. |
| `docs/agents/AGENT-PRIORITIES.md` | team | canonical | true | Define decision priority order for agent work. |
| `docs/agents/AGENT-CONTEXT-MAP.md` | team | canonical | true | Map files to authority level and usage timing. |
| `docs/team/ONBOARDING.md` | team | canonical | true | Provide a quick team-level understanding of the game concept and repo boundaries. |
| `docs/team/DEV-SETUP.md` | team | canonical | true | Document practical local setup for contributors. |
| `docs/team/WORKFLOW.md` | team | canonical | true | Define collaboration flow for the playable vertical slice. |
| `docs/team/QA-CHECKLIST.md` | team | canonical | true | Provide a lightweight quality checklist for current work. |
| `docs/team/HANDOFF.md` | team | canonical | true | Define what must be true before handing off gameplay, content, UI, or asset work. |
| `docs/spec/DATA-CONTRACTS.md` | team | canonical | true | Define the canonical gameplay and Slate handoff contracts for v1. |
| `docs/spec/EVENT-FLOWS.md` | team | draft | false | Define key runtime event sequences from game boot to Slate handoff. |
| `docs/spec/STATE-MACHINE.md` | team | draft | false | Describe game states and transitions for the campus exploration slice. |
| `docs/spec/API-CONTRACTS.md` | team | draft | false | Document browser-facing interfaces and payload builders needed for the prototype. |
| `docs/decisions/ADR-0001-scope.md` | team | canonical | true | Record the scope decision for the one-map exploration-game v1. |
| `docs/decisions/ADR-0002-data-model.md` | team | draft | false | Capture rationale for gameplay data-model choices once finalized. |
| `docs/decisions/ADR-0003-slate-handoff.md` | team | draft | false | Capture final decision rationale for where game scope ends and Slate begins. |
| `docs/stakeholders/PROJECT-BRIEF.md` | team | draft | false | Describe the audience, problem, and value of the game for stakeholders. |
| `docs/stakeholders/SCOPE.md` | team | draft | false | Summarize v1 in-scope and out-of-scope work in plain language. |
| `docs/stakeholders/MILESTONES.md` | team | draft | false | Track delivery phases and completion criteria. |
| `docs/stakeholders/DEMO-SCRIPT.md` | team | draft | false | Provide a repeatable live demo narrative. |
| `docs/stakeholders/SUBMISSION-CHECKLIST.md` | team | draft | false | Track materials needed for final hackathon submission. |
| `docs/qa/TEST-MATRIX.md` | team | draft | false | Outline key test scenarios for gameplay completion and Slate handoff. |
| `docs/qa/EDGE-CASES.md` | team | draft | false | Track edge cases that could break gameplay or handoff integrity. |
| `docs/qa/ACCESSIBILITY.md` | team | draft | false | Capture baseline accessibility expectations for the game experience. |
| `docs/examples/sample-inputs.json` | n/a | draft | false | Example in-memory game session payload for runtime design. |
| `docs/examples/sample-outputs.json` | n/a | draft | false | Example output payload for game-to-Slate handoff metadata. |
| `docs/examples/sample-prompts.md` | team | draft | false | Provide reusable prompt starters for recurring repo tasks. |
| `slate/field-dictionary.md` | n/a | canonical | true | Define Slate visible and hidden field contracts for v1 handoff. |
| `slate/hidden-field-mapping.md` | team | draft | false | Provide a compact mapping reference for game metadata to Slate hidden fields. |
| `codex/prompt-pack.md` | team | draft | false | Store reusable prompts for recurring repo tasks. |
| `codex/workspace-notes.md` | team | draft | false | Capture practical notes for Codex-based collaboration in this repo. |
| `codex/evals.md` | team | draft | false | Track lightweight evaluation notes for Codex-assisted work. |

## Constraints

- Canonical source definitions in this index must match file frontmatter and project authority boundaries.

## Open Questions

- Should this index be auto-generated from frontmatter in the future?
