# Workflow

## Contents

- [Purpose](#purpose)
- [The workflow is not a single pipeline](#the-workflow-is-not-a-single-pipeline)
- [Story entry modes](#story-entry-modes)
- [Story and Design iteration](#story-and-design-iteration)
- [Storyboard position](#storyboard-position)
- [Approval gates](#approval-gates)
- [From Design to Production](#from-design-to-production)
- [Focused work versus project-wide work](#focused-work-versus-project-wide-work)
- [Work tracking and resumable handoffs](#work-tracking-and-resumable-handoffs)

## Purpose

The Comic Framework supports iterative development. It should not force every project through one rigid sequence.

The framework separates responsibilities while allowing information to move between them repeatedly.

## The workflow is not a single pipeline

A useful high-level view is:

```text
                 ┌─────────────────────────────┐
                 │       STORY DEVELOPMENT     │
                 │ world / character / story   │
                 │ script / storyboard         │
                 └──────────────┬──────────────┘
                                │ constraints
                                ▼
                 ┌─────────────────────────────┐
                 │       DESIGN DEVELOPMENT    │
                 │ style / character / world   │
                 │ references / approval       │
                 └──────────────┬──────────────┘
                                │ approved inputs
                                ▼
                 ┌─────────────────────────────┐
                 │        PRODUCTION           │
                 │           planned           │
                 └─────────────────────────────┘
```

In practice, Story and Design may iterate in both directions. Design can expose a factual question or production constraint, but it must not silently redefine Story canon.

## Story entry modes

`comic-project-standard-v1` supports multiple starting points:

- `world-first`
- `character-first`
- `relationship-first`
- `story-first`
- `mixed`

These modes indicate the current creative entry point, not a permanent project type.

Typical examples:

```text
World idea → World Builder → Character development → Story architecture

Character idea → Character Developer → World and/or story development

Relationship idea → Character Developer → Story and/or world development

Premise → Story Architect → Character and world development
```

Creative outputs remain proposals or inferences until the project's canon policy promotes them.

## Story and Design iteration

Design does not need to wait until the entire story is finished.

Design can begin as soon as the project has enough constraints for the requested task. Examples:

- a character can be visually explored from an accepted role and physical constraints
- a location can be designed from established function, scale and world rules
- a project Style Pack can be developed from existing visual references and narrative tone

The iterative relationship is:

```text
Story constraints ───────→ Design exploration
       ▲                         │
       │                         │ questions / conflicts
       └─────────────────────────┘
```

A question discovered during Design returns to Story as `OPEN`, `INFERENCE`, `PROPOSAL` or `CONFLICT` as appropriate. Design does not settle factual canon on its own.

## Storyboard position

Storyboard direction currently belongs to the Story framework.

Its purpose is to express narrative staging and page/panel intent, including:

- panel sequence
- pacing
- framing
- perspective
- composition intent
- reading flow
- dialogue space

Storyboard work may consume approved visual references, but it does not own the project's visual style or approved character/environment design.

This makes the storyboard an important handoff artifact between Story, Design and later Production without making it a Design authority.

## Approval gates

Two independent approval systems are used.

### Narrative

Only the creator or an explicitly authorized workflow may promote material to `CANON`.

### Design

Only the creator or an explicitly authorized workflow may promote visual work to `APPROVED` or `LOCKED`.

An automated review may recommend a state change but does not grant approval by itself.

## From Design to Production

Production should consume sufficiently stable Story and Design inputs.

Typical inputs are expected to include:

```text
accepted script / storyboard intent
            +
approved or locked visual designs
            +
active style and transformation configuration
            ↓
         production
```

Exact production requirements remain open until the production framework is implemented.

## Focused work versus project-wide work

Do not scan or rewrite the complete project for every small task.

For a focused task, use the smallest source set that establishes the required constraints.

For a broad architectural or project-wide task, inspect the relevant entry points and authoritative sources before making recommendations.

## Work tracking and resumable handoffs

When a project adopts `work-status.md`, use it to find the next action and its source records. After meaningful progress, decisions, pauses or handoffs, update only the relevant work items and evidence links. State the remaining action and dependency clearly, and preserve unrelated concurrent work.

Keep actionable work separate from intentionally open story questions and actual contradictions. Task completion does not grant canon or design approval; a pause does not imply a blocker. The overview introduces no new permission gate and does not authorize automatic continuation or scheduling.

See [Project Work Tracking](work-tracking.md) for the optional convention. It is descriptive integration guidance, not a change to the Story or Design standards.
