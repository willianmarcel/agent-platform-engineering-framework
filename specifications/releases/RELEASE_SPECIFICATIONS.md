# Release Specifications

The Release specification library of the APEF. It owns the engineering language for
specify a release: scope, acceptance, readiness, compatibility, migration, rollback, validation, and governance. It is governed by the
[Specification Framework](../SPECIFICATION_FRAMEWORK.md) and specifies concepts owned by
[Chapter 19](../../handbook/19-devops/CHAPTER.md); it references those concepts and
never redefines them.

> The directory [`README.md`](README.md) is a frozen Foundation artifact and is unchanged; this
> document is the authoritative entry point for the Release library.

## Specification types owned

- **Release Specifications** — a specification type owned by this library.
- **Release Scope** — a specification type owned by this library.
- **Acceptance** — a specification type owned by this library.
- **Readiness** — a specification type owned by this library.
- **Compatibility** — a specification type owned by this library.
- **Migration** — a specification type owned by this library.
- **Rollback Strategy** — a specification type owned by this library.
- **Release Validation** — a specification type owned by this library.
- **Release Governance** — a specification type owned by this library.

## Specification contract (per the framework)

- **Purpose:** Specify a release: scope, acceptance, readiness, compatibility, migration, rollback, validation, and governance.
- **Scope:** the Release concern only; one specification per single owning concern.
- **Inputs:** the upstream library's approved specifications ([`../roadmap/`](../roadmap/)) and the relevant
  discovery or domain material.
- **Outputs:** approved Release specifications authored from this library's
  [templates](templates/).
- **Dependencies:** derives from [`../roadmap/`](../roadmap/); constrains none (the tail of the chain).
- **Owner:** Platform Architect / Observability Architect (single owning authority).
- **Review authority:** Operations, Testing review (see [Specification Review](../SPECIFICATION_REVIEW.md)).
- **Completion criteria:** all applicable [completion gates](../SPECIFICATION_COMPLETION.md)
  pass; traceability is bidirectional.
- **Relationship with other libraries:** part of the conceptual chain in the
  [Library Index](../SPECIFICATION_LIBRARY_INDEX.md); derives from the library above and
  constrains the one below.

## Conventions

- Specify the *what* and *why*, never the *how*; name no technology, vendor, cloud, or language.
- Reference concepts owned by [Chapter 19](../../handbook/19-devops/CHAPTER.md) rather
  than redefining them.
- Author from the [templates](templates/); illustrate with the [examples](examples/); manage per
  the [reference guide](reference/REFERENCE_GUIDE.md).
