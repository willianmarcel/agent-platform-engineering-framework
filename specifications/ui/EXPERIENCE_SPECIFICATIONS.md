# Experience Specifications

The Experience specification library of the APEF. It owns the engineering language for
specify the experience: interaction, navigation, accessibility, journeys, and human interaction, as philosophy rather than interface. It is governed by the
[Specification Framework](../SPECIFICATION_FRAMEWORK.md) and specifies concepts owned by
[Chapter 17](../../handbook/17-ui-ux/CHAPTER.md); it references those concepts and
never redefines them.

> The directory [`README.md`](README.md) is a frozen Foundation artifact and is unchanged; this
> document is the authoritative entry point for the Experience library.

## Specification types owned

- **Experience Specifications** — a specification type owned by this library.
- **Interaction Specifications** — a specification type owned by this library.
- **Navigation Specifications** — a specification type owned by this library.
- **Accessibility Specifications** — a specification type owned by this library.
- **Journey Specifications** — a specification type owned by this library.
- **Human Interaction Specifications** — a specification type owned by this library.

## Specification contract (per the framework)

- **Purpose:** Specify the experience: interaction, navigation, accessibility, journeys, and human interaction, as philosophy rather than interface.
- **Scope:** the Experience concern only; one specification per single owning concern.
- **Inputs:** the upstream library's approved specifications ([`../observability/`](../observability/)) and the relevant
  discovery or domain material.
- **Outputs:** approved Experience specifications authored from this library's
  [templates](templates/).
- **Dependencies:** derives from [`../observability/`](../observability/); constrains [`../backlog/`](../backlog/).
- **Owner:** Product Architect / Technical Writer (single owning authority).
- **Review authority:** Product, Documentation review (see [Specification Review](../SPECIFICATION_REVIEW.md)).
- **Completion criteria:** all applicable [completion gates](../SPECIFICATION_COMPLETION.md)
  pass; traceability is bidirectional.
- **Relationship with other libraries:** part of the conceptual chain in the
  [Library Index](../SPECIFICATION_LIBRARY_INDEX.md); derives from the library above and
  constrains the one below.

## Conventions

- Specify the *what* and *why*, never the *how*; name no technology, vendor, cloud, or language.
- Reference concepts owned by [Chapter 17](../../handbook/17-ui-ux/CHAPTER.md) rather
  than redefining them.
- Author from the [templates](templates/); illustrate with the [examples](examples/); manage per
  the [reference guide](reference/REFERENCE_GUIDE.md).
