# Template — Base Specification

The canonical **base template** for every normative Specification-Driven Development artifact in APEF
(AD-0012). All specialized specification templates — the Specification Library's category templates
and the extension templates registered in [`TEMPLATE_OWNERSHIP.md`](../TEMPLATE_OWNERSHIP.md) —
extend this base by refining the *Body* section for their category. Copy it to author a
specification; every section must be populated (no placeholders) to pass the
[completeness gate](../../specifications/SPECIFICATION_COMPLETION.md).

Author the *what* and the *why*, never the *how*. Name no technology, vendor, product, or language.

---

## 1. Identity
- **Title** — the specification's name, from the subject's point of view.
- **Category** — one category from the [Specification Taxonomy](../../specifications/SPECIFICATION_TAXONOMY.md).
- **Owning authority** — the single role or body accountable for this specification.
- **Owning Handbook chapter** — the chapter that owns the concepts this specification realizes.
- **Status** — Draft | In Review | Accepted | Superseded.

## 2. Purpose & Scope
- **Purpose** — the outcome this specification exists to secure.
- **In scope** — what this specification governs.
- **Out of scope** — what it deliberately does not govern.

## 3. Context
The background and drivers: the need, the constraints, and the relevant prior decisions. State
facts, not solutions.

## 4. Body *(specialized per category)*
The normative content of the specification. Each specialized template refines this section into the
required structure for its category (for example, a capability template specifies Jobs & Outcomes; a
domain template specifies the domain model; a runtime template specifies runtime requirements). At
the base level, the Body states the requirements as clear, verifiable, implementation-independent
statements.

## 5. Inputs, Outputs & Dependencies
- **Inputs** — what the subject consumes.
- **Outputs** — what it produces.
- **Dependencies** — upstream sources and downstream consumers, as links.

## 6. Acceptance Criteria
Measurable, verifiable criteria that determine whether the specification is satisfied. Each criterion
is testable without reference to any implementation.

## 7. Traceability
Links to the specification's origin (vision, discovery, capability, or decision) and to the artifacts
it informs, per the [Traceability model](../../specifications/SPECIFICATION_TRACEABILITY.md).

## 8. ADR References
Links to the [ADRs](../../adrs/) that record decisions this specification depends on or realizes.

## 9. Review & Completion
The applicable [review dimensions](../../specifications/SPECIFICATION_REVIEW.md) and the
[completion gate](../../specifications/SPECIFICATION_COMPLETION.md) this specification must pass
before acceptance.

---

## Conventions
- State the *what* and *why*, never the *how*; name no technology, vendor, product, or language.
- Declare a single owning authority and one owning Handbook chapter.
- Populate every section — no placeholders (completeness gate).
- A specialized template extends this base by refining Section 4 (Body); it does not remove base
  sections.
