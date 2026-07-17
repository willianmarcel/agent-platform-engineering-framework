# Template — Security Specification

A normative, implementation-independent template of the Security library. Copy it to author
a Security specification; every section must be populated (no placeholders) to pass the
[completeness gate](../../SPECIFICATION_COMPLETION.md).

## Required sections

1. **Intent** — what this specification requires and why.
2. **Scope** — in scope / out of scope.
3. **Constraints** — boundaries that must hold.
4. **Inputs** — the upstream specifications and material it derives from.
5. **Security Content** — the Security Specifications, Security Requirements, Trust Boundaries, Security Constraints … this specification defines.
6. **Acceptance Criteria** — measurable, marked testable or evaluable.
7. **Traceability** — bidirectional links per the framework.
8. **ADR References** — significant decisions.
9. **Review & Completion** — dimensions applied; gates passed.

## Conventions
- State intent, not implementation; name no technology.
- Declare the single owning authority (Security Architect) and the owning chapter
  ([Chapter 15](../../../handbook/15-security/CHAPTER.md)).
- Establish [traceability](../../SPECIFICATION_TRACEABILITY.md) and pass the applicable
  [reviews](../../SPECIFICATION_REVIEW.md) and [completion gates](../../SPECIFICATION_COMPLETION.md).
