# Status Models

## Contents

- [Purpose](#purpose)
- [Narrative canon states](#narrative-canon-states)
- [Design states](#design-states)
- [The axes are independent](#the-axes-are-independent)
- [Proposal versus exploration](#proposal-versus-exploration)
- [Approval authority](#approval-authority)
- [Conflicts across layers](#conflicts-across-layers)
- [Framework-level Style Pack approval](#framework-level-style-pack-approval)
- [Work-tracking labels](#work-tracking-labels)
- [Production status](#production-status)

## Purpose

The Story and Design frameworks use separate status systems because factual truth and visual approval answer different questions.

Do not collapse them into one combined lifecycle.

## Narrative canon states

`comic-project-standard-v1` defines five primary canon states:

| State | Meaning |
|---|---|
| `CANON` | Confirmed project fact |
| `INFERENCE` | Logical conclusion supported by canon but not explicitly confirmed |
| `PROPOSAL` | New creative suggestion not yet accepted |
| `CONFLICT` | Contradiction requiring resolution |
| `OPEN` | Intentionally unresolved question or decision |

Only the creator or an explicitly authorized project workflow may promote content to `CANON`.

Skills may create proposals, derive inferences or identify conflicts, but they must not silently treat those states as established fact.

## Design states

`comic-design-standard-v1` defines five visual approval states:

| State | Meaning |
|---|---|
| `EXPLORATION` | Uncommitted sketches, tests, variants or generated directions |
| `SELECTED` | Chosen direction for further development, not yet approved |
| `APPROVED` | Creator-accepted current visual solution |
| `LOCKED` | Design should not change without explicit authorization |
| `SUPERSEDED` | Older design replaced by a newer active solution |

Recommended progression:

```text
EXPLORATION
    ↓
SELECTED
    ↓
APPROVED
    ↓
LOCKED
```

A prior visual state may become `SUPERSEDED` when replaced.

## The axes are independent

A subject can have one narrative state and a different design state.

Examples:

```text
Character role
Canon state: CANON

Character appearance
Design state: EXPLORATION
```

or:

```text
Vehicle existence
Canon state: PROPOSAL

Concept image
Design state: SELECTED
```

The second example does not make the vehicle canon. A selected design can still visualize a narrative proposal.

## Proposal versus exploration

These terms are intentionally different.

`PROPOSAL` asks:

> Is this factual or narrative idea accepted as project truth?

`EXPLORATION` asks:

> Is this visual solution accepted as the design?

A newly generated character outfit can therefore be:

```text
Narrative status of the outfit requirement: PROPOSAL
Visual artifact status: EXPLORATION
```

## Approval authority

The framework uses explicit creator gates.

- `CANON` promotion requires creator approval or an explicitly authorized workflow.
- `APPROVED` and `LOCKED` design states require creator approval or an explicitly authorized workflow.
- Review Skills may recommend decisions but do not grant them automatically.

## Conflicts across layers

If a visual direction contradicts established narrative canon, do not solve the contradiction by silently editing the design or the canon.

Report the factual issue as `CONFLICT`, identify the affected design, and let the project decide whether Story or Design should change.

Likewise, a Story revision that invalidates an approved or locked design should surface the downstream design impact explicitly.

## Framework-level Style Pack approval

A reusable Style Pack may itself be `APPROVED` inside `comic-framework-design`.

That approval means:

> This Style Pack definition is accepted as a reusable framework resource.

It does **not** mean:

- every comic project uses it
- the style is active in a project
- project-specific designs made with it are automatically approved

A project must explicitly select or approve its own use of the Style Pack through its Design layer.

## Work-tracking labels

An optional project `work-status.md` may use local labels such as ready, in progress, deferred, awaiting decision or done. They describe work progress, not factual truth or artifact approval, and do not define an additional framework lifecycle.

A completed task may deliver an `EXPLORATION` or `PROPOSAL`. An intentional `OPEN` mystery need not be a blocker. Marking work done does not promote a design to `APPROVED` or a story statement to `CANON`.

See [Project Work Tracking](work-tracking.md) for coordination and handoff guidance.

## Production status

No Production status model has been defined yet.

Do not reuse Design states automatically for Production artifacts unless the future Production framework explicitly chooses to do so.
