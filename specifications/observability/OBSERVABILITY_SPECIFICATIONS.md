# Observability Specifications

The Observability specification library of the APEF. It owns the engineering language for
specify what must be observable and to what standard: metrics, logs, traces, health, monitoring, visibility, and observability acceptance. It is governed by the
[Specification Framework](../SPECIFICATION_FRAMEWORK.md) and specifies concepts owned by
[Chapter 14](../../handbook/14-observability/CHAPTER.md); it references those concepts and
never redefines them.

> The directory [`README.md`](README.md) is a frozen Foundation artifact and is unchanged; this
> document is the authoritative entry point for the Observability library.

## Specification types owned

- **Observability Specifications** — a specification type owned by this library.
- **Metrics** — a specification type owned by this library.
- **Logs** — a specification type owned by this library.
- **Traces** — a specification type owned by this library.
- **Health** — a specification type owned by this library.
- **Monitoring** — a specification type owned by this library.
- **Operational Visibility** — a specification type owned by this library.
- **Observability Acceptance** — a specification type owned by this library.

## Specification contract (per the framework)

- **Purpose:** Specify what must be observable and to what standard: metrics, logs, traces, health, monitoring, visibility, and observability acceptance.
- **Scope:** the Observability concern only; one specification per single owning concern.
- **Inputs:** the upstream library's approved specifications ([`../security/`](../security/)) and the relevant
  discovery or domain material.
- **Outputs:** approved Observability specifications authored from this library's
  [templates](templates/).
- **Dependencies:** derives from [`../security/`](../security/); constrains [`../ui/`](../ui/).
- **Owner:** Observability Architect (single owning authority).
- **Review authority:** Observability, Operations review (see [Specification Review](../SPECIFICATION_REVIEW.md)).
- **Completion criteria:** all applicable [completion gates](../SPECIFICATION_COMPLETION.md)
  pass; traceability is bidirectional.
- **Relationship with other libraries:** part of the conceptual chain in the
  [Library Index](../SPECIFICATION_LIBRARY_INDEX.md); derives from the library above and
  constrains the one below.

## Conventions

- Specify the *what* and *why*, never the *how*; name no technology, vendor, cloud, or language.
- Reference concepts owned by [Chapter 14](../../handbook/14-observability/CHAPTER.md) rather
  than redefining them.
- Author from the [templates](templates/); illustrate with the [examples](examples/); manage per
  the [reference guide](reference/REFERENCE_GUIDE.md).
