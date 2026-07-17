# Template — Runtime Specification Template

A normative, implementation-independent template of the APEF
[Specification Framework](../SPECIFICATION_FRAMEWORK.md). It defines the required structure for
the runtime behavior an artifact requires. Copy it to author a specification; every section must be populated (no placeholders) to
pass the [completeness gate](../SPECIFICATION_COMPLETION.md).

**Purpose of this specification:** Specify execution, lifecycle, and state requirements within runtime boundaries.

## Required sections

1. **Execution Model** — how work is carried out.
2. **Lifecycle** — the stages managed.
3. **State & Session** — runtime state requirements (persistence delegated to Data).
4. **Scope** — the runtime concern.
5. **Acceptance Criteria** — measurable runtime behavior.
6. **Traceability**, **ADR References**, **Review & Completion**.

## Conventions
- State the *what* and *why*, never the *how*; name no technology, vendor, or language.
- Declare a single owning authority and the owning Handbook chapter (see the
  [Taxonomy](../SPECIFICATION_TAXONOMY.md)).
- Establish [traceability](../SPECIFICATION_TRACEABILITY.md) and pass the applicable
  [review dimensions](../SPECIFICATION_REVIEW.md) and [completion gates](../SPECIFICATION_COMPLETION.md).
