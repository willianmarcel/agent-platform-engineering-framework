# Sequence (Interaction) Modeling

The methodology for modeling **interactions over time** — the ordered exchange of messages between
participants. Entry document for [`sequences/`](README.md) (frozen README remains the contract). It
provides Dynamic (interaction) views of the [C4 view model](../c4/MODELING.md) (AD-0010).

## Overview
Sequence modeling describes how participants — users, agents, systems, and components — interact in
order to accomplish something: who sends what to whom, in what order, and what comes back. The
participants and their responsibilities are owned by their Handbook chapters
([06 — Reference Architecture](../../handbook/06-reference-architecture/CHAPTER.md),
[07 — Runtime Platform](../../handbook/07-runtime-platform/CHAPTER.md)); this module owns the modeling
method.

## Purpose
To make ordered behavior explicit where sequence and timing matter — clarifying protocols, exposing
race conditions and failure points, and communicating flows that structural views cannot show.

## Scope
**In scope:** modeling synchronous flows, asynchronous flows, and user, agent, system, and event
interactions as ordered exchanges. **Out of scope:** the couplings themselves
([`integrations/`](../integrations/MODELING.md)) and object lifecycles
([`state-machines/`](../state-machines/MODELING.md)).

## When to use (vs state machines)
Use a **sequence** when the question is *how several participants interact in order* over one scenario.
Use a **[state machine](../state-machines/MODELING.md)** when the question is *how one entity's state
changes over its whole life*. If you are modeling a conversation, use a sequence; if you are modeling
a lifecycle, use a state machine.

## Principles
One scenario per sequence; participants and messages named by role; failure and alternate paths
modeled, not just the happy path; time flows one way.

## Modeling Process
1. **Scenario** — state the single scenario the sequence models and its trigger.
2. **Participants** — list the participants (by role) that take part.
3. **Exchange** — model the ordered messages between them, marking each synchronous or asynchronous.
4. **Alternates** — model the significant alternate and failure paths.
5. **Boundaries** — mark where the flow crosses a trust or context boundary (reference
   [`network/`](../network/MODELING.md) / [`integrations/`](../integrations/MODELING.md)).

## Guidelines & Notation
- Keep one scenario per diagram; split long flows into named sub-scenarios.
- Distinguish synchronous (blocking) from asynchronous (non-blocking) messages notationally.
- Author as diagram-as-code sequence diagrams. Name participants by role, messages by intent; name no
  technology.

## Views & Artifacts
- **Interaction sequence** — the ordered message exchange for one scenario.
- **Alternate/failure paths** — significant deviations from the main flow.

## Patterns & Anti-patterns
**Patterns:** one scenario per diagram; explicit sync/async markers; modeled failure paths; boundary
crossings annotated. **Anti-patterns:** cramming many scenarios into one diagram; happy-path-only
flows; using a sequence to express a lifecycle (use a state machine); embedding structural detail.

## Review Checklist & Quality Criteria
- [ ] The diagram models exactly one scenario with a clear trigger.
- [ ] Every message is marked synchronous or asynchronous.
- [ ] Significant failure/alternate paths are modeled.
- [ ] Boundary crossings reference the network/integration models.
- [ ] Participants and messages are named by role/intent, not product.
- [ ] A lifecycle would not have been the better tool.

## Cross-Module Integration
- **Upstream:** [`runtime/`](../runtime/MODELING.md) (the behavior being sequenced),
  [`integrations/`](../integrations/MODELING.md) (the couplings exercised),
  [`event-storming/`](../event-storming/MODELING.md) (process flows).
- **Downstream:** informs [`c4/`](../c4/MODELING.md) Dynamic views and requirement/decision reviews.
- **Related:** [`state-machines/`](../state-machines/MODELING.md) (the complementary dynamic view).
- **Shared concepts (owned elsewhere):** participants and their responsibilities (Ch 06/07). This
  module defines none of them.

## Traceability & References
- **Handbook:** [06 — Reference Architecture](../../handbook/06-reference-architecture/CHAPTER.md),
  [07 — Runtime Platform](../../handbook/07-runtime-platform/CHAPTER.md).
- **Specifications:** [`architecture-requirements`](../../specifications/architecture-requirements/),
  [`runtime`](../../specifications/runtime/).
- **ADRs:** [AD-0010](../../bootstrap/ARCHITECTURE_DECISIONS.md) (Dynamic views modeled here).
- **Worked Examples:** interaction flows appear in [workflow](../../examples/workflows/) and
  [supervisor](../../examples/supervisors/) examples; sequence instances are ready-structure for
  Phase 5.
