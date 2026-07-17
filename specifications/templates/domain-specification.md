# Template — Domain Specification Template

A normative, implementation-independent template of the APEF
[Specification Framework](../SPECIFICATION_FRAMEWORK.md). It defines the required structure for
a domain: its bounded contexts and language. Copy it to author a specification; every section must be populated (no placeholders) to
pass the [completeness gate](../SPECIFICATION_COMPLETION.md).

**Purpose of this specification:** Model a bounded context and its ubiquitous language.

## Required sections

1. **Bounded Context** — its boundary and meaning.
2. **Ubiquitous Language** — canonical terms, linked to the glossary.
3. **Model** — entities, value objects, aggregates, domain services.
4. **Events** — significant domain events.
5. **Acceptance Criteria** — terminology and model consistency.
6. **Traceability**, **ADR References**, **Review & Completion**.

## Conventions
- State the *what* and *why*, never the *how*; name no technology, vendor, or language.
- Declare a single owning authority and the owning Handbook chapter (see the
  [Taxonomy](../SPECIFICATION_TAXONOMY.md)).
- Establish [traceability](../SPECIFICATION_TRACEABILITY.md) and pass the applicable
  [review dimensions](../SPECIFICATION_REVIEW.md) and [completion gates](../SPECIFICATION_COMPLETION.md).
