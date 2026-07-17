# Template — API Specification Template

A normative, implementation-independent template of the APEF
[Specification Framework](../SPECIFICATION_FRAMEWORK.md). It defines the required structure for
an interaction boundary as a technology-neutral contract. Copy it to author a specification; every section must be populated (no placeholders) to
pass the [completeness gate](../SPECIFICATION_COMPLETION.md).

**Purpose of this specification:** Specify an API by its contract, versioning, and consistency — never its transport.

## Required sections

1. **Contract** — inputs, outputs, and guarantees.
2. **Versioning** — compatibility and evolution rules.
3. **Consistency** — conventions the API follows.
4. **Scope** — public / internal / event / integration.
5. **Acceptance Criteria** — contract conformance.
6. **Traceability**, **ADR References**, **Review & Completion**.

## Conventions
- State the *what* and *why*, never the *how*; name no technology, vendor, or language.
- Declare a single owning authority and the owning Handbook chapter (see the
  [Taxonomy](../SPECIFICATION_TAXONOMY.md)).
- Establish [traceability](../SPECIFICATION_TRACEABILITY.md) and pass the applicable
  [review dimensions](../SPECIFICATION_REVIEW.md) and [completion gates](../SPECIFICATION_COMPLETION.md).
