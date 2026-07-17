# ADR-0008 — Necessary operational playbooks for v1.0

- **Status:** Accepted — see [ADR Lifecycle](../ADR_LIFECYCLE.md)
- **Date:** 2026-07-17
- **Category:** C2 Methodology & Process
- **Authority:** Architecture Board
- **Supersedes:** —
- **Superseded By:** —

## Decision
For APEF v1.0, three playbooks are produced as complete procedures because they operationalize
framework-level governance and quality gates the framework itself defines and references:
**architecture-review**, **security-review**, and **release-review**. The other four playbook
directories — **production-readiness**, **performance-review**, **observability-review**, and
**incident-review** — remain ready-structure (contract README only) as platform-*operation* reviews
deferred to Phase 5.

## Context
The `playbooks/` module contained seven contract-README stubs. EC-2 Objective 2 directed producing
*only the playbooks that remain architecturally necessary after the Engineering Assessment*. The
review *model* is already delivered in the Execution and Specification frameworks; a playbook is
architecturally necessary only where it operationalizes a framework-level gate that is not already
operationalized and does not require a running platform to execute.

## Options Considered
- **Produce the three governance/quality playbooks; defer the four operation playbooks (chosen).**
- **Produce all seven.** Rejected: the four operation reviews (production readiness, performance,
  observability, incident) assess a running platform's behavior against live targets — they are
  adopter-operational, Phase-5 instance content, not framework-level gates.
- **Produce none; rely on the review model.** Rejected: the architecture, security, and release
  reviews are explicitly required by the Charter/ADR governance, the blocking security dimension, and
  the Release Process, and need concrete procedures to be operational.

## Rationale
Architecture-review operationalizes the Charter and ADR review; security-review operationalizes the
blocking security dimension (Chapter 15); release-review operationalizes the Release Process. These
are framework-level and executable without a running platform. The other four depend on operating a
built platform and belong to Phase 5.

## Consequences
The three necessary playbooks are complete and interlinked (architecture → security → release). The
four deferred playbooks keep their contract READMEs and are populated through use in Phase 5. The
framework is operationally complete without over-producing procedures it cannot yet exercise.

## Affected Areas
[`playbooks/`](../../playbooks/): `architecture-review/`, `security-review/`, `release-review/`
(procedures added); `production-readiness/`, `performance-review/`, `observability-review/`,
`incident-review/` (deferred).

## Migration Required
No — the three procedures are added as entry documents beside their frozen READMEs; no README is
modified.

## Traceability
Origin: EC-2 Objective 2 (Board-approved), grounded in the
[Engineering Assessment](../../docs/ENGINEERING_ASSESSMENT.md). Related:
[Release Process](../../bootstrap/RELEASE_PROCESS.md), [Quality Gates](../../bootstrap/QUALITY_GATES.md),
[Chapter 15 — Security](../../handbook/15-security/CHAPTER.md).
