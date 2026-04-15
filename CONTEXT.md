---
title: CONTEXT
owner: team
status: canonical
last_updated: 2026-04-15
source_of_truth: true
---

# Context Map

## Purpose

Provide a single navigation file for project context across agent work, team execution, and stakeholder alignment.

## Read Order

1. [PLAN/PLAN.md](PLAN/PLAN.md)
2. [slate/field-dictionary.md](slate/field-dictionary.md)
3. [docs/agents/AGENT-START-HERE.md](docs/agents/AGENT-START-HERE.md)
4. [docs/spec/DATA-CONTRACTS.md](docs/spec/DATA-CONTRACTS.md)
5. [docs/decisions/ADR-0001-scope.md](docs/decisions/ADR-0001-scope.md)
6. [SKILLS/uofu-enrollment-branding/SKILL.md](SKILLS/uofu-enrollment-branding/SKILL.md)

## Key Entry Docs by Layer

- Index: [docs/DOCS-INDEX.md](docs/DOCS-INDEX.md)
- Agents: [docs/agents/AGENT-START-HERE.md](docs/agents/AGENT-START-HERE.md)
- Team: [docs/team/ONBOARDING.md](docs/team/ONBOARDING.md)
- Stakeholders: [docs/stakeholders/PROJECT-BRIEF.md](docs/stakeholders/PROJECT-BRIEF.md)
- Specs: [docs/spec/DATA-CONTRACTS.md](docs/spec/DATA-CONTRACTS.md)
- Decisions: [docs/decisions/ADR-0001-scope.md](docs/decisions/ADR-0001-scope.md)

## Canonical Sources (Current)

| Area | Source | Purpose |
| --- | --- | --- |
| Scope and boundaries | `PLAN/PLAN.md` | Product goal, non-goals, v1 boundaries, QA targets |
| Slate handoff fields | `slate/field-dictionary.md` | Visible fields, hidden fields, enums, mapping contract |
| Brand/design execution guidance | `SKILLS/uofu-enrollment-branding/` | Campaign-aligned copy/design/system references and assets |

## Context Layers (Target Structure)

| Layer | Location | Status | Notes |
| --- | --- | --- | --- |
| Agent context | `docs/agents/` | in progress | Start with `docs/agents/AGENT-START-HERE.md` |
| Team context | `docs/team/` | in progress | Onboarding, setup, workflow, QA, handoff drafts |
| Stakeholder context | `docs/stakeholders/` | in progress | Brief/scope/milestones/demo/submission drafts |
| Specs/contracts | `docs/spec/` | in progress | Start with `docs/spec/DATA-CONTRACTS.md` |
| Decision history | `docs/decisions/` | in progress | Start with `docs/decisions/ADR-0001-scope.md` |

## Target Directory Map

```text
/
  README.md
  CONTEXT.md
  /docs
    /agents
      AGENT-START-HERE.md
      AGENT-RULES.md
      AGENT-PRIORITIES.md
      AGENT-CONTEXT-MAP.md
    /team
      ONBOARDING.md
      DEV-SETUP.md
      WORKFLOW.md
      QA-CHECKLIST.md
      HANDOFF.md
    /stakeholders
      PROJECT-BRIEF.md
      SCOPE.md
      MILESTONES.md
      DEMO-SCRIPT.md
      SUBMISSION-CHECKLIST.md
    /spec
      DATA-CONTRACTS.md
      EVENT-FLOWS.md
      STATE-MACHINE.md
      API-CONTRACTS.md
    /decisions
      ADR-0001-scope.md
      ADR-0002-data-model.md
      ADR-0003-slate-handoff.md
    /examples
      sample-inputs.json
      sample-outputs.json
      sample-prompts.md
    /qa
      TEST-MATRIX.md
      EDGE-CASES.md
      ACCESSIBILITY.md
  /slate
    field-dictionary.md
    hidden-field-mapping.md
  /codex
    workspace-notes.md
    prompt-pack.md
    evals.md
  /SKILLS
    ...
```

## Constraints

- Keep `PLAN/PLAN.md` as scope source of truth.
- Keep `slate/field-dictionary.md` as Slate field source of truth.
- Do not duplicate canonical definitions across multiple files.
- Keep this file as a map; store detailed rules/specs in their canonical files.

## Open Questions

- Which docs should be marked canonical vs supporting once `docs/` is created?
- What is the preferred update workflow for `last_updated` metadata across docs?
