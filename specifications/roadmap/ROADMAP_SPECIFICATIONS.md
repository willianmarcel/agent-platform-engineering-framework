# Roadmap Specifications

The Roadmap specification library of the APEF. It owns the engineering language for
specify how the product evolves: evolution strategy, capability evolution, release objectives, and strategic themes — a philosophy, not a schedule. It is governed by the
[Specification Framework](../SPECIFICATION_FRAMEWORK.md) and specifies concepts owned by
[Chapter 20](../../handbook/20-roadmap/CHAPTER.md); it references those concepts and
never redefines them.

> The directory [`README.md`](README.md) is a frozen Foundation artifact and is unchanged; this
> document is the authoritative entry point for the Roadmap library.

## Specification types owned

- **Roadmap Specifications** — a specification type owned by this library.
- **Evolution Strategy** — a specification type owned by this library.
- **Capability Evolution** — a specification type owned by this library.
- **Release Objectives** — a specification type owned by this library.
- **Strategic Themes** — a specification type owned by this library.
- **Future Planning** — a specification type owned by this library.

## Specification contract (per the framework)

- **Purpose:** Specify how the product evolves: evolution strategy, capability evolution, release objectives, and strategic themes — a philosophy, not a schedule.
- **Scope:** the Roadmap concern only; one specification per single owning concern.
- **Inputs:** the upstream library's approved specifications ([`../backlog/`](../backlog/)) and the relevant
  discovery or domain material.
- **Outputs:** approved Roadmap specifications authored from this library's
  [templates](templates/).
- **Dependencies:** derives from [`../backlog/`](../backlog/); constrains [`../releases/`](../releases/).
- **Owner:** Product Architect / Enterprise Architect (single owning authority).
- **Review authority:** Product, Business review (see [Specification Review](../SPECIFICATION_REVIEW.md)).
- **Completion criteria:** all applicable [completion gates](../SPECIFICATION_COMPLETION.md)
  pass; traceability is bidirectional.
- **Relationship with other libraries:** part of the conceptual chain in the
  [Library Index](../SPECIFICATION_LIBRARY_INDEX.md); derives from the library above and
  constrains the one below.

## Conventions

- Specify the *what* and *why*, never the *how*; name no technology, vendor, cloud, or language.
- Reference concepts owned by [Chapter 20](../../handbook/20-roadmap/CHAPTER.md) rather
  than redefining them.
- Author from the [templates](templates/); illustrate with the [examples](examples/); manage per
  the [reference guide](reference/REFERENCE_GUIDE.md).
