# Story to Design Handoff

## Contents

- [Purpose](#purpose)
- [Entry points](#entry-points)
- [What Story provides](#what-story-provides)
- [What Design may decide](#what-design-may-decide)
- [What Design must not decide silently](#what-design-must-not-decide-silently)
- [What Design returns](#what-design-returns)
- [Conflict handling](#conflict-handling)
- [Minimum handoff for focused design work](#minimum-handoff-for-focused-design-work)
- [Example](#example)

## Purpose

The Story-to-Design handoff turns narrative constraints into visual development without transferring authority over narrative canon to the Design layer.

The handoff can happen early and repeatedly. A complete script is not required for every Design task.

## Entry points

When both exist:

```text
project.md
→ narrative/project source of truth

design-project.md
→ active Design configuration and Design-layer source of truth
```

For broad Design work, inspect both before deeper source files.

For a focused task, read the smallest additional set needed to establish constraints.

## What Story provides

Relevant Story inputs may include:

- character identity and role
- established physical facts
- relationships and status cues that should be visually legible
- world rules
- technology and functional constraints
- location function and spatial requirements
- recurring props or equipment
- story tone
- issue or scene requirements
- script
- storyboard intent
- explicit visual canon already established as fact
- open questions and known conflicts

Story material provides constraints, not necessarily finished visual solutions.

## What Design may decide

Within those constraints, Design may develop:

- silhouettes and proportions
- face/display language
- costume or shell treatment
- materials
- palette
- linework and rendering language
- visual environment geometry
- visual continuity anchors
- visual versions of props, machinery and vehicles
- Style Packs
- Transformation Profile usage
- visual reference roles

These outputs follow the Design approval lifecycle.

## What Design must not decide silently

Design must not silently establish new narrative facts such as:

- a new injury or body modification with story consequences
- a previously nonexistent faction symbol with narrative meaning
- a new technology capability
- a changed relationship
- a location function that contradicts Story
- a prop that changes what a scene can accomplish

Such discoveries should return to the narrative process as `PROPOSAL`, `INFERENCE`, `OPEN` or `CONFLICT`.

## What Design returns

A useful Design result may include:

- selected, approved or locked visual design records
- project-specific Style Pack
- active reusable Style Pack selection
- active Transformation Profile selection
- character sheets
- environment sheets
- prop/equipment references
- preservation anchors
- visual continuity anchors
- design-review findings
- unresolved questions that need Story decisions

These outputs belong in the comic project repository, not in the reusable Story framework.

## Conflict handling

If Design discovers that a desired visual direction conflicts with Story canon:

1. identify the visual direction
2. identify the conflicting Story source
3. classify the factual problem as `CONFLICT`
4. keep the visual artifact at an appropriate Design state
5. present resolution options without silently choosing one
6. update Story or Design only after the project decision

## Minimum handoff for focused design work

A focused Design task can start when enough constraints exist to avoid arbitrary invention.

For example, a character exploration may require only:

- character identity
- relevant physical canon
- role and personality cues that matter visually
- existing visual references, if any
- active project style information, if any
- explicit preservation requirements

Do not require the entire project repository when the focused task does not depend on it.

## Example

```text
Story:
CANON — Character A is an old maintenance robot.
CANON — It carries a visible unit identifier.
OPEN — Exact surface material has not been established.

Design:
EXPLORATION — three surface-material directions
SELECTED — weathered painted metal

Result:
The selected material does not become narrative canon merely because it was selected visually.
If the material matters as a factual world constraint, Story can explicitly accept it.
```
