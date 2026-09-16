# Framework Boundaries

## Contents

- [Purpose](#purpose)
- [Ownership table](#ownership-table)
- [Story boundary](#story-boundary)
- [Design boundary](#design-boundary)
- [Production boundary](#production-boundary)
- [Shared concerns](#shared-concerns)
- [Common boundary questions](#common-boundary-questions)

## Purpose

Clear ownership prevents duplicate sources of truth and avoids one Skill silently changing another layer's decisions.

A layer may **consume** information owned elsewhere without becoming its authority.

## Ownership table

| Concern | Owner | Notes |
|---|---|---|
| Narrative canon | Story/project layer | Uses `comic-project-standard-v1` |
| Character biography, motivation and role | Story/project layer | Visual appearance is Design |
| Relationships and history | Story/project layer | Design may express them visually |
| World rules and fictional technology rules | Story/project layer | Design interprets their appearance |
| Story arcs and issue structure | Story | Design may expose feasibility questions |
| Script dialogue, captions and SFX intent | Story | Final lettering is Production |
| Storyboard staging and reading flow | Story | May consume Design references |
| Narrative/writing style | Story | Lives under Story `style/` |
| Visual style | Design | May use reusable or project-specific Style Packs |
| Character visual identity | Design | Must respect narrative facts |
| Environment visual identity and geometry | Design | Functional facts remain Story-owned |
| Props, machinery, vehicles, costumes and creatures in v1 | Design | Character or Environment Designer depending on context |
| Source-image preservation rules | Design | Transformation Profiles |
| Visual approval state | Design | Independent from canon state |
| Format, page budget and ad reservations | Production planning | Draft contract; Story retains pacing and panel intent |
| Panel defaults and per-page overrides | Production planning with Story reconciliation | Targets, not automatic rewrites of storyboards |
| Final panel rendering | Production, planned | Not yet standardized |
| Page assembly | Production, planned | Not yet standardized |
| Lettering and final page treatment | Production, planned | Story supplies textual/narrative intent |
| Export formats | Production, planned | Not yet standardized |

## Story boundary

Story answers questions such as:

> What is true in this fictional project?

> What happens, to whom, where and why?

> What should a scene or page communicate narratively?

Story may include visual facts when they are factual canon, for example a required scar, uniform, device or location feature. It does not own the complete visual implementation of those facts.

`style/` in the Story project structure is reserved for narrative and writing conventions. Visual-language rules belong to Design.

## Design boundary

Design answers questions such as:

> What should the accepted visual solution look like?

> Which visual anchors must stay consistent?

> How should source material be preserved or transformed?

Design may propose new visual ideas, but an idea that changes narrative truth remains subject to the Story canon process.

Design should report downstream production requirements without silently taking over final page production.

## Production boundary

Production is expected to answer questions such as:

> How do we turn accepted Story intent and approved Design into final comic assets reliably?

Likely responsibilities include rendering, assembly, lettering, correction passes and exports.

The planning boundary is defined in the Production draft schemas. Rendering, assembly and export remain future scope. Physical slot allocation belongs to Production; changes to narrative panel intent return to Story. See [Production Planning](production-planning.md).

## Shared concerns

Some concerns cross layers but still need a clear owner.

### Continuity

Story's Continuity Reviewer checks concrete narrative and visual implementation continuity across scenes, pages and issues.

Design's Design Reviewer checks visual-system consistency, reference fidelity, design cohesion and approval readiness.

The two reviewers may identify related problems from different perspectives.

### Storyboards

Storyboards are owned by Story because they encode narrative staging and reading flow. They may depend on approved Design information and later act as a Production input.

### Props

A prop's existence, function and story significance are Story facts. Its approved appearance is Design. Its final rendered instance in a panel will be Production.

### Environments

A location's narrative function and factual constraints are Story-owned. Its approved visual geometry, materials, palette and visual continuity anchors are Design-owned.

## Common boundary questions

**Does Design decide that a character now has a prosthetic arm?**  
Only if that fact is already canon or the Story process accepts it. Otherwise it is a proposal or conflict, not silent canon.

**Does Story decide the exact surface material and rendering treatment of the arm?**  
Not normally. Story may constrain facts; Design owns the visual solution.

**Does the Storyboard Director define the project art style?**  
No. It may use existing Design references while planning staging and composition.

**Does an approved reusable Style Pack automatically become the project's style?**  
No. Framework-level approval means the pack is accepted as a reusable resource. The project still selects or approves its own use of that pack.

**Who owns lettering?**  
Story owns the text and narrative intent. Final lettering and page treatment are reserved for the future Production layer.
