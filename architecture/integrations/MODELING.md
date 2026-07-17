# Integration Modeling

The methodology for modeling how the platform's parts and external systems **communicate**. Entry
document for [`integrations/`](README.md) (frozen README remains the contract).

## Overview
Integration modeling describes the connections between containers and between the platform and
external systems: whether communication is synchronous or asynchronous, the contracts that govern it,
how those contracts evolve, and how the integration behaves under failure. The API, contract, and
versioning concepts it depicts are owned by [13 — API Platform](../../handbook/13-api-platform/CHAPTER.md)
and [09 — Provider Platform](../../handbook/09-provider-platform/CHAPTER.md); the anti-corruption
boundary is a [Domain-Driven Design](../../handbook/05-domain-driven-design/CHAPTER.md) concept. This
module owns the modeling method.

## Purpose
To make integration boundaries, contracts, and failure behavior explicit, so the platform's couplings
are deliberate, evolvable, and resilient.

## Scope
**In scope:** modeling synchronous and asynchronous communication, messaging, API interactions,
contracts and their versioning, anti-corruption layers, and reliability patterns. **Out of scope:**
defining API/contract concepts (Ch 13/09), the network path ([`network/`](../network/MODELING.md)),
and the interaction ordering ([`sequences/`](../sequences/MODELING.md)).

## Principles
Make coupling explicit and minimal; contracts are first-class and versioned; protect a bounded context
from foreign models via an anti-corruption boundary; design for partial failure.

## Modeling Process
1. **Identify integrations** — enumerate the couplings between containers and with external systems.
2. **Classify style** — mark each as synchronous (request/response) or asynchronous
   (message/event), with rationale.
3. **Define the contract** — model the interface/message contract each integration honors and its
   compatibility expectations.
4. **Version** — model how each contract evolves (compatible change, deprecation, retirement).
5. **Protect boundaries** — place anti-corruption boundaries where an external model must not leak in.
6. **Add reliability** — model the reliability arrangement (timeout, retry, idempotency, fallback,
   circuit-breaking) for each integration.

## Guidelines & Notation
- Choose synchronous vs asynchronous deliberately; record why.
- Treat every contract as versioned from the outset; model compatibility, not just the current shape.
- Author as diagram-as-code: integration maps for topology of couplings, and reference
  [`sequences/`](../sequences/MODELING.md) for the ordered flows. Name protocols by role, not product.

## Views & Artifacts
- **Integration map** — couplings, each labeled sync/async and with its contract.
- **Contract model** — the interface/message shape and compatibility rules.
- **Versioning model** — the contract's evolution path.
- **Reliability annotations** — timeout/retry/idempotency/fallback per integration.

## Patterns & Anti-patterns
**Patterns:** asynchronous messaging for decoupling; idempotent consumers; anti-corruption layer at
context edges; explicit versioning with backward compatibility; circuit breaking on unreliable
dependencies. **Anti-patterns:** hidden synchronous chains that cascade failure; shared mutable
contracts with no version; leaking an external model across a context boundary; retry without
idempotency; naming a specific broker or product.

## Review Checklist & Quality Criteria
- [ ] Every integration is classified sync/async with rationale.
- [ ] Every integration has a defined, versioned contract.
- [ ] Context boundaries needing protection have an anti-corruption boundary.
- [ ] Each integration states its reliability arrangement.
- [ ] Ordering detail is referenced to [`sequences/`](../sequences/MODELING.md), not redrawn.
- [ ] Naming is technology-neutral.

## Cross-Module Integration
- **Upstream:** [`c4/`](../c4/MODELING.md) (Container view — what integrates),
  [`architecture-requirements`](../../specifications/architecture-requirements/) (integration
  requirements).
- **Downstream:** [`sequences/`](../sequences/MODELING.md) (ordered flows over the integrations),
  [`network/`](../network/MODELING.md) (the connectivity the integrations traverse).
- **Related:** [`runtime/`](../runtime/MODELING.md) (failure handling), [`deployment/`](../deployment/MODELING.md).
- **Shared concepts (owned elsewhere):** API contracts/versioning (Ch 13), provider integration
  contract (Ch 09), anti-corruption layer (Ch 05). This module defines none of them.

## Traceability & References
- **Handbook:** [13 — API Platform](../../handbook/13-api-platform/CHAPTER.md),
  [09 — Provider Platform](../../handbook/09-provider-platform/CHAPTER.md),
  [05 — Domain-Driven Design](../../handbook/05-domain-driven-design/CHAPTER.md).
- **Specifications:** [`architecture-requirements`](../../specifications/architecture-requirements/).
- **ADRs:** integration decisions are recorded via the [ADR framework](../../adrs/ADR_FRAMEWORK.md).
- **Worked Examples:** [provider examples](../../examples/providers/) illustrate integration
  contracts; integration model instances are ready-structure for Phase 5.
