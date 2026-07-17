# Engineering Guide

The Engineering Guide defines the standards and practices every contribution to the Agent
Platform Engineering Framework (APEF) follows. It is the operational reference a contributor
consults to know *how* to do engineering work in this framework to the expected level of
quality. It is framework-, technology-, and implementation-neutral: it describes engineering
methodology, not tools or code.

The [Handbook](../handbook/HANDBOOK_SUMMARY.md) is the normative source of truth; this guide
tells contributors how to work within it. Where a topic has a Handbook owner, this guide points
to it rather than restating it.

## Engineering principles in practice

APEF work is judged against the engineering principles owned by
[Chapter 03 — Engineering Principles](../handbook/03-engineering-principles/CHAPTER.md):
simplicity, maintainability, evolvability, and quality by design, expressed at the engineering,
architectural, and design levels. In practice this means:

- **Prefer the simplest artifact that fully serves its purpose.** Remove accidental complexity;
  add structure only when it earns its cost.
- **Define once, reference everywhere.** Every concept has exactly one owning chapter; never
  redefine it — link to the owner.
- **Design for change.** Keep artifacts single-owned, versioned, and cross-referenced so they
  can evolve without disproportionate cost.
- **Build quality in.** Meet the quality gates continuously, not at the end.

## Specification-Driven Development

APEF practises Specification-Driven Development, owned by
[Chapter 04 — Development Methodology](../handbook/04-development-methodology/CHAPTER.md) and
operationalized by the [Specification Framework](../specifications/SPECIFICATION_FRAMEWORK.md).
Intent is captured as a specification before the work it governs proceeds. A significant piece of
work therefore begins with the appropriate specification (from the
[Specification Taxonomy](../specifications/SPECIFICATION_TAXONOMY.md)), authored from its
template, traced to its origin, and reviewed before it is accepted.

## Documentation standards

All documentation follows the [Documentation Conventions](../governance/DOCUMENTATION_CONVENTIONS.md):

- The eight-section README contract for every directory (AD-0001).
- The Module Entry Pattern: a frozen directory README plus authoritative entry documents.
- Diagrams authored as diagram-as-code (Mermaid) within the documents that use them.
- The [Writing Guide](../handbook/WRITING_GUIDE.md) chapter template and the
  [Glossary Guidelines](../handbook/GLOSSARY_GUIDELINES.md) canonical terminology.
- **No placeholders** — no `TODO`, `TBD`, or `Coming Soon`; every document is useful on merge.

## Conventions for artifacts

- **Specifications** are authored from the [Specification Library](../specifications/SPECIFICATION_LIBRARY_INDEX.md)
  templates, single-owned, and bidirectionally traceable.
- **Decisions** of architectural significance are recorded through the ADR framework in
  [`../adrs/`](../adrs/), following its lifecycle and governance.
- **Architecture** is expressed as diagram-as-code and conceptual models consistent with
  [Chapter 06 — Reference Architecture](../handbook/06-reference-architecture/CHAPTER.md) and the
  [Platform Capability Model](../handbook/PLATFORM_CAPABILITY_MODEL.md).
- **Examples** are non-executable and name no technology; **reference** material may analyze
  external technologies for educational purposes only.

## Review and definition of done

Work is reviewed through the review model owned by the
[Execution Framework](../execution/REVIEW_FRAMEWORK.md) and, for specifications, the
[Specification Review Framework](../specifications/SPECIFICATION_REVIEW.md). An artifact is
**done** only when it satisfies its definition of done: its specification (where applicable) is
met, its significant decisions are recorded as ADRs, it passes the applicable review dimensions,
and it clears the [Quality Gates](QUALITY_GATES.md).

## Relationships

- Elaborates the principles set in [`MASTER_PLAN.md`](MASTER_PLAN.md) and
  [Chapter 03](../handbook/03-engineering-principles/CHAPTER.md).
- Enforced by [`QUALITY_GATES.md`](QUALITY_GATES.md); applied through [`WORKFLOW.md`](WORKFLOW.md).
- Consistent with the [Architecture Charter](../governance/ARCHITECTURE_CHARTER.md) and the
  [Documentation Conventions](../governance/DOCUMENTATION_CONVENTIONS.md).
