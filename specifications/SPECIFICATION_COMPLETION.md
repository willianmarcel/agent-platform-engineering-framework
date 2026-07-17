# Specification Completion

A specification is complete only when it passes every applicable quality gate below. Each gate
is **measurable** — checkable by a reviewer, never a matter of opinion. Completion is the
condition for a specification to move from **Under Review** to **Approved** in the
[lifecycle](SPECIFICATION_LIFECYCLE.md). This is part of the
[Specification Framework](SPECIFICATION_FRAMEWORK.md).

## Specification quality gates

| Gate | Measure (pass condition) |
|------|--------------------------|
| **Completeness** | Every section required by the category [template](templates/) is present and populated; zero `TODO`/`TBD`. |
| **Consistency** | No statement contradicts another within the specification or any specification it references. |
| **Correctness** | Every claim is verifiable through stated acceptance criteria; no unverifiable assertion. |
| **Traceability** | Every applicable trace link from [Traceability](SPECIFICATION_TRACEABILITY.md) is present and bidirectional. |
| **Review coverage** | Every applicable [review dimension](SPECIFICATION_REVIEW.md) has been assessed and passed. |
| **Ownership** | Exactly one owning authority and one owning Handbook concern are named. |
| **Non-duplication** | No concept owned elsewhere is redefined; references are used instead. |
| **Architectural alignment** | Consistent with the reference architecture and the Platform Capability Model; no boundary breach. |
| **Governance compliance** | Authorities, change rules, and versioning conform to [Governance](SPECIFICATION_GOVERNANCE.md). |
| **Maintainability** | The specification is structured for change: single-owned, versioned, and cross-referenced. |
| **Testability** | Every software-correctness acceptance criterion is expressed so a test can verify it. |
| **Evaluability** | Every AI-quality criterion is expressed so an evaluation can measure it. |
| **Operational readiness** | The operational conditions the artifact must meet are stated and measurable. |

Gates apply where relevant to the category: for example, *Evaluability* applies to
specifications with model-dependent behavior, and *Testability* to those with deterministic
behavior; both may apply.

## Completion criteria

A specification is **complete and approvable** when:

1. All applicable quality gates above pass.
2. All applicable review dimensions have a passing verdict.
3. All applicable traceability links exist and are bidirectional.
4. The completion is recorded and attributed to the approval authority.

## Completion checklist

- [ ] All template sections present and populated; no placeholders (Completeness).
- [ ] No internal or cross-specification contradiction (Consistency).
- [ ] Every claim is verifiable (Correctness).
- [ ] All applicable trace links present and bidirectional (Traceability).
- [ ] All applicable review dimensions passed (Review coverage).
- [ ] Single owning authority and Handbook concern named (Ownership).
- [ ] No concept redefined; references used (Non-duplication).
- [ ] Consistent with the reference architecture (Architectural alignment).
- [ ] Authorities and change rules conform (Governance compliance).
- [ ] Structured for change (Maintainability).
- [ ] Correctness criteria are testable (Testability).
- [ ] AI-quality criteria are measurable (Evaluability).
- [ ] Operational conditions stated and measurable (Operational readiness).

## Gate discipline

- **Measurable.** Every gate has an objective pass condition; no gate is "felt" to pass.
- **Applicable-only.** A gate applies where the category warrants it; non-applicability is
  recorded, not assumed.
- **Blocking.** A specification is not approved while any applicable gate is unmet.
- **Owned.** Each gate is owned by the corresponding review dimension's authority.
