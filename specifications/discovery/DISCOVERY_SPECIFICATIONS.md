# Discovery Specifications

The Discovery specification library of the APEF. It owns the engineering language for
specify what discovery has established before commitment: stakeholders, personas, problems, opportunities, assumptions, and open questions. It is governed by the
[Specification Framework](../SPECIFICATION_FRAMEWORK.md) and specifies concepts owned by
[Chapter 02](../../handbook/02-product-thinking/CHAPTER.md); it references those concepts and
never redefines them.

> The directory [`README.md`](README.md) is a frozen Foundation artifact and is unchanged; this
> document is the authoritative entry point for the Discovery library.

## Specification types owned

- **Discovery Specifications** — a specification type owned by this library.
- **Stakeholders** — a specification type owned by this library.
- **Personas** — a specification type owned by this library.
- **Business Problems** — a specification type owned by this library.
- **Opportunities** — a specification type owned by this library.
- **Assumptions** — a specification type owned by this library.
- **Open Questions** — a specification type owned by this library.
- **Scope Discovery** — a specification type owned by this library.

## Specification contract (per the framework)

- **Purpose:** Specify what discovery has established before commitment: stakeholders, personas, problems, opportunities, assumptions, and open questions.
- **Scope:** the Discovery concern only; one specification per single owning concern.
- **Inputs:** the upstream library's approved specifications ([`../vision/`](../vision/)) and the relevant
  discovery or domain material.
- **Outputs:** approved Discovery specifications authored from this library's
  [templates](templates/).
- **Dependencies:** derives from [`../vision/`](../vision/); constrains [`../capabilities/`](../capabilities/).
- **Owner:** Product Architect (single owning authority).
- **Review authority:** Product, Domain review (see [Specification Review](../SPECIFICATION_REVIEW.md)).
- **Completion criteria:** all applicable [completion gates](../SPECIFICATION_COMPLETION.md)
  pass; traceability is bidirectional.
- **Relationship with other libraries:** part of the conceptual chain in the
  [Library Index](../SPECIFICATION_LIBRARY_INDEX.md); derives from the library above and
  constrains the one below.

## Conventions

- Specify the *what* and *why*, never the *how*; name no technology, vendor, cloud, or language.
- Reference concepts owned by [Chapter 02](../../handbook/02-product-thinking/CHAPTER.md) rather
  than redefining them.
- Author from the [templates](templates/); illustrate with the [examples](examples/); manage per
  the [reference guide](reference/REFERENCE_GUIDE.md).
