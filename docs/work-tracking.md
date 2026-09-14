# Project Work Tracking

## Scope and compatibility

A comic project may adopt a root-level `work-status.md` as an optional cross-layer work overview. It helps creators and Skills resume work without reconstructing every conversation.

This is a **descriptive integration convention**, not a new required file in `comic-project-standard-v1` or `comic-design-standard-v1`. It does not modify either normative schema, install Skill behavior, create a Production contract or require a migration. Projects adopt and document it explicitly in `project.md`; projects with an existing equivalent may keep their layout.

Project-specific work belongs in the comic project repository. This framework documentation describes the method; it must not become a live backlog for any individual comic.

## Responsibilities and authority

| Record | Responsibility |
|---|---|
| `project.md` | Project identity, narrative policy, conventions and Story entry point |
| `design-project.md` | Active visual configuration and Design entry point |
| `work-status.md`, if adopted | Next actions, pending decisions, dependencies, handoffs and links to current records |
| Domain records | Authoritative facts, designs, detailed open questions and decisions |
| Conflict index, if adopted | Links to unresolved/resolved contradictions and their full analyses |

`work-status.md` is a navigation and coordination index. It does not override a canon file, an approved design, a current environment record or a creator decision. If the summary is stale, inspect the authoritative sources and correct the summary. Report an actual unresolved source disagreement rather than silently resolving it.

For focused work, use the index to locate relevant records; it is not a reason to scan the entire project mechanically.

## Distinguish three kinds of open material

1. **Work to perform:** a concrete next action with an expected result, owner role and source.
2. **Decision or intentional unknown:** a question that may need a creator choice, or may deliberately remain unresolved. Narrative `OPEN` is not automatically a task to solve.
3. **Contradiction:** incompatible claims or designs requiring investigation or resolution. Link the actual report; do not copy its full analysis into the work overview.

Some projects use `canon/conflicts.md` as their central conflict index. That path is a project convention, not a universal required file. Other projects may use another documented index. Design reviews may also contain open geometric findings; missing measurements or exploratory alternatives are not automatically canon conflicts.

## Suggested contents

Keep the overview short enough to resume from:

- last reviewed date and scope;
- one concrete recommended next step;
- active or pending work with stable IDs;
- creator decisions and intentionally deferred questions;
- links to conflicts and relevant reviews;
- artifacts awaiting repository intake, if any;
- a small recent-completion section with result links.

A task row can record **ID, work state, next action/result, responsible role, source, dependency or decision needed**. Roles identify responsibility; listing a Skill does not spawn an agent or assign a running task. Use the project's language and terminology.

Avoid duplicating every `OPEN` field across the repository. Summarize the items needed for coordination and link to the rest.

## Work state is not artifact approval

Projects may use ordinary work labels such as “ready”, “in progress”, “awaiting decision”, “deferred”, “blocked” and “done”. These are optional local coordination labels, **not another framework approval lifecycle**.

- A completed exploration can remain `EXPLORATION`.
- A completed writing task can still produce a `PROPOSAL`.
- A `SELECTED` design may still need geometry work.
- An intentional mystery can remain `OPEN` without blocking unrelated work.
- A pause does not mean “blocked”; identify a real missing prerequisite when using that label.

Only describe work as in progress when it actually is. A task row, a completion checkbox or a handoff never promotes content to `CANON`, `APPROVED` or `LOCKED`. It also does not authorize new work, publication, file replacement, scheduling, commits or pushes.

See [Status Models](status-models.md) for the actual narrative and design status systems.

## Maintenance and handoff cycle

When this convention is adopted:

1. **Resume:** read the project entry points as appropriate, identify the relevant work item, then verify its source records and current file state. Existing creator authorization still applies; a status file does not introduce a separate approval step.
2. **Work:** perform the requested action in its owning layer. Keep canon questions and visual approval independent.
3. **Update:** after meaningful progress or an actual decision, update the domain record when authorized and revise the corresponding work row. Preserve the exact scope of partial approvals.
4. **Pause or hand off:** state what is complete, what remains, the next concrete action and any real dependency. Link the current artifact and its version. Do not leave idle work marked “in progress”.
5. **Complete:** record the result and evidence link, retain stable IDs and keep only useful recent history. Git remains the primary history; do not automatically archive or commit.

If multiple contributors work concurrently, re-read the affected file before writing, preserve unrelated changes and edit only the relevant rows. A new handoff should replace stale next-step wording rather than append contradictory instructions indefinitely.

For a conflict, update the owning report and the project's conflict index when authorized, then link them from the work overview. For an intentionally open story question, preserve it in Story and record only when it next needs attention.

## Artifacts outside the repository

Explorations may temporarily live in a task output directory or explicitly referenced storage. Record the artifact version, location, reference role, creator decision and its scope, and whether project intake is pending.

Prefer repo-relative links after intake. Absolute local paths may be used temporarily to make a handoff recoverable, but mark them as machine-local and nonportable. Never include credentials or access tokens. A missing external file is a retrieval problem, not permission to reconstruct its content or approval from memory.

When an intake task is performed, preserve reference provenance and approval history, update the authoritative project design records and active configuration as appropriate, then replace temporary links. A work overview must not silently turn external drafts into approved project assets. Do not migrate artifacts merely because the index exists.

## Minimal illustrative example

```markdown
# Project — Work Status

Last reviewed: YYYY-MM-DD

## Next step
W-01: Revise the location plan using the accepted doorway position.

## Work
| ID | Work state | Next action / result | Role | Source / dependency |
|---|---|---|---|---|
| W-01 | Ready | Create plan v2; preserve v1. | Environment Designer | Current location record and plan v1 |
| W-02 | After W-01 | Review circulation before generating reverse views. | Creator / Environment Designer | Plan v2 |

## Decisions and intentional unknowns
- D-01: Earlier use of the location remains OPEN in the Story record.

## Conflicts
- Link to the project's conflict index and the relevant full report.

## Recent completion
- E-01: Entrance direction selected; link to the design record and image.
```

The example is illustrative. It does not define a new template contract, require these exact labels or imply that a complete project has only these tasks.

## Adoption checklist

- Document the optional overview and its update convention in `project.md`.
- Link to domain records and the existing conflict index.
- Separate work completion from narrative and visual status.
- Give each actionable item a concrete next step and an evidence/source link.
- Keep deferred mysteries distinct from blocked work.
- Preserve creator decisions, concurrent changes and artifact provenance.

Related integration guidance: [Project Model](project-model.md), [Workflow](workflow.md), [Framework Boundaries](framework-boundaries.md), [Story to Design](handoffs/story-to-design.md).
