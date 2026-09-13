# Design to Production Handoff

> **Status:** Preliminary architecture note. `comic-framework-production` and its contract do not yet exist.

## Contents

- [Purpose](#purpose)
- [Current boundary](#current-boundary)
- [Expected Design inputs](#expected-design-inputs)
- [Expected Story inputs](#expected-story-inputs)
- [Production responsibilities to validate](#production-responsibilities-to-validate)
- [Rules already established](#rules-already-established)
- [Questions intentionally left open](#questions-intentionally-left-open)

## Purpose

This document records the currently intended Design-to-Production boundary without pretending that a Production standard has already been designed.

It should become an input to `comic-framework-production`, not a substitute for that future framework's normative schemas.

## Current boundary

Design answers:

> What should the accepted visual solution look like?

Production is expected to answer:

> How do we reliably turn accepted Story intent and approved Design into final comic assets?

## Expected Design inputs

A future Production workflow is expected to consume relevant material such as:

- active Style Pack and version
- project-specific style definition
- active Transformation Profile when relevant
- approved or locked character designs
- approved or locked environment designs
- prop and equipment references
- palette, material and rendering anchors
- visual-reference roles
- source-preservation strengths
- continuity anchors
- unresolved visual questions that Production must not guess about

Production should not treat `EXPLORATION` or `SELECTED` Design artifacts as final unless explicitly authorized.

## Expected Story inputs

Production will also need Story-side material such as:

- accepted script or page content
- storyboard or panel intent
- dialogue, captions and SFX content
- scene continuity requirements
- narrative state that affects the rendered panel

Production therefore consumes both Story and Design. Design is not the sole upstream source.

## Production responsibilities to validate

The future framework should test whether Production owns:

- panel generation or rendering
- repeatable character placement and appearance
- environment reuse and camera consistency
- page composition from storyboard intent
- lettering and balloon placement
- correction passes
- production-level continuity checks
- source/provenance tracking for generated assets
- final exports

These are candidate responsibilities, not yet normative assignments.

## Rules already established

Even before Production is implemented, several cross-framework rules are already stable:

1. Production must not silently change narrative canon.
2. Production must not silently redesign approved or locked visual identity.
3. Story text and narrative intent remain Story-owned.
4. Final lettering and page treatment do not belong in the Story `style/` directory.
5. Project-specific final assets belong in the comic project repository or in storage explicitly referenced by that project.
6. Production should surface missing or conflicting upstream information rather than guess silently.

## Questions intentionally left open

The Production framework still needs to decide:

- contract identifier
- production entry-point filename
- production directory structure
- whether Production needs its own artifact status model
- what counts as approval for a final panel or page
- storage strategy for large generated assets
- Git LFS or external asset guidance
- provenance metadata
- revision and re-render policy
- division between automated generation and manual assembly
- exact review Skills

Do not freeze these decisions here before real production testing provides evidence.
