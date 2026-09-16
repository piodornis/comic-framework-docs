# Roadmap

## Contents

- [Current baseline](#current-baseline)
- [Phase 1 - Story framework](#phase-1---story-framework)
- [Phase 2 - Design framework](#phase-2---design-framework)
- [Phase 3 - Cross-framework documentation](#phase-3---cross-framework-documentation)
- [Phase 4 - Real-project integration testing](#phase-4---real-project-integration-testing)
- [Phase 5 - Production framework](#phase-5---production-framework)
- [Future expansion rule](#future-expansion-rule)

## Current baseline

The architecture currently consists of two implemented framework modules, one documentation repository and one draft production planning module.

```text
comic-framework-story       implemented
comic-framework-design      implemented
comic-framework-docs        current documentation layer
comic-framework-production  planning foundation v0.1 draft
```

## Phase 1 - Story framework

Implemented core Skills:

- `comic-character-developer`
- `comic-world-builder`
- `comic-canon-guardian`
- `comic-story-architect`
- `comic-issue-writer`
- `comic-storyboard-director`
- `comic-continuity-reviewer`

Current contract:

```text
comic-project-standard-v1
```

## Phase 2 - Design framework

Implemented core Skills:

- `comic-style-director`
- `comic-character-designer`
- `comic-environment-designer`
- `comic-design-reviewer`

Current reusable visual resources include:

```text
Style Pack:
franco-belgian-vivid

Transformation Profile:
photo-to-comic
```

Current contract:

```text
comic-design-standard-v1
```

## Phase 3 - Cross-framework documentation

Goals:

- document the suite architecture
- define framework boundaries clearly
- document the combined project model
- explain independent status systems
- record Story-to-Design and preliminary Design-to-Production handoffs
- keep normative details in the owning framework repositories

This repository fulfills that role.

## Phase 4 - Real-project integration testing

Use one or more actual comic projects to test the combined framework.

The first useful tests should cover:

- Story sources consumed by Design without accidental canon changes
- project-specific visual style development
- refinement of existing character designs rather than redesign from scratch
- visual reference roles and preservation strengths
- character and environment consistency
- Story/Design conflict reporting
- creator approval gates
- usefulness of current file structures under real iteration

Human Park is a suitable integration project, but its canon and visual identity remain project-specific and must not be embedded into reusable framework logic.

## Phase 5 - Production framework

The initial `comic-framework-production` foundation now addresses the supplied concrete requirements: configurable format, page count, panel defaults with per-page exceptions and advertising reservations. It includes draft schemas, a project template and worked 24-page and 32-page examples. The 24-page example includes two full interior ads; prose-first intake distinguishes provisional budgets from accepted Story pages. No executable Production Skills or rendering/export implementation exist yet.

Next: exercise the plan on one real issue, resolve physical-slot versus Story-page mapping, and then implement `comic-production-planner`. See [Production Planning](production-planning.md).

Remaining implementation topics include:

- production entry point
- production artifact status and approval model, if needed
- panel-generation workflow
- page assembly
- lettering
- correction passes
- asset provenance
- repeatable character/environment rendering
- export formats
- Design-to-Production and Story-to-Production dependencies

Do not prematurely freeze these decisions in the documentation repository.

## Future expansion rule

Prefer a small set of broad, well-defined Skills over speculative specialization.

Split responsibilities such as props, vehicles, costumes, creatures or specialized production tasks into dedicated Skills only when repeated real-world use shows that the existing ownership model is insufficient.
