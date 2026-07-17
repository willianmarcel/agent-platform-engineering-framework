# Security Specifications

The Security specification library of the APEF. It owns the engineering language for
specify security intent: requirements, trust boundaries, constraints, compliance and privacy requirements, and security acceptance criteria. It is governed by the
[Specification Framework](../SPECIFICATION_FRAMEWORK.md) and specifies concepts owned by
[Chapter 15](../../handbook/15-security/CHAPTER.md); it references those concepts and
never redefines them.

> The directory [`README.md`](README.md) is a frozen Foundation artifact and is unchanged; this
> document is the authoritative entry point for the Security library.

## Specification types owned

- **Security Specifications** — a specification type owned by this library.
- **Security Requirements** — a specification type owned by this library.
- **Trust Boundaries** — a specification type owned by this library.
- **Security Constraints** — a specification type owned by this library.
- **Compliance Requirements** — a specification type owned by this library.
- **Privacy Requirements** — a specification type owned by this library.
- **Security Acceptance Criteria** — a specification type owned by this library.

## Specification contract (per the framework)

- **Purpose:** Specify security intent: requirements, trust boundaries, constraints, compliance and privacy requirements, and security acceptance criteria.
- **Scope:** the Security concern only; one specification per single owning concern.
- **Inputs:** the upstream library's approved specifications ([`../runtime/`](../runtime/)) and the relevant
  discovery or domain material.
- **Outputs:** approved Security specifications authored from this library's
  [templates](templates/).
- **Dependencies:** derives from [`../runtime/`](../runtime/); constrains [`../observability/`](../observability/).
- **Owner:** Security Architect (single owning authority).
- **Review authority:** Security, Governance review (see [Specification Review](../SPECIFICATION_REVIEW.md)).
- **Completion criteria:** all applicable [completion gates](../SPECIFICATION_COMPLETION.md)
  pass; traceability is bidirectional.
- **Relationship with other libraries:** part of the conceptual chain in the
  [Library Index](../SPECIFICATION_LIBRARY_INDEX.md); derives from the library above and
  constrains the one below.

## Conventions

- Specify the *what* and *why*, never the *how*; name no technology, vendor, cloud, or language.
- Reference concepts owned by [Chapter 15](../../handbook/15-security/CHAPTER.md) rather
  than redefining them.
- Author from the [templates](templates/); illustrate with the [examples](examples/); manage per
  the [reference guide](reference/REFERENCE_GUIDE.md).
