# Event Storming Modeling

The methodology for **domain exploration** through collaborative event modeling. Entry document for
[`event-storming/`](README.md) (frozen README remains the contract). Per **AD-0011**, event storming
is an Architecture activity whose outputs may inform, but do not own, the domain model.

## Overview
Event storming explores a domain by discovering the significant events that occur in it, then the
commands, policies, aggregates, and hotspots around them. It answers "what happens in this domain,
what causes it, and where is it uncertain?" The domain concepts it surfaces — bounded contexts,
domain events, aggregates, the ubiquitous language — are owned by
[05 — Domain-Driven Design](../../handbook/05-domain-driven-design/CHAPTER.md); this module owns the
exploration method and connects its outputs to the specifications.

## Purpose
To make domain discovery a repeatable, low-cost activity that surfaces behavior and disagreement early
and feeds precise inputs into domain specifications — before structural or runtime modeling begins.

## Scope
**In scope:** the exploration process and its notation (events, commands, policies, aggregates,
hotspots) and the handoff to specifications. **Out of scope:** defining DDD concepts (Ch 05) and
authoring the domain specifications themselves ([`domains`](../../specifications/domains/)).

## Principles
Explore behavior before structure; use the domain's own language; make uncertainty visible (hotspots)
rather than hiding it; keep the model disposable and cheap until it stabilizes.

## Modeling Process
1. **Events** — surface the domain events (facts that occurred), in past tense, along a timeline.
2. **Commands** — identify the commands (intentions/actions) that cause each event.
3. **Actors & Policies** — attach the actors that issue commands and the policies ("whenever X then
   Y") that react to events.
4. **Aggregates** — cluster commands and events around the aggregates that enforce their consistency.
5. **Hotspots** — mark disagreements, unknowns, and risks explicitly for resolution.
6. **Boundaries** — group the model into candidate bounded contexts.

## Guidelines & Notation
- Keep events past-tense and business-meaningful; keep commands imperative.
- Do not resolve hotspots by guessing — record them and route them to discovery/domain work.
- Author as diagram-as-code (a timeline of events with commands, policies, and aggregate groupings);
  color/lane conventions distinguish the element types. Name no technology.

## Views & Artifacts
- **Event timeline** — events in sequence.
- **Command/event/policy model** — causes and reactions.
- **Aggregate groupings** — consistency boundaries.
- **Hotspot list** — open questions and risks.
- **Candidate bounded contexts** — handoff to domain specifications.

## Patterns & Anti-patterns
**Patterns:** big-picture first, then process-level detail; hotspots surfaced early; aggregates
derived from invariants. **Anti-patterns:** jumping to data models or structure; suppressing
disagreement; inventing events with no actor or command; treating the storming output as the final
domain model (it *informs* it — AD-0011).

## Review Checklist & Quality Criteria
- [ ] Events are past-tense, business-meaningful facts.
- [ ] Every event has a cause (command or policy).
- [ ] Aggregates enforce stated invariants.
- [ ] Hotspots are captured, not silently resolved.
- [ ] Candidate contexts hand off cleanly to domain specifications.
- [ ] The model uses the ubiquitous language and names no technology.

## Cross-Module Integration
- **Upstream:** [`discovery` specifications](../../specifications/discovery/) and product intent —
  what to explore.
- **Downstream:** [`domains` specifications](../../specifications/domains/) (the outputs feed the
  domain model, per AD-0011); [`state-machines/`](../state-machines/MODELING.md) (aggregate
  lifecycles) and [`sequences/`](../sequences/MODELING.md) (process flows).
- **Related:** [`runtime/`](../runtime/MODELING.md) (events realized at runtime).
- **Shared concepts (owned elsewhere):** bounded contexts, domain events, aggregates, ubiquitous
  language (Ch 05). This module defines none of them.

## Traceability & References
- **Handbook:** [05 — Domain-Driven Design](../../handbook/05-domain-driven-design/CHAPTER.md).
- **Specifications:** [`discovery`](../../specifications/discovery/),
  [`domains`](../../specifications/domains/).
- **ADRs:** [AD-0011](../../bootstrap/ARCHITECTURE_DECISIONS.md) (placement; informs the domain model).
- **Worked Examples:** domain behavior appears in [agent examples](../../examples/agents/); storming
  instances are ready-structure for Phase 5.
