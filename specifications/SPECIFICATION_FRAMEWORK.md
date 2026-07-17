# APEF Specification Framework

The Specification Framework is the normative methodology of the APEF for transforming product
intent into specified, reviewable engineering work **before implementation**. It defines how
every engineering artifact is specified, so that any software product built with the APEF —
regardless of technology, language, cloud, or AI framework — is specified the same coherent
way.

This framework extends the [Handbook](../handbook/HANDBOOK_SUMMARY.md) (the normative source of
truth) and the [Execution Framework](../.claude/EXECUTION_FRAMEWORK.md) (the engineering
operating system); it never contradicts or modifies them. It contains no implementation
guidance, no technology selection, and no programming language — it is engineering methodology
only.

> **Module entry note.** The directory README ([`README.md`](README.md)) is a frozen Foundation
> artifact and is not modified. This document is the authoritative entry point for the
> Specification Framework.

## The framework at a glance

| Concern | Document |
|---------|----------|
| Philosophy and overview | this document |
| Lifecycle and states | [SPECIFICATION_LIFECYCLE.md](SPECIFICATION_LIFECYCLE.md) |
| Categories of specification | [SPECIFICATION_TAXONOMY.md](SPECIFICATION_TAXONOMY.md) |
| Ownership and authority | [SPECIFICATION_GOVERNANCE.md](SPECIFICATION_GOVERNANCE.md) |
| Traceability | [SPECIFICATION_TRACEABILITY.md](SPECIFICATION_TRACEABILITY.md) |
| Review | [SPECIFICATION_REVIEW.md](SPECIFICATION_REVIEW.md) |
| Completion and quality gates | [SPECIFICATION_COMPLETION.md](SPECIFICATION_COMPLETION.md) |
| Relationships | [SPECIFICATION_RELATIONSHIPS.md](SPECIFICATION_RELATIONSHIPS.md) |
| Templates · Examples · Reference | [templates/](templates/) · [examples/](examples/) · [reference/](reference/) |

## Specification Philosophy

**What is a Specification?** A specification is a normative statement of *what must be true*
for an engineering artifact to be correct — its intent, scope, constraints, and acceptance
criteria — captured before, and independent of, how it is implemented. A specification
describes the *what* and the *why*; it never prescribes the *how*.

**Why specifications exist.** Specifications make intent explicit, reviewable, and traceable
at the point where change is cheapest — before implementation. They give every downstream
artifact a source of truth to satisfy, turn tacit understanding into shared commitment, and
make correctness a property that can be verified rather than assumed. This realizes the
Specification-Driven Development methodology owned by
[Chapter 04](../handbook/04-development-methodology/CHAPTER.md).

**Relationship with Product Discovery.** Discovery precedes specification: it frames the
problem, users, jobs, and outcomes (owned by
[Chapter 02](../handbook/02-product-thinking/CHAPTER.md)). A specification consumes discovery
findings and fixes them as normative intent; discovery explores, the specification commits.

**Relationship with Architecture.** A specification states what must be true; the architecture
(owned by [Chapter 06](../handbook/06-reference-architecture/CHAPTER.md)) states how the
structure satisfies it. Architecture is designed to satisfy specifications, and architecture
specifications state the constraints architecture must meet — the two are distinct and
bidirectionally traceable.

**Relationship with ADRs.** Significant choices made within or about a specification are
recorded as Architecture Decision Records (owned by
[Chapter 04](../handbook/04-development-methodology/CHAPTER.md)). A specification references the
ADRs that justify its significant decisions; an ADR references the specification it shapes.

**Relationship with Implementation.** Implementation realizes what a specification requires and
is held accountable to it. The Specification Framework produces no implementation; it produces
the intent implementation must satisfy, verified through the definition of done.

**Relationship with Testing.** Testing (owned by
[Chapter 18](../handbook/18-testing/CHAPTER.md)) verifies that an implementation satisfies its
specification's acceptance criteria for software correctness. A specification's acceptance
criteria are the source from which tests are designed.

**Relationship with Evaluation.** Evaluation (owned by
[Chapter 16](../handbook/16-evaluation/CHAPTER.md)) measures the quality of model-dependent AI
behavior against a specification's quality criteria. Evaluation and testing are distinct
disciplines, and a specification distinguishes the criteria each verifies.

**Relationship with Operations.** A specification states the operational conditions an artifact
must meet — observability and operational readiness (owned by
[Chapter 14](../handbook/14-observability/CHAPTER.md) and
[Chapter 19](../handbook/19-devops/CHAPTER.md)) — so that what is specified can be operated,
not only built.

## Principles

- **Specify before implementing.** No implementation proceeds without an approved
  specification of what it must satisfy.
- **What and why, never how.** A specification states intent, scope, constraints, and
  acceptance; it never prescribes technology or implementation.
- **One owner per specification.** Every specification has a single owning authority and a
  single owning Handbook concern.
- **Traceable in both directions.** Every specification traces to its origin and to what
  verifies it, and can be traced back from them.
- **Reviewed and gated.** A specification advances only when its reviews pass and its quality
  gates are met.
- **Technology- and framework-neutral.** The methodology is reusable across any software
  product; it names no technology, vendor, or language.

## How to use the framework

1. Determine the specification's category from the [Taxonomy](SPECIFICATION_TAXONOMY.md).
2. Author it from the matching [template](templates/), stating intent, scope, constraints, and
   acceptance criteria.
3. Establish [traceability](SPECIFICATION_TRACEABILITY.md) to its origin and verification.
4. Move it through the [lifecycle](SPECIFICATION_LIFECYCLE.md), passing
   [review](SPECIFICATION_REVIEW.md) and [completion](SPECIFICATION_COMPLETION.md) gates.
5. Govern its ownership and change per [governance](SPECIFICATION_GOVERNANCE.md).
