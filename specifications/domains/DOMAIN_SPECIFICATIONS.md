# Domain Specifications

The Domain specification library of the APEF. It owns the engineering language for
specify the problem domain: its bounded contexts, responsibilities, relationships, and boundaries, in ubiquitous language. It is governed by the
[Specification Framework](../SPECIFICATION_FRAMEWORK.md) and specifies concepts owned by
[Chapter 05](../../handbook/05-domain-driven-design/CHAPTER.md); it references those concepts and
never redefines them.

> The directory [`README.md`](README.md) is a frozen Foundation artifact and is unchanged; this
> document is the authoritative entry point for the Domain library.

## Specification types owned

- **Domain Specifications** — a specification type owned by this library.
- **Bounded Context Specifications** — a specification type owned by this library.
- **Domain Responsibilities** — a specification type owned by this library.
- **Domain Relationships** — a specification type owned by this library.
- **Domain Boundaries** — a specification type owned by this library.

## Specification contract (per the framework)

- **Purpose:** Specify the problem domain: its bounded contexts, responsibilities, relationships, and boundaries, in ubiquitous language.
- **Scope:** the Domain concern only; one specification per single owning concern.
- **Inputs:** the upstream library's approved specifications ([`../capabilities/`](../capabilities/)) and the relevant
  discovery or domain material.
- **Outputs:** approved Domain specifications authored from this library's
  [templates](templates/).
- **Dependencies:** derives from [`../capabilities/`](../capabilities/); constrains [`../architecture-requirements/`](../architecture-requirements/).
- **Owner:** Domain Expert (single owning authority).
- **Review authority:** Domain, Architecture review (see [Specification Review](../SPECIFICATION_REVIEW.md)).
- **Completion criteria:** all applicable [completion gates](../SPECIFICATION_COMPLETION.md)
  pass; traceability is bidirectional.
- **Relationship with other libraries:** part of the conceptual chain in the
  [Library Index](../SPECIFICATION_LIBRARY_INDEX.md); derives from the library above and
  constrains the one below.

## Conventions

- Specify the *what* and *why*, never the *how*; name no technology, vendor, cloud, or language.
- Reference concepts owned by [Chapter 05](../../handbook/05-domain-driven-design/CHAPTER.md) rather
  than redefining them.
- Author from the [templates](templates/); illustrate with the [examples](examples/); manage per
  the [reference guide](reference/REFERENCE_GUIDE.md).
