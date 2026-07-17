# Runtime Specifications

The Runtime specification library of the APEF. It owns the engineering language for
specify runtime intent: responsibilities, constraints, execution models, operational behaviour, and lifecycle, within runtime boundaries. It is governed by the
[Specification Framework](../SPECIFICATION_FRAMEWORK.md) and specifies concepts owned by
[Chapter 07](../../handbook/07-runtime-platform/CHAPTER.md); it references those concepts and
never redefines them.

> The directory [`README.md`](README.md) is a frozen Foundation artifact and is unchanged; this
> document is the authoritative entry point for the Runtime library.

## Specification types owned

- **Runtime Specifications** — a specification type owned by this library.
- **Runtime Responsibilities** — a specification type owned by this library.
- **Runtime Constraints** — a specification type owned by this library.
- **Execution Models** — a specification type owned by this library.
- **Operational Behaviour** — a specification type owned by this library.
- **Lifecycle** — a specification type owned by this library.

## Specification contract (per the framework)

- **Purpose:** Specify runtime intent: responsibilities, constraints, execution models, operational behaviour, and lifecycle, within runtime boundaries.
- **Scope:** the Runtime concern only; one specification per single owning concern.
- **Inputs:** the upstream library's approved specifications ([`../architecture-requirements/`](../architecture-requirements/)) and the relevant
  discovery or domain material.
- **Outputs:** approved Runtime specifications authored from this library's
  [templates](templates/).
- **Dependencies:** derives from [`../architecture-requirements/`](../architecture-requirements/); constrains [`../security/`](../security/).
- **Owner:** Runtime Architect (single owning authority).
- **Review authority:** Runtime, Architecture review (see [Specification Review](../SPECIFICATION_REVIEW.md)).
- **Completion criteria:** all applicable [completion gates](../SPECIFICATION_COMPLETION.md)
  pass; traceability is bidirectional.
- **Relationship with other libraries:** part of the conceptual chain in the
  [Library Index](../SPECIFICATION_LIBRARY_INDEX.md); derives from the library above and
  constrains the one below.

## Conventions

- Specify the *what* and *why*, never the *how*; name no technology, vendor, cloud, or language.
- Reference concepts owned by [Chapter 07](../../handbook/07-runtime-platform/CHAPTER.md) rather
  than redefining them.
- Author from the [templates](templates/); illustrate with the [examples](examples/); manage per
  the [reference guide](reference/REFERENCE_GUIDE.md).
