# Template — Architecture Specification Template

A normative, implementation-independent template of the APEF
[Specification Framework](../SPECIFICATION_FRAMEWORK.md). It defines the required structure for
the architectural constraints an artifact must satisfy. Copy it to author a specification; every section must be populated (no placeholders) to
pass the [completeness gate](../SPECIFICATION_COMPLETION.md).

**Purpose of this specification:** State the boundaries, quality attributes, and structure required, consistent with the reference architecture.

## Required sections

1. **Constraints** — architectural requirements and quality attributes.
2. **Boundaries** — derived from bounded contexts.
3. **Views** — the perspectives that describe the structure.
4. **Scope** — the concern addressed.
5. **Acceptance Criteria** — measurable conformance.
6. **Traceability**, **ADR References**, **Review & Completion**.

## Conventions
- State the *what* and *why*, never the *how*; name no technology, vendor, or language.
- Declare a single owning authority and the owning Handbook chapter (see the
  [Taxonomy](../SPECIFICATION_TAXONOMY.md)).
- Establish [traceability](../SPECIFICATION_TRACEABILITY.md) and pass the applicable
  [review dimensions](../SPECIFICATION_REVIEW.md) and [completion gates](../SPECIFICATION_COMPLETION.md).
