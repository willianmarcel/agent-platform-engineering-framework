# Chapter 13 — API Platform

## Introduction

This chapter defines the API plane of an AI Agent Platform: the capability through which
the platform's interaction boundaries are defined and consumed. Its prerequisite is
[Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md), which placed
the API plane within the whole. The API plane is where the platform's capabilities are made
available to consumers through explicit, stable contracts.

This chapter defines interaction boundaries as an architectural capability — contracts,
versioning, governance, and lifecycle — not any transport technology. It never prescribes a
particular API style or protocol; it describes what an API contract must guarantee, so the
guidance remains valid whatever transport realizes it. No product is named and no
implementation is prescribed.

## Objectives

After reading this chapter, a reader will be able to:

- Explain what the API plane is responsible for and where its boundary lies.
- Distinguish public, internal, event, and integration APIs.
- Reason about API contracts, versioning, governance, and lifecycle.
- Keep API design consistent and technology-neutral.

## Concepts

This chapter **owns** the concepts below; other chapters reference them without redefining
them.

**Platform APIs.** The full set of explicit contracts through which the platform's
capabilities are offered for consumption. Platform APIs are the platform's interaction
boundary: they make capability available without exposing how it is realized.

**Public APIs.** The platform APIs offered to consumers outside the platform's own
implementation, held to the strongest stability and compatibility commitments. Public APIs
are a promise the platform keeps to those who depend on it.

**Internal APIs.** The platform APIs used among the platform's own parts, which may evolve
more freely than public ones while still honoring explicit contracts. The public/internal
distinction sets how strong a compatibility promise each API carries.

**Event APIs.** The contracts through which the platform offers events for consumers to
observe and react to. Event APIs expose events as an interaction boundary; the persistence
of events is owned by [Chapter 12](../12-data-platform/CHAPTER.md) and the meaning of domain
events by [Chapter 05](../05-domain-driven-design/CHAPTER.md).

**Integration APIs.** The contracts through which the platform is integrated with external
systems as a first-class interaction boundary. Integration APIs are the platform's own
contracts for integration; the plugin connectors that reach outward are owned by
[Chapter 10](../10-plugin-platform/CHAPTER.md).

**API Contracts.** The explicit agreements an API embodies — what it accepts, what it
returns, and the guarantees it upholds — independent of how the API is transported. The
contract, not the transport, is the durable substance of an API.

**API Versioning.** The discipline of evolving APIs without breaking those who depend on
them, by making compatibility explicit and change deliberate. Versioning is how an API
honors its contract across time.

**API Consistency.** The property that the platform's APIs follow one coherent set of
conventions, so consumers can learn once and apply everywhere. Consistency makes the API
surface predictable and trustworthy.

**API Design Principles.** The durable, technology-neutral principles that govern how APIs
are shaped — clarity, consistency, explicitness of contract, and compatibility. These are
the API-specific expression of the design principles owned by
[Chapter 03](../03-engineering-principles/CHAPTER.md).

**API Governance.** The practices that keep the API surface coherent, compatible, and
compliant over time — deciding what may be published, how it must conform, and how it
evolves. API governance is the API-specific application of the platform governance owned by
[Chapter 11](../11-control-plane/CHAPTER.md).

**API Lifecycle.** The stages an API passes through — from design and publication, through
versioned evolution, to deprecation and retirement — managed so consumers are never
stranded. The lifecycle keeps API change orderly and humane.

**API Discovery.** The capability by which consumers find the APIs available to them and
understand their contracts. Discovery is what makes the platform's capabilities usable
without prior knowledge of them.

## Principles

- **Contract over transport.** Define APIs by the guarantees of their contract, never by a
  particular transport technology or style.
- **Compatibility is a promise.** Evolve APIs through explicit versioning so those who
  depend on them are never broken without notice.
- **One coherent surface.** Hold all APIs to consistent conventions so the platform is
  learnable once.
- **Govern the surface.** Keep the API surface coherent and compliant through API
  governance, applying platform governance.
- **Uphold the platform's architectural principles.** Like every platform capability, the
  API plane is secure, observable, governable, explainable, and composable by design;
  provider-, cloud-, and runtime-agnostic; and vendor-neutral — as expressed in the
  [Platform Capability Model](../PLATFORM_CAPABILITY_MODEL.md) and owned by
  [Chapter 03](../03-engineering-principles/CHAPTER.md).

## Architecture

