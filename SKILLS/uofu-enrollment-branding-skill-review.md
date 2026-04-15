# uofu-enrollment-branding Skill Review

This review covers the current skill implementation in `SKILLS/uofu-enrollment-branding/`, including `SKILL.md`, `agents/openai.yaml`, `references/`, and `assets/`.

## Top 10 Improvement Suggestions

1. **Add a version + refresh process for source-derived references**
- Why: `strategy`, `color`, and `typography` references were extracted from live pages and can drift over time.
- Improve: Add `references/source-sync.md` with fetch date, source URLs, refresh cadence, and exact extraction commands.
- Focus: Make updates repeatable and auditable.

2. **Create a single asset manifest for machine-usable indexing**
- Why: The asset catalog is human-readable, but not structured for deterministic selection.
- Improve: Add `assets/asset-manifest.json` with fields like `pack`, `format`, `color_space`, `channel`, `use_case`, `path`.
- Focus: Enable faster and more consistent asset picking in future runs.

3. **Normalize folder naming for long-term maintainability**
- Why: Mixed naming styles remain (`_EPS`, `_PNG`, `_Swatch Files`, spaces in filenames).
- Improve: Keep vendor originals, but add normalized aliases or a canonical mapping section in the manifest.
- Focus: Reduce path friction and brittle references in automation.

4. **Add channel-specific output specs reference**
- Why: Skill is strong on brand voice/design rules, but light on execution specs.
- Improve: Add `references/channel-specs.md` with recommended dimensions, safe areas, export formats, and file naming for web/social/email/print.
- Focus: Make outputs production-ready, not just brand-aligned.

5. **Add a compliance checklist template file for final reviews**
- Why: QA rules exist, but there is no reusable checklist artifact.
- Improve: Add `assets/templates/brand-qa-checklist.md` and reference it in `SKILL.md`.
- Focus: Standardize review quality across deliverables.

6. **Add example-driven usage tests for the skill**
- Why: The skill has no embedded “test prompts + expected structure” examples.
- Improve: Add `references/test-cases.md` with 5-8 representative prompts and pass/fail criteria.
- Focus: Improve reliability when iterating on skill instructions.

7. **Clarify rights/licensing and permitted usage per asset pack**
- Why: AI/EPS/TTF assets are present, but no explicit usage guardrails are documented in the repo.
- Improve: Add `references/asset-usage-rights.md` noting internal-use assumptions, redistribution limits, and approval requirements.
- Focus: Prevent downstream legal/compliance mistakes.

8. **Tighten `SKILL.md` to reduce instruction overhead**
- Why: Current `SKILL.md` is solid but can be more directive for rapid execution.
- Improve: Add a short decision table (“task type -> references to load -> output template to use”) near Quick Start.
- Focus: Faster, more deterministic behavior with less context scanning.

9. **Add lightweight automation scripts for recurring checks**
- Why: Current quality checks are manual.
- Improve: Add scripts under `scripts/` for:
  - asset/doc path validation
  - missing-file detection from references
  - optional color/typography consistency checks
- Focus: Catch regressions quickly as the skill grows.

10. **Add deliverable starter templates for common campaign outputs**
- Why: The skill defines guidance, but users still start from blank files for frequent outputs.
- Improve: Add `assets/templates/` starter files for common formats (social square/story, email module, one-sheet layout brief, landing-page hero block) with placeholders.
- Focus: Speed up execution while keeping brand consistency from the first draft.

## What To Focus On Next

1. **Reliability first**: implement #1, #2, #3 so documentation and assets stay synchronized.
2. **Production readiness**: implement #4, #5, and #10 so outputs are deployment-ready and faster to produce.
3. **Maintainability at scale**: implement #3 and #9 before adding many more asset packs.
4. **Quality loop**: implement #6 to make future skill edits safer.
