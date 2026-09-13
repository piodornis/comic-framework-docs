# Project Model

## Contents

- [Purpose](#purpose)
- [One comic, one project repository](#one-comic-one-project-repository)
- [Current combined layout](#current-combined-layout)
- [Project entry points](#project-entry-points)
- [Authority by layer](#authority-by-layer)
- [Project-specific styles and configuration](#project-specific-styles-and-configuration)
- [Future production layer](#future-production-layer)
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

## Project entry points

The current combined model has two complementary entry points.

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

## Future production layer

Production has not yet been standardized.

A future project may add a production entry point and directories for panels, pages, lettering, assets or exports, but those paths are **illustrative only** until `comic-framework-production` defines its contract.

Do not treat a speculative production tree in this documentation as a current standard.

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
