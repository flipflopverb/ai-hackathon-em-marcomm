---
title: ACCESSIBILITY
owner: team
status: draft
last_updated: 2026-04-17
source_of_truth: false
---

# Accessibility

## Purpose
Capture baseline accessibility expectations for the game experience.

## Inputs
- `../team/QA-CHECKLIST.md`
- `TEST-MATRIX.md`

## Outputs
- Accessibility baseline checklist for planning and implementation.

## Baseline Checks

- Keyboard navigation across start, dialogue, results, and Slate handoff screens
- Visible focus states for all non-canvas UI controls
- Sufficient color contrast for text, HUD elements, and buttons
- Reduced-motion support for camera effects, transitions, and `Swoop` animations
- Readable text sizing on mobile
- Touch target sizing for mobile interaction controls
- Clear text alternatives for non-text UI indicators where practical
- Clear labels and error states on the Slate handoff step

## Game-Specific Concerns

- Movement should not require one precise input method only.
- Dialogue should remain readable without relying on animation timing.
- Critical progression information should not be communicated by color alone.
- If audio is added later, important information should not depend on audio cues.

## Constraints
- Keep checks realistic for v1 and current implementation maturity.

## Examples
- Verify a keyboard-only user can start the game, complete interactions, view results, and reach the Slate handoff CTA.

## Open Questions
- Do we want an explicit on-screen touch-control fallback in v1, or only keyboard plus desktop controls in the first slice?
