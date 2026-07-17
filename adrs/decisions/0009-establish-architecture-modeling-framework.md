# ADR-0009 — Establish the Architecture Modeling Framework

- **Status:** Accepted — see [ADR Lifecycle](../ADR_LIFECYCLE.md)
- **Date:** 2026-07-17
- **Category:** C2 Methodology & Process
- **Authority:** Architecture Board
- **Supersedes:** —
- **Superseded By:** —

## Decision
The [`architecture/`](../../architecture/) module is the **Architecture Modeling Framework** of APEF:
the canonical methodology for how architecture is modeled, represented, reviewed, and communicated. It
is defined by [`ARCHITECTURE_MODELING_FRAMEWORK.md`](../../architecture/ARCHITECTURE_MODELING_FRAMEWORK.md)
and eight discipline entry documents (`c4`, `deployment`, `event-storming`, `integrations`, `network`,
`runtime`, `sequences`, `state-machines`). It owns **modeling methodology only** and references the
architectural, domain, and platform **concepts** owned by the Handbook, never redefining them.

## Context
The `architecture/` module was reserved from Foundation as the modeling layer but held only contract
READMEs. EC-3 directed designing and implementing the complete Architecture Modeling Framework as the
final engineering capability before v1.0, complementing — never duplicating — the Handbook,
Specifications, Execution Framework, ADR Library, Reference Studies, and Worked Examples.

## Options Considered
- **A methodology framework that owns modeling and references Handbook concepts (chosen).**
- **A diagram collection.** Rejected: the Board explicitly scoped the module as methodology, not
  diagrams; AD-0008 already removed the catch-all.
- **Redefine architectural concepts locally for modeling.** Rejected: would create multiple concept
  owners, violating concept single-ownership.

## Rationale
Architectural modeling is a distinct discipline needing consistent methodology. Owning the *method*
while referencing Handbook-owned *concepts* mirrors the Specification Framework's separation, keeps
concept ownership single, and makes models consistent, traceable, and neutral.

## Consequences
The framework gains a modeling methodology layer with one consistent structure across eight
disciplines, model quality gates, and cross-module integration. No new architectural principle is
introduced (modeling principles derive from Chapter 03). The `c4` module defines the canonical view
model including Deployment and Dynamic view *types*, while — per AD-0010 — those view *artifacts* are
modeled in `deployment/`, `sequences/`, and `state-machines/` (see Outstanding Decisions OD-13).

## Affected Areas
[`architecture/`](../../architecture/) and its eight modules; references to the Handbook,
Specifications, Execution Framework, and ADR Library.

## Migration Required
No — the framework is added as entry documents beside frozen READMEs (Module Entry Pattern); no frozen
README, Handbook chapter, Foundation artifact, Concept Ownership, or the PCM is modified.

## Traceability
Origin: EC-3 (Board-authorized). Consistent with AD-0008 (no catch-all), AD-0010 (C4 directory scope),
AD-0011 (event storming placement) in the Foundation
[Architecture Decisions](../../bootstrap/ARCHITECTURE_DECISIONS.md). Recorded in the
[Traceability Matrix](../ADR_TRACEABILITY_MATRIX.md).
