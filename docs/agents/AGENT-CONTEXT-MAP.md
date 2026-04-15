---
title: AGENT-CONTEXT-MAP
owner: team
status: canonical
last_updated: 2026-04-15
source_of_truth: true
---

# Agent Context Map

## Purpose

Map repository files to their intent, authority level, and usage timing for agent workflows.

## Inputs

- [CONTEXT.md](../../CONTEXT.md)
- [docs/agents/AGENT-START-HERE.md](AGENT-START-HERE.md)
- [docs/agents/AGENT-RULES.md](AGENT-RULES.md)

## Outputs

- A deterministic navigation map for agent context loading
- Reduced duplication and fewer conflicting edits

## File-to-Purpose Map

| Path | Category | Canonical | When to Read | Purpose |
| --- | --- | --- | --- | --- |
| `README.md` | entry | no | first-pass orientation | High-level project purpose + pointers |
| `CONTEXT.md` | navigation | yes | before planning edits | Context layers, read order, target docs map |
| `PLAN/PLAN.md` | scope | yes | before changing behavior/specs | Product goals, boundaries, non-goals, QA targets |
| `slate/field-dictionary.md` | contract | yes | before field or handoff changes | Slate visible/hidden fields, enums, mapping |
| `docs/agents/AGENT-START-HERE.md` | agent | yes | always before editing | Agent read order, boundaries, validation |
| `docs/agents/AGENT-RULES.md` | agent | yes | when uncertain about edit safety | Must-follow policy and approval boundaries |
| `docs/agents/AGENT-PRIORITIES.md` | agent | yes | when tradeoffs arise | Decision hierarchy for conflicting constraints |
| `docs/agents/AGENT-CONTEXT-MAP.md` | agent | yes | during planning and onboarding | File authority and navigation |
| `docs/spec/DATA-CONTRACTS.md` | spec | yes | when modeling payloads/contracts | Structured object definitions and examples |
| `docs/decisions/ADR-0001-scope.md` | decisions | yes | when scope ambiguity appears | Why v1 scope was intentionally constrained |
| `SKILLS/uofu-enrollment-branding/SKILL.md` | skill | yes (skill-local) | for branding/content/design tasks | Skill workflow and resource entry points |
| `SKILLS/uofu-enrollment-branding/references/*` | skill references | yes (skill-local) | as needed by task | Strategy/color/type/asset guidance |
| `SKILLS/uofu-enrollment-branding/assets/*` | skill assets | supporting | during output production | Reusable campaign files for deliverables |
| `repo-dir-structure.txt` | utility | no | optional | Snapshot of repository tree at generation time |

## Read Sequences by Task Type

### Contract-sensitive task

1. `docs/agents/AGENT-START-HERE.md`
2. `PLAN/PLAN.md`
3. `slate/field-dictionary.md`
4. `docs/spec/DATA-CONTRACTS.md`
5. Relevant target files

### Branding/design/content task

1. `docs/agents/AGENT-START-HERE.md`
2. `CONTEXT.md`
3. `SKILLS/uofu-enrollment-branding/SKILL.md`
4. Relevant `SKILLS/.../references/*.md`
5. Relevant `SKILLS/.../assets/*`

### Documentation architecture task

1. `CONTEXT.md`
2. `docs/agents/AGENT-RULES.md`
3. `docs/agents/AGENT-PRIORITIES.md`
4. Target docs under `docs/`

## Constraints

- Do not treat non-canonical docs as contract authority.
- Do not override canonical values by copying stale content into new files.
- If canonical sources conflict, stop and request human decision.

## Examples

- For a contract-sensitive change, load `PLAN/PLAN.md` and `slate/field-dictionary.md` before touching spec docs.

## Open Questions

- Should we add a `status: draft|canonical|deprecated` index file for all docs?
- Should this map include owner/contact metadata per file?
