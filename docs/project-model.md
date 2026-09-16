# Project Model

## Contents

- [Purpose](#purpose)
- [One comic, one project repository](#one-comic-one-project-repository)
- [Current combined layout](#current-combined-layout)
- [Character profiles and design records](#character-profiles-and-design-records)
- [Project entry points](#project-entry-points)
- [Optional work overview](#optional-work-overview)
- [Authority by layer](#authority-by-layer)
- [Project-specific styles and configuration](#project-specific-styles-and-configuration)
- [Production planning layer](#production-planning-layer)
- [Framework repositories are not project templates](#framework-repositories-are-not-project-templates)

## Purpose

A comic project combines the framework layers in one project repository. Story, design and later production should not be split into independent repositories merely because their reusable frameworks are separate.

## One comic, one project repository

Recommended model:

```text
comic-framework-story   ──────┐
comic-framework-design  ──────┼──→  comic-project
production framework    ──────┘
```

This keeps narrative facts, approved visual decisions and final assets connected to the same project history.

## Current combined layout

A project using the current Story and Design standards may look like:

```text
comic-project/
├── project.md
├── work-status.md          # optional project convention
├── canon/
├── characters/
├── relationships/
├── locations/
├── factions/
├── story/
├── issues/
├── style/
├── archive/
│
├── design-project.md
└── design/
    ├── styles/
    ├── characters/
    ├── environments/
    ├── props/
    ├── references/
    └── archive/
```

The Story layer's `style/` directory is for **narrative and writing conventions** such as dialogue voice and storytelling rules. Visual style belongs under the Design layer.

Projects may intentionally adapt the exact directory layout. Compatibility depends on preserving the framework's responsibilities and source-of-truth rules, not on mechanically creating every optional directory.

## Character profiles and design records

When Story and Design are used together, use matching character IDs and keep one authoritative copy of each asset:

```text
characters/<character-id>/profile.md
design/characters/<character-id>/design.md
design/characters/<character-id>/references/
```

The profile owns narrative identity, biography and canon states. The design record owns visual decisions, reference inventory and design states. Link the profile to the design record and the design record back to the profile. Store visual references and available generation prompts under the Design references directory; do not duplicate them under Story. Story-specific source material may still use `characters/<character-id>/references/`.

For Story-only projects, the local `characters/<character-id>/references/` pattern remains valid. Respect documented project-specific paths; adding the Design layer does not authorize moving existing assets. Optional `characters/README.md` and `design/characters/README.md` indexes can make the records discoverable without creating another source of truth.

Generic body-type studies and ensemble sheets remain design studies; no individual character profile is required until a named character actually exists. Missing references should be explicit, not filled with an unrelated asset or invented original prompt.

When a project author requests harmonization, preserve image contents and narrative/design states, update active links, and document old/new paths. Original prompts and provenance records remain historical evidence; a migration map can resolve their old paths. Optional checksums help verify that a move did not alter an image. An organizational change neither approves a design nor establishes new canon.

Frameworks contain reusable conventions and generic examples. Character properties, institutional hierarchies, project-specific models and concrete artwork belong only in the comic project repository.

## Project entry points

The combined model has Story and Design entry points, plus an opt-in Production planning entry point.

### `project.md`

Narrative/project source of truth and Story-layer configuration.

It may define:

- project identity
- current development entry point
- premise
- canon policy and canon threshold
- story-side paths
- project-specific conventions

### `design-project.md`

Design-layer entry point and active visual configuration.

It may define:

- Story and Design contract compatibility
- active Style Pack or Style Packs
- active Transformation Profile
- design approval policy
- design paths
- project-specific style notes
- open design questions

For project-wide Design tasks, inspect both files when present and relevant.

`design-project.md` must not silently override narrative canon from the Story layer. Likewise, Story-side edits must not silently replace an approved or locked visual design.

## Optional work overview

A project may add `work-status.md` for next actions, pending decisions, handoffs and links to conflicts. Document its adoption in `project.md`. It is a coordination index, not a third source-of-truth entry point and not a required file in either current framework contract.

The domain records retain authority over narrative facts and visual approval. A project-specific conflict index, such as `canon/conflicts.md`, retains its own responsibility; the work overview links to it rather than duplicating its contents.

See [Project Work Tracking](work-tracking.md) for suggested fields, maintenance, pauses and external artifact intake.

## Authority by layer

Use Story/project sources for facts such as:

- who a character is
- what exists in the world
- relationships and history
- required story events
- functional requirements for locations or props
- script and storyboard intent

Use Design sources for visual decisions such as:

- silhouette and proportions
- palette and materials
- visual style
- character sheets
- environment geometry as a visual continuity anchor
- approved visual references
- preservation priorities for transformations

A visual decision that introduces a new factual claim does not become canon merely because it appears in an image.

## Project-specific styles and configuration

Reusable Style Packs may live in `comic-framework-design`, but a comic's own visual identity should normally live in its project repository.

Example:

```text
comic-project/
└── design/
    └── styles/
        └── project-style/
            ├── style.md
            └── references/
```

A framework-level Style Pack can be approved as a reusable resource without being active or approved for a particular comic. Project activation belongs in `design-project.md` or another explicitly documented project-level decision.

## Production planning layer

Projects may opt into `comic-production-standard-v0.1-draft` through `production-project.md`, with issue plans under `production/issues/<issue-id>/production-plan.md`. These records hold format defaults, physical page allocation, panel targets and advertising reservations. They link Story and Design records without replacing them.

The draft template and normative structure live in `comic-framework-production`. Rendering/export paths remain deferred. See [Production Planning](production-planning.md).

## Framework repositories are not project templates

Framework repositories own reusable process logic. A project may copy or adapt their templates, but should not remain structurally coupled to a framework Git repository.

The intended lifecycle is:

```text
framework template
      ↓
initialize project structure
      ↓
project evolves independently
      ↓
framework Skills operate against the project's declared contracts
```
