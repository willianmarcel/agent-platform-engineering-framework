# Procedure — Release Review

A repeatable procedure for reviewing a release candidate before it is cut and published. It
operationalizes the [Release Process](../../bootstrap/RELEASE_PROCESS.md) and is the review the
process requires before a version is tagged. It is technology-neutral and describes method, not
tooling.

## Trigger
Run this review when a release candidate is proposed — that is, when one or more approved milestones
are to be consolidated into a published version.

## Inputs
- The release scope: the approved milestones the release consolidates.
- The [Quality Gates](../../bootstrap/QUALITY_GATES.md) results across that scope.
- The [CHANGELOG](../../CHANGELOG.md) draft and the [Roadmap](../../bootstrap/ROADMAP.md) position.
- The [Version Control Policy](../../governance/VERSION_CONTROL_POLICY.md).

## Steps
1. **Confirm scope.** Verify every item in scope traces to a Board-approved milestone; nothing
   unapproved is included.
2. **Verify gates.** Confirm all eight [Quality Gates](../../bootstrap/QUALITY_GATES.md) pass across
   the release scope — completeness, single-ownership, links, neutrality, traceability, decision
   integrity, structural conformance, consistency.
3. **Confirm required reviews.** Verify the [Architecture Review](../architecture-review/PROCEDURE.md)
   and, where applicable, the [Security Review](../security-review/PROCEDURE.md) have passed for the
   scope.
4. **Classify the version.** Determine the Semantic Version increment (major/minor/patch) from the
   nature of the changes; confirm breaking changes are recorded as superseding ADRs.
5. **Verify communication.** Confirm the CHANGELOG accurately states additions, changes, and any
   breaking change, each traceable to its milestone and ADRs.
6. **Decide.** Recommend cut/tag or hold, with rationale, for the Board's release decision.

## Decision criteria
Recommend the release only when scope is fully approved, all gates pass, required reviews have
passed, the version increment is correct, and the CHANGELOG is accurate. Any failing gate holds the
release.

## Outputs
- A recommendation: **ready to cut** or **hold (with reasons)**.
- The confirmed Semantic Version and CHANGELOG entry.
- A record suitable for the Board's release decision and the release manifest under
  [`docs/`](../../docs/).

## Gates enforced
All eight [Quality Gates](../../bootstrap/QUALITY_GATES.md) across the release scope.

## Relationships
- Operationalizes the [Release Process](../../bootstrap/RELEASE_PROCESS.md) and the
  [Version Control Policy](../../governance/VERSION_CONTROL_POLICY.md).
- Consumes the [Architecture Review](../architecture-review/PROCEDURE.md) and
  [Security Review](../security-review/PROCEDURE.md) outcomes.
