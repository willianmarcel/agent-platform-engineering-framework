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

The Board approved the [Migration Plan](ADR_MIGRATION_PLAN.md) (OD-9) in EC-2; the seed set below was
authored accordingly. Each record references its source decision and rewrites nothing that lives
elsewhere.

| ID | Title | Category | Status | Supersedes | Superseded By |
|----|-------|----------|--------|------------|---------------|
| [ADR-0001](decisions/0001-adopt-adr-framework.md) | Adopt the ADR engineering framework | C6 | Accepted | — | — |
| [ADR-0002](decisions/0002-creator-experience-owned-by-chapter-08.md) | Creator Experience is owned by Chapter 08 | C5 | Accepted | — | — |
| [ADR-0003](decisions/0003-chapter-17-titled-user-experience.md) | Chapter 17 is titled "User Experience" | C1 | Accepted | — | — |
| [ADR-0004](decisions/0004-adopt-module-entry-pattern.md) | Adopt the Module Entry Pattern | C1 | Accepted | — | — |
| [ADR-0005](decisions/0005-establish-governance-module.md) | Establish the `governance/` top-level module | C1 | Accepted | — | — |
| [ADR-0006](decisions/0006-adopt-version-control-policy.md) | Adopt the Version Control Policy | C6 | Accepted | — | — |
| [ADR-0007](decisions/0007-template-ownership-and-consolidation.md) | Template ownership and consolidation | C1 | Accepted | — | — |
| [ADR-0008](decisions/0008-necessary-operational-playbooks.md) | Necessary operational playbooks for v1.0 | C2 | Accepted | — | — |
| [ADR-0009](decisions/0009-establish-architecture-modeling-framework.md) | Establish the Architecture Modeling Framework | C2 | Accepted | — | — |

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
