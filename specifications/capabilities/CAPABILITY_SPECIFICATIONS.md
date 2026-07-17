# Capability Specifications

The Capability specification library of the APEF. It owns the engineering language for
specify the durable capabilities a product provides, and their relationships, dependencies, boundaries, and evolution. It is governed by the
[Specification Framework](../SPECIFICATION_FRAMEWORK.md) and specifies concepts owned by
[Chapter 02](../../handbook/02-product-thinking/CHAPTER.md); it references those concepts and
never redefines them.

> The directory [`README.md`](README.md) is a frozen Foundation artifact and is unchanged; this
> document is the authoritative entry point for the Capability library.

## Specification types owned

- **Capability Specifications** — a specification type owned by this library.
- **Capability Relationships** — a specification type owned by this library.
- **Capability Dependencies** — a specification type owned by this library.
- **Capability Boundaries** — a specification type owned by this library.
- **Capability Evolution** — a specification type owned by this library.

## Specification contract (per the framework)

- **Purpose:** Specify the durable capabilities a product provides, and their relationships, dependencies, boundaries, and evolution.
- **Scope:** the Capability concern only; one specification per single owning concern.
- **Inputs:** the upstream library's approved specifications ([`../discovery/`](../discovery/)) and the relevant
  discovery or domain material.
- **Outputs:** approved Capability specifications authored from this library's
  [templates](templates/).
- **Dependencies:** derives from [`../discovery/`](../discovery/); constrains [`../domains/`](../domains/).
- **Owner:** Product Architect (single owning authority).
- **Review authority:** Product, Architecture review (see [Specification Review](../SPECIFICATION_REVIEW.md)).
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
