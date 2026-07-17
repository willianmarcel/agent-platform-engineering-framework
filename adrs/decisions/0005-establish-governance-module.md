# ADR-0005 — Establish the `governance/` top-level module

- **Status:** Accepted — see [ADR Lifecycle](../ADR_LIFECYCLE.md)
- **Date:** 2026-07-16
- **Category:** C1 Structural & Documentation
- **Authority:** Architecture Board
- **Supersedes:** —
- **Superseded By:** —

## Decision
The Architecture Governance Package is a dedicated top-level module, [`governance/`](../../governance/),
holding the Charter, Board, Operating Model, Escalation Policy, Team Operating Rules, Version Control
Policy, and Documentation Conventions. This formalizes the Board-initiated repository-topology change
made during the Publication Readiness milestone.

## Context
The governance artifacts were originally placed under `architecture/`. During Publication Readiness
the Board relocated them into a new top-level `governance/` module and added a Version Control Policy
and an expanded Charter. The Architecture Team detected the relocation, adapted all navigation, and
added a contract README. Repository-topology changes are Board matters under the Charter; this ADR
records the decision formally.

## Options Considered
- **Dedicated `governance/` top-level module (chosen).** Governance is a first-class concern,
  separate from architectural models.
- **Keep governance under `architecture/`.** Rejected by the Board: conflated governance with
  structural architecture and buried it beneath a models directory.

## Rationale
Governance (authority, process, versioning, conventions) is a distinct top-level concern deserving
its own module, discoverable and separate from the `architecture/` models directory.

## Consequences
The repository has a fourteenth top-level module. All cross-references resolve to `governance/`. The
Charter designates repository-topology and governance-model changes as Board matters.

## Affected Areas
[`governance/`](../../governance/) and every artifact that references the governance package;
repository topology.

## Migration Required
No — the relocation and all inbound links were completed during Publication Readiness; this ADR
records the ratified topology decision.

## Traceability
Origin: Board-initiated topology change during Publication Readiness; see
[Publication Readiness](../../docs/PUBLICATION_READINESS.md),
[Final Architecture Review](../../docs/FINAL_ARCHITECTURE_REVIEW.md), and the
[Traceability Matrix](../ADR_TRACEABILITY_MATRIX.md).
