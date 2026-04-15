---
title: DEV-SETUP
owner: team
status: canonical
last_updated: 2026-04-15
source_of_truth: true
---

# Dev Setup

## Purpose

Document the practical local setup for this hackathon team so contributors can clone the repo and work in Codex.

## Inputs

- [README.md](../../README.md)
- [CONTEXT.md](../../CONTEXT.md)
- [PLAN/PLAN.md](../../PLAN/PLAN.md)

## Outputs

After setup, contributors should be able to:

- Clone the repository to their workstation
- Open the repository in the Codex app
- Understand where key project files live

## Current Setup (Phase 0)

Required:

- GitHub account with repo access
- Git installed
- **Codex app** (required editor/workspace tool)

Recommended:

- GitHub Desktop (easier clone/pull workflow for non-developers)

Repository actions currently expected:

- Open/read docs
- Review assets and references
- Contribute copy, design inputs, and feedback via files in the repo

## Not Yet Defined

The following are intentionally not locked yet:

- Application runtime stack/framework
- Build pipeline
- Test runner and CI workflow
- Deployment environment

Do not assume these until implementation planning explicitly defines them.

## Setup Steps (macOS and Windows)

Repository URL:

- `https://github.com/uu-slate-admin/ai-hackathon-em-marcomm.git`

1. Install Git (if not already installed).
2. Clone the repo:
   - Option A (recommended for most team members): use GitHub Desktop -> `File` -> `Clone repository`.
   - Option B (CLI): `git clone https://github.com/uu-slate-admin/ai-hackathon-em-marcomm.git`.
3. Open the cloned folder in Codex app.
4. Confirm these files are visible:
   - `README.md`
   - `CONTEXT.md`
   - `PLAN/PLAN.md`
   - `slate/field-dictionary.md`
   - `SKILLS/uofu-enrollment-branding/`

## Setup Verification Checklist

- Repo is cloned locally.
- Repo opens in Codex app.
- Team member can navigate to plan + context + slate docs.
- Team member knows where to place edits/files for their role.

## Team Role Notes

- Lead developer: owns implementation decisions and technical merges.
- Secondary developer: supports coding and technical validation.
- Copywriter: contributes copy drafts and messaging revisions in markdown/docs files.
- Graphic designer: contributes asset updates in `SKILLS/uofu-enrollment-branding/assets/`.
- Photographer: contributes/selects approved imagery assets and references.

## Constraints

- Keep instructions simple for mixed technical backgrounds.
- Treat Codex app as the default collaboration environment.
- Keep canonical scope/contract files unchanged unless explicitly approved by project lead.

## Examples

- Good setup outcome: teammate clones repo with GitHub Desktop, opens in Codex, and can navigate to `PLAN/PLAN.md` and `CONTEXT.md`.

## Open Questions

- Should we provide a one-page visual “repo tour” for non-technical contributors?
- Should we standardize GitHub Desktop as the default for all non-developer roles?
- Do we want a short “how to pull latest changes” guide as a separate file?
