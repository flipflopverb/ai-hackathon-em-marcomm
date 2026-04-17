---
title: AGENT-CONTEXT-MAP
owner: team
status: canonical
last_updated: 2026-04-17
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
| `README.md` | entry | no | first-pass orientation | High-level project purpose and repo structure |
| `CONTEXT.md` | navigation | yes | before planning edits | Read order, canonical sources, runtime structure |
| `PLAN/PLAN.md` | scope | yes | before changing behavior/specs | Product goals, boundaries, phases, and success criteria |
| `PLAN/stack.md` | stack | yes | before runtime architecture changes | Engine, build, map, and hosting choices |
| `docs/spec/DATA-CONTRACTS.md` | spec | yes | before modeling runtime or payload changes | Gameplay objects, session model, and output contract |
| `slate/field-dictionary.md` | contract | yes | before handoff changes | Slate visible and hidden fields, mapping, and validation |
| `docs/agents/AGENT-START-HERE.md` | agent | yes | always before editing | Agent read order, boundaries, validation |
| `docs/agents/AGENT-RULES.md` | agent | yes | when uncertain about edit safety | Must-follow policy and approval boundaries |
| `docs/agents/AGENT-PRIORITIES.md` | agent | yes | when tradeoffs arise | Decision hierarchy for conflicting constraints |
| `docs/agents/AGENT-CONTEXT-MAP.md` | agent | yes | during onboarding | File authority and navigation |
| `docs/decisions/ADR-0001-scope.md` | decisions | yes | when scope ambiguity appears | Why v1 is intentionally one map and one loop |
| `src/game/` | runtime | no | before gameplay edits | Scenes, movement, triggers, session logic |
| `src/content/` | runtime | no | before content or scoring edits | Landmark, map, item, and result data |
| `src/ui/` | runtime | no | before overlay or HUD edits | Dialogue, HUD, results, and handoff UI |
| `assets/` | runtime assets | no | before asset-related edits | Maps, sprites, tilesets, and audio |
| `SKILLS/uofu-enrollment-branding/SKILL.md` | skill | yes (skill-local) | for branding/content/design tasks | Skill workflow and resource entry points |
| `SKILLS/uofu-enrollment-branding/references/*` | skill references | yes (skill-local) | as needed | Strategy, color, type, and asset guidance |

## Read Sequences by Task Type

### Contract-sensitive task

1. `docs/agents/AGENT-START-HERE.md`
2. `PLAN/PLAN.md`
3. `PLAN/stack.md`
4. `docs/spec/DATA-CONTRACTS.md`
5. `slate/field-dictionary.md`
6. Relevant target files

### Runtime implementation task

1. `docs/agents/AGENT-START-HERE.md`
2. `PLAN/PLAN.md`
3. `PLAN/stack.md`
4. `docs/spec/DATA-CONTRACTS.md`
5. Relevant files under `src/` and `assets/`

### Branding or content task

1. `docs/agents/AGENT-START-HERE.md`
2. `CONTEXT.md`
3. `PLAN/PLAN.md`
4. `SKILLS/uofu-enrollment-branding/SKILL.md`
5. Relevant `SKILLS/.../references/*.md`

## Constraints

- Do not treat non-canonical docs as contract authority.
- Do not override canonical values by copying stale content into new files.
- If canonical sources conflict, stop and request a human decision.

## Open Questions

- Should this map include per-file owners once runtime implementation spreads across more directories?
