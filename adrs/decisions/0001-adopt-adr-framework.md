# ADR-0001 — Adopt the ADR engineering framework

- **Status:** Accepted — see [ADR Lifecycle](../ADR_LIFECYCLE.md)
- **Date:** 2026-07-16
- **Category:** C6 Governance & Lifecycle
- **Authority:** Architecture Board
- **Supersedes:** —
- **Superseded By:** —

## Decision
APEF governs every architecturally significant decision made from EC-1 forward through the ADR
engineering framework established in [`adrs/`](../): each such decision is recorded as a numbered
Architecture Decision Record, authored from the [ADR template](../ADR_TEMPLATE.md), classified under
one [decision category](../decision-categories/CATEGORIES.md), and taken through the
[ADR lifecycle](../ADR_LIFECYCLE.md) under [ADR governance](../ADR_GOVERNANCE.md).

## Context
Through Foundation and the subsequent milestones, architecturally significant decisions were
recorded in two places — the immutable Foundation register (`AD-0001..AD-0021`) and Board
Outstanding Decisions (`OD-1..OD-6`) scattered across milestone summaries. The Engineering Assessment
identified (gap G2) that the framework had no standing instrument for recording decisions going
forward, harming traceability and auditability. EC-1 established the ADR framework to close that gap.

## Options Considered
- **Adopt a standing ADR framework (chosen).** A single, governed instrument for all future
  significant decisions.
- **Continue extending the Foundation `AD-` register.** Rejected: the register is explicitly
  immutable and Foundation-scoped; extending it would blur Foundation's boundary.
- **Record decisions only in milestone summaries.** Rejected: the scattering this produced is the
  very problem G2 identified.

## Rationale
A dedicated, governed ADR framework makes the decision history explicit, traceable, governable, and
immutable-by-supersession, while interoperating cleanly with the Foundation register and the
Documentation Conventions standard rather than replacing them.

## Consequences
Significant decisions now require an ADR (Quality Gate G-7). The framework gains an auditable
decision log. A small authoring overhead accompanies each significant decision — accepted as the
cost of traceability.

## Affected Areas
[`adrs/`](../), the [Workflow](../../bootstrap/WORKFLOW.md), and the
[Quality Gates](../../bootstrap/QUALITY_GATES.md) (G-7).

## Migration Required
No — this decision establishes the instrument. Existing ratified decisions are handled by the
[Migration Plan](../ADR_MIGRATION_PLAN.md) (ADR-0002..ADR-0006).

## Traceability
Origin: EC-1 / gap G2 of the [Engineering Assessment](../../docs/ENGINEERING_ASSESSMENT.md),
approved by the Board (OD-9). Establishes the framework described in
[ADR_FRAMEWORK.md](../ADR_FRAMEWORK.md).
