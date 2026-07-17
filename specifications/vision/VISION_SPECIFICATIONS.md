# Vision Specifications

The Vision specification library of the APEF. It owns the engineering language for
specify the enduring intent of a product: its vision, objectives, outcomes, and the constraints and assumptions that frame it. It is governed by the
[Specification Framework](../SPECIFICATION_FRAMEWORK.md) and specifies concepts owned by
[Chapter 01](../../handbook/01-platform-vision/CHAPTER.md); it references those concepts and
never redefines them.

> The directory [`README.md`](README.md) is a frozen Foundation artifact and is unchanged; this
> document is the authoritative entry point for the Vision library.

## Specification types owned

- **Vision Specifications** — a specification type owned by this library.
- **Mission Specifications** — a specification type owned by this library.
- **Business Objectives** — a specification type owned by this library.
- **Product Outcomes** — a specification type owned by this library.
- **Success Metrics** — a specification type owned by this library.
- **Business Constraints** — a specification type owned by this library.
- **Strategic Assumptions** — a specification type owned by this library.

## Specification contract (per the framework)

- **Purpose:** Specify the enduring intent of a product: its vision, objectives, outcomes, and the constraints and assumptions that frame it.
- **Scope:** the Vision concern only; one specification per single owning concern.
- **Inputs:** the upstream library's approved specifications (none (the head of the chain)) and the relevant
  discovery or domain material.
- **Outputs:** approved Vision specifications authored from this library's
  [templates](templates/).
- **Dependencies:** derives from none (the head of the chain); constrains [`../discovery/`](../discovery/).
- **Owner:** Product Architect / Enterprise Architect (single owning authority).
- **Review authority:** Business, Product review (see [Specification Review](../SPECIFICATION_REVIEW.md)).
- **Completion criteria:** all applicable [completion gates](../SPECIFICATION_COMPLETION.md)
  pass; traceability is bidirectional.
- **Relationship with other libraries:** part of the conceptual chain in the
  [Library Index](../SPECIFICATION_LIBRARY_INDEX.md); derives from the library above and
  constrains the one below.

## Conventions

- Specify the *what* and *why*, never the *how*; name no technology, vendor, cloud, or language.
- Reference concepts owned by [Chapter 01](../../handbook/01-platform-vision/CHAPTER.md) rather
  than redefining them.
- Author from the [templates](templates/); illustrate with the [examples](examples/); manage per
  the [reference guide](reference/REFERENCE_GUIDE.md).
