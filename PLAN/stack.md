# Stack Decision: Campus Exploration Game

## Chosen Stack

| Layer | Choice |
| --- | --- |
| Game engine | Phaser 3 |
| Build tool | Vite |
| Language | JavaScript |
| Map authoring | Tiled |
| UI overlays | HTML + CSS |
| Content/data | Static JSON or JS data modules |
| Hosting | GitHub Pages |
| Local dev | Vite dev server |

This project should use a real browser game stack, not a no-build static microsite stack.

## Why This Stack

- `Phaser 3` gives the project the core game systems it actually needs: scenes, sprites, tilemaps, camera movement, collisions, input handling, animation, and asset loading.
- `Vite` gives fast local development and a clean static production build that GitHub Pages can host.
- `Tiled` is the fastest practical way to build a Pokemon-style campus map with walkable areas, collision layers, and landmark trigger zones.
- HTML and CSS overlays are still useful for dialogue panels, HUD elements, result screens, and the Slate handoff UI.
- Keeping the runtime fully client-side preserves GitHub Pages compatibility.

## Why Not The Old Stack

The previous “HTML + CSS + vanilla JS + no build step” approach was acceptable for a survey-like prototype, but it is the wrong default for a map-based exploration game.

Problems with the old stack for this concept:
- You would end up hand-building scene management, animation timing, movement, collision, and asset loading.
- Map editing would be slower and less repeatable without a tilemap workflow.
- Runtime complexity would still exist, just hidden inside ad hoc JavaScript instead of an engine built for it.

## Runtime Architecture

Recommended runtime structure:

```text
/
  index.html
  public/
  src/
    main.js
    scenes/
      BootScene.js
      TitleScene.js
      CampusScene.js
      ResultsScene.js
      HandoffScene.js
    systems/
      sessionState.js
      academicInterest.js
      swoopProgression.js
      slatePayload.js
    content/
      mapScenes.js
      locationTriggers.js
      dialogueEvents.js
      collectibleItems.js
      academicInterests.js
      resultMappings.js
    ui/
      hud.js
      dialogueOverlay.js
      resultOverlay.js
  assets/
    maps/
    sprites/
    audio/
    tilesets/
```

## Core Systems For v1

The first playable slice should include:

- One campus map scene
- Player movement on a tile-based or grid-aware map
- Camera follow behavior
- Collision boundaries
- 5-8 landmark trigger zones
- Short dialogue or prompt interactions
- `Swoop` growth progression
- Collectible tracking
- `academic_interest` scoring
- Result screen
- Slate handoff CTA/screen

## Map Workflow

Use `Tiled` for map production.

Recommended approach:
- Create the campus map in Tiled
- Define walkable and blocked layers
- Define object layers for trigger zones and spawn points
- Export the map as JSON
- Load the exported map into Phaser

This will be much faster to iterate than hardcoding landmark positions and collision data by hand.

## Data Approach

Keep gameplay content data-driven where possible.

Recommended modules:
- `mapScenes`
- `locationTriggers`
- `dialogueEvents`
- `collectibleItems`
- `academicInterests`
- `resultMappings`

These can start as JS modules for speed, then move to JSON later if needed.

## GitHub Pages Deployment

This stack is compatible with GitHub Pages because the final build is static.

Recommended deployment flow:
- Run `vite build`
- Deploy the generated `dist/` directory to GitHub Pages
- Use a GitHub Actions workflow or `gh-pages` branch publishing

Important config note:
- Set Vite `base` correctly if the project is deployed as a GitHub Pages project site rather than a custom domain or user site.
- Asset paths must be relative to the configured Vite base so sprites, maps, and tilesets load correctly in production.

## Slate Handoff

Slate remains a final handoff step, not the runtime core.

If the player continues to Slate, the game should pass only:

| Field | Source |
| --- | --- |
| `game_academic_interest` | Computed at result screen |
| `game_version` | Game/content contract version |
| `game_session_id` | Generated at game start |
| `game_completed_at` | Timestamp at result completion |

No PII, `swoop_stage`, or collectible data should be passed via query parameters in v1.

## Next Steps

1. Initialize the repo as a Vite app.
2. Add Phaser runtime bootstrapping and scene structure.
3. Create the first campus map in Tiled and export it as JSON.
4. Wire movement, triggers, `Swoop` progression, and `academic_interest` scoring.
5. Add the result screen and Slate payload builder.
