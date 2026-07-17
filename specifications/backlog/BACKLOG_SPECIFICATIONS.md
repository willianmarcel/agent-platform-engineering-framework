# Backlog Specifications

The Backlog specification library of the APEF. It owns the engineering language for
specify how work is decomposed and governed as a backlog — epics, features, stories, and tasks — as methodology, never prescribing any Agile framework. It is governed by the
[Specification Framework](../SPECIFICATION_FRAMEWORK.md) and specifies concepts owned by
[Chapter 04](../../handbook/04-development-methodology/CHAPTER.md); it references those concepts and
never redefines them.

> The directory [`README.md`](README.md) is a frozen Foundation artifact and is unchanged; this
> document is the authoritative entry point for the Backlog library.

## Specification types owned

- **Engineering Backlog** — a specification type owned by this library.
- **Capability Decomposition** — a specification type owned by this library.
- **Epics** — a specification type owned by this library.
- **Features** — a specification type owned by this library.
- **Stories** — a specification type owned by this library.
- **Tasks** — a specification type owned by this library.
- **Prioritization** — a specification type owned by this library.
- **Backlog Lifecycle** — a specification type owned by this library.
- **Backlog Governance** — a specification type owned by this library.
- **Traceability to Specifications** — a specification type owned by this library.

## Specification contract (per the framework)

- **Purpose:** Specify how work is decomposed and governed as a backlog — epics, features, stories, and tasks — as methodology, never prescribing any Agile framework.
- **Scope:** the Backlog concern only; one specification per single owning concern.
- **Inputs:** the upstream library's approved specifications ([`../ui/`](../ui/)) and the relevant
  discovery or domain material.
- **Outputs:** approved Backlog specifications authored from this library's
  [templates](templates/).
- **Dependencies:** derives from [`../ui/`](../ui/); constrains [`../roadmap/`](../roadmap/).
- **Owner:** Product Architect (single owning authority).
- **Review authority:** Product, Governance review (see [Specification Review](../SPECIFICATION_REVIEW.md)).
- **Completion criteria:** all applicable [completion gates](../SPECIFICATION_COMPLETION.md)
  pass; traceability is bidirectional.
- **Relationship with other libraries:** part of the conceptual chain in the
  [Library Index](../SPECIFICATION_LIBRARY_INDEX.md); derives from the library above and
  constrains the one below.

## Conventions

- Specify the *what* and *why*, never the *how*; name no technology, vendor, cloud, or language.
- Reference concepts owned by [Chapter 04](../../handbook/04-development-methodology/CHAPTER.md) rather
  than redefining them.
- Author from the [templates](templates/); illustrate with the [examples](examples/); manage per
  the [reference guide](reference/REFERENCE_GUIDE.md).
