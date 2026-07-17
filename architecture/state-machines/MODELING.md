# State Machine (Lifecycle) Modeling

The methodology for modeling **lifecycles** — how a single entity's state changes over its life. Entry
document for [`state-machines/`](README.md) (frozen README remains the contract). It provides Dynamic
(lifecycle) views of the [C4 view model](../c4/MODELING.md) (AD-0010).

## Overview
State-machine modeling describes the states an entity can be in, the transitions between them, the
events and guards that trigger transitions, the actions transitions perform, and the terminal states
where the lifecycle ends. The entities and their runtime state are owned by
[07 — Runtime Platform](../../handbook/07-runtime-platform/CHAPTER.md) (and domain aggregates by
[05 — Domain-Driven Design](../../handbook/05-domain-driven-design/CHAPTER.md)); this module owns the
modeling method.

## Purpose
To make an entity's lifecycle explicit and complete — every state reachable, every transition guarded,
every terminal state defined — so lifecycle behavior is correct by construction and reviewable.

## Scope
**In scope:** modeling states, transitions, guards, events, actions, and terminal states for a single
entity's lifecycle. **Out of scope:** multi-participant interactions
([`sequences/`](../sequences/MODELING.md)) and the execution orchestration
([`runtime/`](../runtime/MODELING.md)).

## When to prefer a state machine (vs a sequence)
Prefer a **state machine** when modeling *the lifecycle of one entity* — when the same entity moves
through distinct states and its allowed transitions and terminal conditions matter. Prefer a
**[sequence](../sequences/MODELING.md)** when modeling *how several participants interact over one
scenario*. Rule of thumb: lifecycle of one thing → state machine; conversation among many → sequence.

## Principles
Model one entity's lifecycle per machine; make every state reachable and every terminal state
explicit; guard every transition; keep the machine deterministic (no ambiguous transitions).

## Modeling Process
1. **Entity & states** — identify the entity and enumerate its states.
2. **Transitions** — model the allowed transitions between states.
3. **Events & guards** — attach the triggering event and the guard condition to each transition.
4. **Actions** — model the action performed on transition (or on entry/exit) where relevant.
5. **Terminal states** — define the states where the lifecycle ends.
6. **Completeness** — verify every state is reachable and no state is a dead end unless terminal.

## Guidelines & Notation
- One entity per machine; compose or nest rather than merging unrelated lifecycles.
- Every transition has an event and, where needed, a guard; no unguarded ambiguous transitions.
- Author as diagram-as-code state diagrams. Name states and events by meaning; name no technology.

## Views & Artifacts
- **State model** — states and transitions.
- **Transition table** — event, guard, and action per transition (where a table is clearer than the
  diagram).
- **Terminal-state set** — the defined end states.

## Patterns & Anti-patterns
**Patterns:** explicit terminal states; guarded transitions; hierarchical/nested states for
complexity; a transition table alongside the diagram. **Anti-patterns:** unreachable states;
non-terminal dead ends; ambiguous (unguarded, overlapping) transitions; using a state machine to model
a multi-party interaction (use a sequence); naming a technology.

## Review Checklist & Quality Criteria
- [ ] Every state is reachable; every non-terminal state has an exit.
- [ ] Terminal states are explicitly defined.
- [ ] Every transition has an event and, where needed, a guard.
- [ ] Transitions are unambiguous (deterministic).
- [ ] The machine models one entity's lifecycle; a sequence would not have been better.
- [ ] Naming is technology-neutral.

## Cross-Module Integration
- **Upstream:** [`runtime/`](../runtime/MODELING.md) (runtime lifecycle it details),
  [`event-storming/`](../event-storming/MODELING.md) (aggregate lifecycles),
  [`runtime` specifications](../../specifications/runtime/).
- **Downstream:** informs [`c4/`](../c4/MODELING.md) Dynamic views and requirement/decision reviews.
- **Related:** [`sequences/`](../sequences/MODELING.md) (the complementary dynamic view).
- **Shared concepts (owned elsewhere):** runtime state and lifecycle (Ch 07); aggregates (Ch 05).
  This module defines none of them.

## Traceability & References
- **Handbook:** [07 — Runtime Platform](../../handbook/07-runtime-platform/CHAPTER.md),
  [05 — Domain-Driven Design](../../handbook/05-domain-driven-design/CHAPTER.md).
- **Specifications:** [`runtime`](../../specifications/runtime/).
- **ADRs:** [AD-0010](../../bootstrap/ARCHITECTURE_DECISIONS.md) (Dynamic views modeled here).
- **Worked Examples:** entity lifecycles appear in [agent](../../examples/agents/) and
  [workflow](../../examples/workflows/) examples; state-machine instances are ready-structure for
  Phase 5.
