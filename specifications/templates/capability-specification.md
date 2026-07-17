# Template — Capability Specification Template

A normative, implementation-independent template of the APEF
[Specification Framework](../SPECIFICATION_FRAMEWORK.md). It defines the required structure for
a durable business capability. Copy it to author a specification; every section must be populated (no placeholders) to
pass the [completeness gate](../SPECIFICATION_COMPLETION.md).

**Purpose of this specification:** Define a capability by the jobs it serves and the outcomes it produces.

## Required sections

1. **Capability** — named from the user's view.
2. **Jobs & Outcomes** — the jobs served and outcomes produced.
3. **Scope** — in / out.
4. **Inputs & Outputs** — what it consumes and produces.
5. **Acceptance Criteria** — measurable.
6. **Dependencies** — upstream product; downstream domains.
7. **Traceability**, **ADR References**, **Review & Completion**.

## Conventions
- State the *what* and *why*, never the *how*; name no technology, vendor, or language.
- Declare a single owning authority and the owning Handbook chapter (see the
  [Taxonomy](../SPECIFICATION_TAXONOMY.md)).
- Establish [traceability](../SPECIFICATION_TRACEABILITY.md) and pass the applicable
  [review dimensions](../SPECIFICATION_REVIEW.md) and [completion gates](../SPECIFICATION_COMPLETION.md).