This section describes the structure of the *API plane*, one capability within the
[Platform Capability Model](../PLATFORM_CAPABILITY_MODEL.md) and the reference architecture
owned by [Chapter 06](../06-reference-architecture/CHAPTER.md).

The API plane is organized around explicit, governed contracts:

1. **Platform APIs** — as **public**, **internal**, **event**, and **integration** APIs —
   expose the platform's capabilities.
2. Each is defined by an **API contract**, shaped by **API design principles** and held to
   **API consistency**.
3. **API versioning** and the **API lifecycle** govern change; **API governance** keeps the
   surface coherent; and **API discovery** makes it usable.

The API plane exposes the capabilities other planes provide without performing their work:
it offers the runtime's execution, the builder's creations, the provider's intelligence,
and the data plane's information as contracts, under the control plane's governance.

## Patterns

- **Contract-first APIs.** *Context:* offering any capability. Define the contract before
  the transport, so consumers depend on guarantees, not mechanisms.
- **Versioned evolution.** *Context:* changing an API. Evolve through explicit versioning
  and a managed lifecycle so no consumer is stranded.
- **Uniform surface.** *Context:* many APIs. Apply one set of conventions so the whole
  surface is consistent and discoverable.

## Anti-patterns

- **Transport-defined API.** *Why it fails:* defining an API by its transport couples
  consumers to a technology and dates the design. *Instead:* contract over transport.
- **Silent breaking change.** *Why it fails:* changing a contract without versioning breaks
  dependents and destroys trust. *Instead:* compatibility is a promise.
- **Inconsistent surface.** *Why it fails:* APIs with divergent conventions force consumers
  to relearn constantly. *Instead:* one coherent surface.
- **Ungoverned publication.** *Why it fails:* APIs published without governance drift and
  proliferate. *Instead:* govern the surface.

## Best Practices

- Express every API as a contract independent of transport.
- Evolve APIs through explicit versioning and a managed lifecycle.
- Apply consistent design conventions across the whole API surface.
- Govern the API surface as a specialization of platform governance
  ([Chapter 11](../11-control-plane/CHAPTER.md)).
- Expose events and integration as first-class APIs without redefining their meaning or
  persistence.

## Examples

The following are illustrative, non-executable aids.

**Kinds of platform API:**

| Kind | Interaction boundary it defines |
|------|---------------------------------|
| Public API | Capability offered to external consumers, with the strongest compatibility promise |
| Internal API | Capability shared among the platform's parts, free to evolve within contract |
| Event API | Events offered for consumers to observe and react to |
| Integration API | The platform's own contracts for integration with external systems |

**Versioned evolution (illustrative):** an API's contract may change only in ways that keep
existing consumers working, or through a new version with a managed deprecation of the old —
so a consumer is never broken without a path forward.

## Checklist

A reader is ready to proceed to
[Chapter 14 — Observability](../14-observability/CHAPTER.md) when they can confirm:

- [ ] I can state what the API plane defines and its boundary.
- [ ] I can distinguish public, internal, event, and integration APIs.
- [ ] I can reason about API contracts, versioning, governance, and lifecycle.
- [ ] I can keep API design consistent and technology-neutral.

## References

- [Chapter 03 — Engineering Principles](../03-engineering-principles/CHAPTER.md) — owns the
  design principles the API design principles specialize.
- [Chapter 05 — Domain-Driven Design](../05-domain-driven-design/CHAPTER.md) — owns the
  domain events that event APIs expose.
- [Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md) — the frame
  that places the API plane.
- [Chapter 10 — Plugin Platform](../10-plugin-platform/CHAPTER.md) — owns the plugin
  connectors distinct from integration APIs.
- [Chapter 11 — Control Plane](../11-control-plane/CHAPTER.md) — owns the platform governance
  that API governance specializes.
- [Chapter 12 — Data Platform](../12-data-platform/CHAPTER.md) — owns the persistence of the
  events that event APIs expose.
- [Platform Capability Model](../PLATFORM_CAPABILITY_MODEL.md) — the canonical model this
  capability belongs to.
- [Glossary](../21-glossary/) — canonical terms used in this chapter.

## Summary

The API plane defines the platform's interaction boundaries as explicit, technology-neutral
contracts — public, internal, event, and integration APIs — shaped by consistent API design
principles, evolved through versioning and a managed lifecycle, kept coherent through API
governance, and made usable through discovery. It exposes the capabilities of the other
planes without performing their work, and it defines contracts, never transports. The next
chapter, [Chapter 14 — Observability](../14-observability/CHAPTER.md), defines how the
platform is made visible in operation.
