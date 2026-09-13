# Versioning

## Contents

- [Purpose](#purpose)
- [Three versioning scopes](#three-versioning-scopes)
- [Framework contract identifiers](#framework-contract-identifiers)
- [Repository versions](#repository-versions)
- [Reusable resource versions](#reusable-resource-versions)
- [Project artifact versions](#project-artifact-versions)
- [Breaking changes](#breaking-changes)
- [Repository renames](#repository-renames)
- [Archives versus Git history](#archives-versus-git-history)

## Purpose

The framework uses several kinds of versioning. Keeping them separate prevents repository names, framework contracts and project artifact revisions from becoming accidentally coupled.

## Three versioning scopes

```text
Framework contract
→ compatibility rules, e.g. comic-design-standard-v1

Repository history
→ Git commits and optional release tags

Project/resource artifact version
→ a Style Pack version, character sheet revision, script revision, etc.
```

These scopes may evolve independently.

## Framework contract identifiers

Current identifiers:

- `comic-project-standard-v1`
- `comic-design-standard-v1`

Treat them as compatibility contracts, not marketing or repository names.

A contract identifier should remain stable while compatible projects and Skills can still follow the same required behavior and structure.

## Repository versions

Git is the primary history for framework source repositories.

Use commits to record normal evolution. Optional Git tags or releases may be introduced when a stable checkpoint should be easy to reference.

A repository release does not automatically create a new framework contract version.

For example, several tagged releases may all implement `comic-design-standard-v1`.

## Reusable resource versions

Reusable resources may have their own versions when useful.

Example:

```text
Style ID: franco-belgian-vivid
Style version: 1.0
Framework: comic-design-standard-v1
```

A Style Pack version tracks changes in that visual resource, not the entire Design framework.

Transformation Profiles may use a similar independent versioning approach when versioning becomes useful.

## Project artifact versions

Project files should rely primarily on Git history.

Use explicit artifact versions or archived snapshots when they materially help the creative workflow, for example:

- a major character redesign
- a substantially replaced environment sheet
- a discarded but valuable story branch
- a visual artifact that needs human-browsable provenance

Do not create a new archived file for every minor correction.

## Breaking changes

Introduce a new framework contract version only when the compatibility rules change in a way that existing Skills or projects cannot safely treat as the same standard.

Examples may include:

- incompatible source-of-truth rules
- required structural changes that old Skills cannot interpret safely
- changed status semantics
- changed authority or approval rules

Documentation corrections, clarifications and repository renames do not by themselves require a new contract version.

## Repository renames

Repository names and contract identifiers are deliberately independent.

Example:

```text
Repository:
comic-framework-story

Contract:
comic-project-standard-v1
```

Renaming the repository does not require changing the contract.

## Archives versus Git history

Both Story and Design use Git as primary history and archives as supplementary historical storage.

General rule:

```text
ordinary evolution → Git history
major useful superseded snapshot → archive when appropriate
```

Archiving is not the same as changing a status:

- Story archive material is historical, not current canon by default.
- Design `SUPERSEDED` is a lifecycle state; `design/archive/` is a storage location.

Destructive or archival actions should not happen silently.
