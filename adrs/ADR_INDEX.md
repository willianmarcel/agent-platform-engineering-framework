# ADR Index

The registry of all Architecture Decision Records: their identifier, title, category, status, and
supersession links. This index is the fastest view of the decision log's current state; the
individual records in [`decisions/`](decisions/) hold the authoritative detail.

## How to read this index

- **ID** — the permanent `ADR-NNNN` identifier.
- **Category** — one of the [decision categories](decision-categories/CATEGORIES.md) (C1–C6).
- **Status** — a state from the [ADR Lifecycle](ADR_LIFECYCLE.md).
- **Supersedes / Superseded By** — the supersession chain, if any.

## Authored ADR records

*No `ADR-NNNN` records are authored yet.* The ADR framework has been established (this milestone,
EC-1); the first records are authored on the Board's approval of the
[Migration Plan](ADR_MIGRATION_PLAN.md), which defines the seed set and the order in which existing
ratified decisions are represented as formal ADRs.

| ID | Title | Category | Status | Supersedes | Superseded By |
|----|-------|----------|--------|------------|---------------|
| — | *(none authored yet)* | — | — | — | — |

## Existing ratified decisions (not yet formal ADRs)

The framework already contains ratified decisions recorded through other instruments. They are
**not** rewritten as ADRs by this milestone; the [Migration Plan](ADR_MIGRATION_PLAN.md) defines how
each is represented going forward, and the [Traceability Matrix](ADR_TRACEABILITY_MATRIX.md) records
their origin and affected areas.

- **Foundation Architecture Decisions** `AD-0001..AD-0021` — immutable, in
  [`../bootstrap/ARCHITECTURE_DECISIONS.md`](../bootstrap/ARCHITECTURE_DECISIONS.md).
- **Board Outstanding Decisions** `OD-1..OD-6` — recorded across milestone approvals; see the
  [Traceability Matrix](ADR_TRACEABILITY_MATRIX.md).
- **Board-initiated topology/version-control decisions** — the `governance/` module and the Version
  Control Policy; see the [Migration Plan](ADR_MIGRATION_PLAN.md).

## Maintenance

The Architecture Team updates this index on every ADR state transition, per
[ADR Governance](ADR_GOVERNANCE.md). Every authored record appears here exactly once; every
supersession link resolves in both directions.
