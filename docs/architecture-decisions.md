# Architecture Decisions

## Contents

- [Purpose](#purpose)
- [One project repository per comic](#one-project-repository-per-comic)
- [Separate framework modules by responsibility](#separate-framework-modules-by-responsibility)
- [Keep project truth outside framework repositories](#keep-project-truth-outside-framework-repositories)
- [Keep contract identifiers independent from repository names](#keep-contract-identifiers-independent-from-repository-names)
- [Keep Story and Design status models independent](#keep-story-and-design-status-models-independent)
- [Keep storyboard direction in Story](#keep-storyboard-direction-in-story)
- [Separate Style Packs from Transformation Profiles](#separate-style-packs-from-transformation-profiles)
- [Require explicit creator approval for authoritative promotion](#require-explicit-creator-approval-for-authoritative-promotion)
- [Defer Production rules until the Production framework exists](#defer-production-rules-until-the-production-framework-exists)
- [Decision maintenance](#decision-maintenance)

## Purpose

This document records the main architectural choices behind the Comic Framework and the reasons for them.

It is descriptive, not normative. The owning framework repositories remain authoritative for their contracts and schemas. The goal here is to preserve design intent so future changes can distinguish deliberate architecture from accidental convention.

## One project repository per comic

**Decision:** Keep Story, Design and later Production data for one comic in the same project repository.

**Reason:** Narrative facts, approved visual decisions and final production assets describe the same creative work and should share one project history. Splitting them into separate repositories would create cross-repository synchronization problems and competing sources of truth.

Framework modules remain separate because they define reusable responsibilities, not because a comic should be physically split by discipline.

## Separate framework modules by responsibility

**Decision:** Maintain separate framework repositories for Story, Design and Production.

**Reason:** Each layer owns a different class of decisions:

- Story owns narrative truth and narrative intent.
- Design owns visual interpretation and visual approval.
- Production will own reliable realization of final comic assets.

This separation reduces scope creep and allows each framework to evolve without absorbing unrelated rules.

## Keep project truth outside framework repositories

**Decision:** Store project-specific canon, designs and production assets only in the comic project repository.

**Reason:** Framework repositories must remain reusable across unrelated comics. A project may be used to test a framework, but its characters, lore, visual identity or production artifacts must not become generic framework defaults.

Templates may initialize a project, but the resulting project evolves independently.

## Keep contract identifiers independent from repository names

**Decision:** Treat compatibility identifiers such as `comic-project-standard-v1` and `comic-design-standard-v1` as stable contracts rather than repository names.

**Reason:** Repository naming is organizational and may change without changing the actual file contract or workflow semantics. Renaming a repository should therefore not force a compatibility-breaking contract revision.

Introduce a new contract identifier only when compatibility itself changes.

## Keep Story and Design status models independent

**Decision:** Use separate status axes for narrative truth and visual design approval.

**Reason:** A fact can be canon while its visual implementation is still exploratory, and an approved visual asset can still contain a narrative implication that has not been accepted as canon.

Current axes are:

```text
Narrative / canon                 Design approval
─────────────────                 ───────────────
CANON                             EXPLORATION
INFERENCE                         SELECTED
PROPOSAL                          APPROVED
CONFLICT                          LOCKED
OPEN                              SUPERSEDED
```

Neither axis should silently imply a state change on the other.

## Keep storyboard direction in Story

**Decision:** Keep storyboard direction in the Story framework.

**Reason:** Storyboarding primarily defines narrative staging, page and panel rhythm, framing, composition intent and reading flow. These decisions translate a script into sequential storytelling and therefore belong with narrative intent.

The Storyboard Director may consume approved Design references, but it does not define the project's visual style. Final visual realization belongs downstream.

## Separate Style Packs from Transformation Profiles

**Decision:** Model visual aesthetics and source-preservation behavior as independent concepts.

**Reason:** A Style Pack answers what an accepted visual result should look and feel like. A Transformation Profile answers which properties of source material must be preserved or may change.

Keeping them independent allows combinations such as:

```text
photo-to-comic + franco-belgian-vivid
photo-to-comic + manga-clean
photo-to-comic + project-specific-style
```

This avoids duplicating source-preservation rules inside every visual style.

## Require explicit creator approval for authoritative promotion

**Decision:** Do not let framework Skills silently promote proposals, inferences, explorations or selections into authoritative states.

**Reason:** Canon and approved visual identity are creative decisions. Skills may analyze, propose, compare and review, but promotion to authoritative states requires explicit creator approval or an explicitly authorized workflow.

This applies especially to:

- narrative promotion to `CANON`
- design promotion to `APPROVED`
- design promotion to `LOCKED`

## Defer Production rules until the Production framework exists

**Decision:** Document Production only at the boundary level until `comic-framework-production` is designed.

**Reason:** Prematurely standardizing directories, states or contracts would turn speculation into accidental architecture. The current documentation may describe expected Production responsibilities, but those descriptions remain provisional until the Production framework defines its own normative contract.

## Decision maintenance

Add or revise an entry when a cross-framework architectural choice changes materially.

Do not use this file to duplicate detailed schemas or operating procedures. Record the decision, its rationale and the boundary it establishes; keep normative implementation details in the owning framework repository.
