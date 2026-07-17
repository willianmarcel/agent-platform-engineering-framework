# Execution Quality Gates

The quality gates of the APEF Execution Framework are the measurable conditions a
[workflow](WORKFLOW_CATALOG.md) stage must satisfy before it may progress. Each gate is
objective — checkable by a reviewer — and maps to a [review dimension](REVIEW_FRAMEWORK.md)
and a Handbook chapter. A stage advances only when its applicable gates pass.

> This document defines the *execution* gates for the framework's workflows. It is distinct
> from the framework-authoring gates in [`../bootstrap/QUALITY_GATES.md`](../bootstrap/QUALITY_GATES.md)
> and the Handbook's [chapter Quality Criteria](../handbook/QUALITY_CRITERIA.md).

## Process gates

Applied to the progression of work regardless of dimension.

| Gate | Measure (pass condition) |
|------|--------------------------|
| Specification-completeness | The specification satisfies its acceptance criteria; scope and constraints are explicit; open questions are zero. |
| Decision-record | Every significant decision in the stage is recorded as an ADR. |
| Definition-of-done | The stage's agreed definition-of-done criteria are all met. |
| Foundation-consistency | The effort's structure and conventions conform to the repository Foundation and Handbook. |
| Terminology | Canonical terms only; zero forbidden synonyms; new terms are glossary-linked. |

## Dimension gates

One gate per [review dimension](REVIEW_FRAMEWORK.md); each passes when its dimension's review
yields no unresolved finding above the agreed severity threshold.

| Gate | Pass condition | Handbook |
|------|----------------|----------|
| Product | Output traces to a persona, job, and outcome; no vanity capability. | [02](../handbook/02-product-thinking/CHAPTER.md) |
| Domain | Output reflects the bounded contexts and ubiquitous language; no unbounded term. | [05](../handbook/05-domain-driven-design/CHAPTER.md) |
| Architecture | Output fits the reference architecture; boundaries respected; concept ownership intact. | [06](../handbook/06-reference-architecture/CHAPTER.md) |
| Security | Threat-modeled; consistent with zero trust and defense in depth; no unresolved high-severity finding. | [15](../handbook/15-security/CHAPTER.md) |
| Runtime | Sound within runtime boundaries; persistence delegated; no execution/data leakage. | [07](../handbook/07-runtime-platform/CHAPTER.md) |
| Performance | Meets the stated architectural quality attributes; trade-offs recorded. | [06](../handbook/06-reference-architecture/CHAPTER.md) |
| Observability | Emits the required signals; SLOs defined; operationally ready. | [14](../handbook/14-observability/CHAPTER.md) |
| Testing | Software correctness verified across the appropriate levels; regression covered. | [18](../handbook/18-testing/CHAPTER.md) |
| Documentation | Follows the Writing Guide; links resolve; terminology compliant. | [21](../handbook/21-glossary/CHAPTER.md) |

## Release gates

Applied at release preparation, on top of all process and dimension gates.

| Gate | Pass condition | Handbook |
|------|----------------|----------|
| Operational-readiness | The change is observable, governable, recoverable, and understood. | [19](../handbook/19-devops/CHAPTER.md) |
| Backward-compatibility | Dependents are preserved, or change is versioned with a migration path. | [13](../handbook/13-api-platform/CHAPTER.md), [20](../handbook/20-roadmap/CHAPTER.md) |
| Release-readiness | All process, dimension, and release gates pass; the release decision is recorded. | [19](../handbook/19-devops/CHAPTER.md), [20](../handbook/20-roadmap/CHAPTER.md) |

## Gate discipline

- **Objective.** Every gate has a measurable pass condition; a gate is never "felt" to pass.
- **Blocking.** A stage does not progress while an applicable gate is unmet.
- **Owned.** Each dimension gate is owned by the dimension's [skill](SKILL_CATALOG.md); process
  and release gates are owned by the workflow's lead architect.
- **Traceable.** Every gate maps to a Handbook chapter, so its authority is explicit.
- **Extensible.** A new gate may be added only with a measurable condition and a single owner.
