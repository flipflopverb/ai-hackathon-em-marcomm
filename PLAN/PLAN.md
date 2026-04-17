# University of Utah Campus Exploration Game Plan

## 1) Product Summary

Build a short, branded campus exploration game for prospective students that feels like a lightweight Pokemon-style walkaround with a Tamagotchi-style `Swoop` companion.

The player should:
- walk through a stylized University of Utah campus map
- discover landmarks and student-life moments
- trigger short interactions tied to academics, belonging, and future goals
- help `Swoop` hatch and grow through exploration
- collect campus-themed items
- finish with a clear `academic_interest` result
- optionally continue to a Slate RFI handoff

The game should feel playful, exploratory, and distinctly University of Utah. It should not feel like a survey dressed up as a game.

## 2) Core v1 Experience

v1 is a single playable vertical slice.

The v1 experience includes:
- one top-down campus map
- one controllable player character
- one `Swoop` companion with visible growth progression
- 5-8 landmark interactions
- a collectible system
- one `academic_interest` result
- one result screen with next-step CTA
- one optional Slate handoff

The target completion time is 2-5 minutes.

## 3) Player Loop

The core gameplay loop for v1 is:

1. Player starts the game and enters the campus map.
2. Player walks to a landmark or point of interest.
3. A short interaction opens:
   - dialogue
   - a quick choice
   - a discovery moment
4. Completing the interaction:
   - adds weight toward one or more `academic_interest` outcomes
   - advances `Swoop` growth
   - may award a collectible item
5. Player returns to exploration and repeats until the run is complete.
6. Game resolves the final result and shows:
   - `academic_interest`
   - final `swoop_stage`
   - collected items
7. Player can continue to Slate.

## 4) Design Principles

The game should follow these principles:

- Exploration first: movement and discovery are the primary mode of progress.
- Short interactions: each stop should be fast and readable on mobile.
- Place-based storytelling: landmarks should make campus feel real and memorable.
- Companion-driven emotion: `Swoop` growth should create a sense of care and momentum.
- Clear payoff: the result should feel earned, not random.
- Lightweight scope: v1 should prioritize one polished loop over feature breadth.

## 5) Game Systems

### Exploration

- Top-down 2D movement across a stylized campus map
- Camera follow behavior
- Collision boundaries for buildings, edges, and blocked paths
- Trigger zones for landmarks and interaction points

### Landmark Interactions

Each landmark should deliver:
- a place cue
- a short narrative or question
- a meaningful but fast response moment
- a reward, score contribution, or growth event

Landmarks should represent a mix of:
- academics
- student life
- belonging and support
- ambition and future opportunities
- campus/city context

### `Swoop` Progression

`Swoop` begins as an egg and grows as the player explores.

Recommended v1 stage progression:
- `egg`
- `hatchling`
- `growing`
- `adult`

Progression should be driven by completed landmark interactions, not by time or randomness.

### Collectibles

Collectibles should reinforce discovery and campus identity.

Possible collectible categories:
- campus keepsakes
- achievement tokens
- place-based icons
- student-life memorabilia

Collectibles are shown in the result recap, but they are not passed to Slate.

### `academic_interest` Resolution

Each landmark interaction contributes weights to one or more academic-interest buckets.

The final game result should resolve to exactly one `academic_interest` outcome in v1.

The scoring model should be:
- deterministic
- simple to tune
- content-driven rather than AI-generated

## 6) Content Model

The game should be built around data-driven content wherever practical.

Core content types:
- `MapScene`
- `LocationTrigger`
- `DialogueEvent`
- `CollectibleItem`
- `SwoopStage`
- `AcademicInterest`
- `ResultMapping`
- `GameSession`

Content should be structured so the team can change:
- landmark placement
- dialogue
- scoring
- collectible rewards
- result copy

without rewriting core systems.

## 7) Technical Approach

The implementation stack for this plan is:
- `Phaser 3` for the game runtime
- `Vite` for development and production builds
- `JavaScript` for v1
- `Tiled` for map authoring
- `HTML + CSS` for overlays and handoff UI
- `GitHub Pages` for deployment

Technical assumptions:
- the game must run fully client-side
- the production output must be a static build
- no backend is required for the first playable slice
- gameplay assets must resolve correctly under a GitHub Pages base path

Recommended runtime structure:
- `src/scenes/` for boot, title, campus, results, and handoff scenes
- `src/systems/` for session state, scoring, progression, and payload creation
- `src/content/` for map, trigger, interaction, and result data
- `src/ui/` for overlays, HUD, and result presentation
- `assets/` for maps, sprites, tilesets, and audio

## 8) Map and Asset Workflow

The campus map should be authored in `Tiled`.

The map workflow for v1 should be:
- create a stylized campus layout
- define walkable and blocked layers
- define spawn points and trigger zones
- export the map as JSON
- load the exported map into Phaser

Asset priorities for v1:
- one map tileset or illustrated map layer
- player sprite
- `Swoop` stage sprites
- collectible icons
- basic UI art

Art does not need to be production-final in the first playable slice, but it must be coherent enough to communicate the concept clearly.

## 9) Slate Handoff

Slate is the final step, not the core of the product.

The game-to-Slate handoff should only include:
- `game_academic_interest`
- `game_version`
- `game_session_id`
- `game_completed_at`

The game must not pass:
- PII
- `swoop_stage`
- collected items
- internal scoring details

Slate should appear only after results, as an optional next step for the player.

## 10) v1 Scope Boundaries

In scope for v1:
- one map
- one short exploration loop
- 5-8 landmark interactions
- one `Swoop` companion lifecycle
- one deterministic result
- GitHub Pages deployment

Out of scope for v1:
- multiple maps
- combat systems
- enemy encounters
- full RPG progression
- open-world campus simulation
- multiplayer
- deep branching storylines
- separate in-state and out-of-state versions
- CRM routing beyond Slate submission

## 11) Delivery Phases

### Phase 1: Foundation

- finalize gameplay and content contracts
- scaffold the Vite + Phaser project
- set up GitHub Pages-compatible build output
- create the runtime folder structure

### Phase 2: Playable Vertical Slice

- implement player movement and camera behavior
- load the first campus map
- add collision and trigger zones
- implement 3-5 landmark interactions
- implement `Swoop` growth logic
- implement basic collectible tracking

### Phase 3: Complete v1 Loop

- expand to 5-8 landmarks
- finalize `academic_interest` scoring
- add result screen and recap
- add Slate payload builder and handoff screen
- tune pacing for 2-5 minute completion

### Phase 4: Polish and Launch Readiness

- mobile tuning
- keyboard and touch support review
- visual polish
- bug fixing
- GitHub Pages deployment verification

## 12) Success Criteria

The v1 plan is successful when:
- the game runs on GitHub Pages without a backend
- a player can complete a full session in 2-5 minutes
- movement, triggers, and progression feel coherent
- `Swoop` visibly grows during play
- a full run resolves one `academic_interest`
- the result screen clearly summarizes the player’s journey
- the Slate handoff payload is valid and contains no PII
- the game feels like exploration, not a disguised form

## 13) Primary Risks

The biggest risks for v1 are:
- overbuilding the game before the core loop is fun
- spending too long on map art before movement and triggers work
- letting dialogue interactions grow too long and break pacing
- making the scoring model too complex to tune quickly
- breaking production asset paths on GitHub Pages

The plan should bias toward a working, playable slice early, then expand content and polish only after the loop is proven.
