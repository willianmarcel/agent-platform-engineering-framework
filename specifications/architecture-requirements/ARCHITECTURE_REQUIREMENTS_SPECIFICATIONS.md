# Architecture Requirements Specifications

The Architecture Requirements specification library of the APEF. It owns the engineering language for
specify what the architecture must satisfy: drivers, constraints, quality-attribute scenarios, risks, trade-offs, and the forces behind decisions. It is governed by the
[Specification Framework](../SPECIFICATION_FRAMEWORK.md) and specifies concepts owned by
[Chapter 06](../../handbook/06-reference-architecture/CHAPTER.md); it references those concepts and
never redefines them.

> The directory [`README.md`](README.md) is a frozen Foundation artifact and is unchanged; this
> document is the authoritative entry point for the Architecture Requirements library.

## Specification types owned

- **Architecture Drivers** — a specification type owned by this library.
- **Architecture Constraints** — a specification type owned by this library.
- **Quality Attribute Scenarios** — a specification type owned by this library.
- **Business Constraints** — a specification type owned by this library.
- **Regulatory Constraints** — a specification type owned by this library.
- **Technical Constraints** — a specification type owned by this library.
- **Architecture Risks** — a specification type owned by this library.
- **Trade-offs** — a specification type owned by this library.
- **Decision Forces** — a specification type owned by this library.
- **Architectural Assumptions** — a specification type owned by this library.

## Specification contract (per the framework)

- **Purpose:** Specify what the architecture must satisfy: drivers, constraints, quality-attribute scenarios, risks, trade-offs, and the forces behind decisions.
- **Scope:** the Architecture Requirements concern only; one specification per single owning concern.
- **Inputs:** the upstream library's approved specifications ([`../domains/`](../domains/)) and the relevant
  discovery or domain material.
- **Outputs:** approved Architecture Requirements specifications authored from this library's
  [templates](templates/).
- **Dependencies:** derives from [`../domains/`](../domains/); constrains [`../runtime/`](../runtime/).
- **Owner:** Platform Architect (single owning authority).
- **Review authority:** Architecture, Security review (see [Specification Review](../SPECIFICATION_REVIEW.md)).
- **Completion criteria:** all applicable [completion gates](../SPECIFICATION_COMPLETION.md)
  pass; traceability is bidirectional.
- **Relationship with other libraries:** part of the conceptual chain in the
  [Library Index](../SPECIFICATION_LIBRARY_INDEX.md); derives from the library above and
  constrains the one below.

## Conventions

- Specify the *what* and *why*, never the *how*; name no technology, vendor, cloud, or language.
- Reference concepts owned by [Chapter 06](../../handbook/06-reference-architecture/CHAPTER.md) rather
  than redefining them.
- Author from the [templates](templates/); illustrate with the [examples](examples/); manage per
  the [reference guide](reference/REFERENCE_GUIDE.md).
