# Architecture

## Contents

- [Purpose](#purpose)
- [Repository model](#repository-model)
- [Three project layers](#three-project-layers)
- [Source-of-truth model](#source-of-truth-model)
- [Framework contracts](#framework-contracts)
- [Installed Skills versus source Skills](#installed-skills-versus-source-skills)
- [Cross-framework rules](#cross-framework-rules)
- [Normative versus descriptive documentation](#normative-versus-descriptive-documentation)

## Purpose

The Comic Framework is a modular system for developing comics with reusable AI-assisted workflows without mixing generic process logic with the content of a particular comic.

The architecture separates reusable framework modules from comic project repositories.

```text
Reusable framework layer                 Project layer
────────────────────────                 ─────────────
comic-framework-story       ───────┐
comic-framework-design      ───────┼──→  one comic project repository
comic-framework-production  ───────┘     containing project-specific truth
```

`comic-framework-production` is planned but not yet implemented.

## Repository model

The framework family uses one repository per responsibility:

| Repository | Responsibility |
|---|---|
| `comic-framework-story` | Narrative development and narrative consistency |
| `comic-framework-design` | Visual development and visual approval |
| `comic-framework-production` | Final comic production; planned |
| `comic-framework-docs` | Cross-framework architecture and integration documentation |

A comic such as Human Park should use a separate project repository rather than becoming a branch or fork of a framework repository.

Framework repositories contain reusable logic. Project repositories contain project-specific facts, decisions and assets.

## Three project layers

### Story

Story owns narrative truth and narrative intent.

Typical responsibilities include:

- canon and world rules
- characters and relationships
- locations and factions as narrative entities
- story architecture and arcs
- issue outlines and scripts
- narrative and writing style
- storyboard intent, staging, framing and reading flow
- canon and continuity review

The current contract is `comic-project-standard-v1`.

### Design

Design owns visual interpretation and visual approval.

Typical responsibilities include:

- active visual style
- Style Packs
- Transformation Profiles
- character appearance
- environment appearance and spatial visual anchors
- props, machinery, vehicles and related visual objects in v1
- visual references and reference roles
- design exploration, selection, approval and locking
- design consistency review

The current contract is `comic-design-standard-v1`.

### Production

Production will own the creation and assembly of final comic assets from approved story and design inputs.

Expected responsibilities include:

- final panel imagery
- page assembly
- lettering
- production corrections
- export and delivery formats

This layer is intentionally not yet normative. Its repository structure, status model and contract should be defined only when the production framework is designed.

## Source-of-truth model

There are two different kinds of source of truth.

### Reusable process truth

Each framework repository is authoritative for the reusable process and schemas it owns.

Examples:

```text
comic-framework-story
→ comic-project-standard-v1

comic-framework-design
→ comic-design-standard-v1
```

### Project-specific truth

The comic project repository is authoritative for the actual comic.

This includes accepted narrative facts, approved designs, active project configuration and later production assets.

Framework repositories must not absorb project-specific canon merely because a project was used to test them.

## Framework contracts

Contract identifiers are stable compatibility names, not repository names.

Current contracts:

```text
comic-project-standard-v1
comic-design-standard-v1
```

A repository may be renamed without changing its contract identifier.

A new contract identifier should be introduced only for a compatibility-breaking standard revision, not for ordinary documentation improvements or repository naming changes.

## Installed Skills versus source Skills

Editable Skill directories live in the owning framework repository.

```text
Framework Skill source
        ↓
validate / package
        ↓
installed ChatGPT Skill
```

The repository version is the maintainable source. Installed Skill packages are deployment artifacts.

When behavior changes, update the source Skill first and then package and reinstall it.

## Cross-framework rules

The following rules apply across the suite:

1. Do not silently change another layer's authoritative decisions.
2. Surface contradictions instead of silently reconciling them.
3. Keep project-specific material in the comic project repository.
4. Treat creator approval as the gate for canon promotion and for design approval or locking.
5. Use Git as the primary history for text and other practical tracked artifacts.
6. Do not automatically commit, push, archive, overwrite, move or delete project files unless the workflow explicitly authorizes it.
7. Read the smallest relevant source set for focused tasks, but inspect the appropriate project entry points before broad cross-project changes.

## Normative versus descriptive documentation

This repository describes the architecture across modules but does not replace their schemas.

Normative details remain in:

```text
comic-framework-story/schemas/
comic-framework-design/schemas/
```

When a new production framework is created, its normative rules should likewise live in that repository.
