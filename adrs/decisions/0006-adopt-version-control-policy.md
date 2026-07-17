# ADR-0006 — Adopt the Version Control Policy

- **Status:** Accepted — see [ADR Lifecycle](../ADR_LIFECYCLE.md)
- **Date:** 2026-07-16
- **Category:** C6 Governance & Lifecycle
- **Authority:** Architecture Board
- **Supersedes:** —
- **Superseded By:** —

## Decision
Version control follows the [Version Control Policy](../../governance/VERSION_CONTROL_POLICY.md):
work is committed only after Board milestone approval; one approved milestone maps to one logical
commit (Conventional Commits); and tags are applied only at publication milestones. This formalizes
the Board-initiated version-control decision.

## Context
During Publication Readiness the Board added a Version Control Policy to the governance package,
establishing that commits are gated on milestone approval and that tagging occurs only at
publication. Outstanding Decision OD-6 (commits deferred until Publication Readiness approval) is a
specific application of this policy. The policy governs how the accumulated approved work is
committed and how releases are tagged.

## Options Considered
- **Approval-gated, one-milestone-one-commit, publication-only tags (chosen).** Keeps the history
  clean, auditable, and aligned to Board approvals.
- **Commit continuously during a milestone.** Rejected by the Board: produces speculative,
  pre-approval history and blurs the approval boundary.

## Rationale
Gating commits on approval and mapping one milestone to one logical commit makes the version history
a faithful, auditable record of Board-approved increments; publication-only tags keep releases
meaningful.

## Consequences
No commit is made before its milestone is approved (this is the OD-6 gate in force through EC-2).
When the Board approves, each milestone is committed as one logical commit and publication milestones
are tagged.

## Affected Areas
[Version Control Policy](../../governance/VERSION_CONTROL_POLICY.md); every commit and tag;
repository-wide version-control practice.

## Migration Required
No — the policy is in force; this ADR records the ratified version-control decision. OD-6 remains a
process gate governed by this policy until the Board lifts it.

## Traceability
Origin: Board-initiated version-control decision during Publication Readiness; related to OD-6. See
the [Version Control Policy](../../governance/VERSION_CONTROL_POLICY.md) and the
[Traceability Matrix](../ADR_TRACEABILITY_MATRIX.md).
