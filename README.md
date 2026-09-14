# comic-framework-docs

Architecture and integration documentation for the modular Comic Framework.

This repository explains how the framework modules fit together, how comic project repositories consume them, and where responsibilities pass from story to design and eventually to production.

It is intentionally **descriptive and cross-framework**. Normative schemas and executable Skill sources stay in their owning framework repositories.

## Framework family

| Repository | Role | Current state |
|---|---|---|
| `comic-framework-story` | Narrative truth, world and character development, story, scripts, storyboards, canon and continuity review | Implemented |
| `comic-framework-design` | Visual style, character and environment design, visual references, source transformations and design approval | Implemented |
| `comic-framework-production` | Final comic asset production, page assembly, lettering and export | Planned |
| `comic-framework-docs` | Cross-framework architecture, boundaries, handoffs and roadmap | This repository |

Project-specific comic content lives outside the framework repositories, for example in a repository such as `dcomics-human-park`.

## Core principle

Keep reusable process logic separate from project-specific truth.

```text
Framework repositories
    define reusable methods, schemas, templates and Skills

Comic project repository
    contains the actual story, canon, designs and later production assets
```

A comic project may use several framework modules at the same time. The project repository remains the source of truth for project-specific material.

## Architecture at a glance

```text
                         Comic project repository
                                  │
                  ┌───────────────┼───────────────┐
                  │               │               │
                  ▼               ▼               ▼
                STORY           DESIGN        PRODUCTION
                  ▲               ▲               ▲
                  │               │               │
    comic-framework-story  comic-framework-design  comic-framework-production
                                                    (planned)
```

The modules are separate because they own different decisions, not because a comic should be split into separate project repositories.

## Current framework contracts

- Story/project layer: **Comic Project Standard v1** — `comic-project-standard-v1`
- Design layer: **Comic Design Standard v1** — `comic-design-standard-v1`
- Production layer: no contract has been defined yet

Repository names and framework-contract identifiers are deliberately independent. Renaming a repository does not require renaming an established contract.

## Documentation map

- [`docs/architecture.md`](docs/architecture.md) — suite architecture and source-of-truth model
- [`docs/architecture-decisions.md`](docs/architecture-decisions.md) — major architectural choices and their rationale
- [`docs/project-model.md`](docs/project-model.md) — how one comic project combines the layers
- [`docs/workflow.md`](docs/workflow.md) — non-linear end-to-end development flow
- [`docs/work-tracking.md`](docs/work-tracking.md) — optional project work overview, open decisions, conflict links and resumable handoffs
- [`docs/framework-boundaries.md`](docs/framework-boundaries.md) — ownership and scope boundaries
- [`docs/status-models.md`](docs/status-models.md) — canon and design status axes
- [`docs/versioning.md`](docs/versioning.md) — repository, contract and artifact versioning guidance
- [`docs/roadmap.md`](docs/roadmap.md) — current implementation state and next phases
- [`docs/handoffs/story-to-design.md`](docs/handoffs/story-to-design.md) — story/design interface
- [`docs/handoffs/design-to-production.md`](docs/handoffs/design-to-production.md) — preliminary design/production interface

## Normative source rule

This repository should not duplicate detailed schemas from the framework repositories.

When this documentation and a normative framework schema disagree, the owning framework repository wins for that contract. Update this documentation afterward so that it describes the current architecture again.

## Current reference repositories

- `comic-framework-story` — <https://github.com/piodornis/comic-framework-story>
- `comic-framework-design` — <https://github.com/piodornis/comic-framework-design>

Add `comic-framework-production` here only after that repository and its contract actually exist.
