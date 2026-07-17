# ADR Governance

This document defines who owns Architecture Decision Records, how they are numbered, how they are
reviewed and ratified, and how their integrity is maintained over time. It applies the authority
model of the [Architecture Charter](../governance/ARCHITECTURE_CHARTER.md) to the ADR framework.

## Ownership and authority

- The **Architecture Board** is the ratifying authority for ADRs. An ADR becomes **Accepted** only
  by Board ratification, consistent with the [Architecture Board](../governance/ARCHITECTURE_BOARD.md)
  mandate and the Foundation register's requirement that a superseding decision requires explicit
  Board ratification.
- The **Architecture Team** authors and maintains ADRs: drafting proposals, keeping the
  [Index](ADR_INDEX.md) and [Traceability Matrix](ADR_TRACEABILITY_MATRIX.md) current, and
  performing supersession bookkeeping.
- Any contributor may **propose** an ADR; authority to **accept** rests with the Board.
- Decisions that change repository topology or the governance model are Board matters by the
  Charter and must be recorded as ADRs.

## Numbering

- ADRs are numbered sequentially with a zero-padded four-digit identifier: `ADR-0001`, `ADR-0002`, …
- Numbers are assigned at **proposal** time and are **never reused or renumbered**, even if the
  proposal is rejected.
- The `ADR-` series is distinct from the Foundation `AD-` series. The Foundation register owns
  `AD-0001..AD-0021`; new ADRs begin at `ADR-0001`. The two series are kept distinct precisely so
  neither renumbers the other; the [Migration Plan](ADR_MIGRATION_PLAN.md) defines how the `AD-`
  decisions are represented in the ADR framework without altering their identifiers.
- Record files are named `NNNN-short-title.md` and live in [`decisions/`](decisions/).

## Review and ratification

An ADR proposal is reviewed against these criteria before ratification:

1. **Significance** — the decision meets the significance threshold in the
   [ADR Framework](ADR_FRAMEWORK.md); trivial or purely local choices are not ADRs.
2. **Singularity** — the record captures exactly one decision.
3. **Completeness** — every mandatory field of the [template](ADR_TEMPLATE.md) is filled with
   substance, no placeholders.
4. **Traceability** — the decision links to its origin and to the areas it affects; the
   [Traceability Matrix](ADR_TRACEABILITY_MATRIX.md) is updated.
5. **Consistency** — the decision does not silently contradict an Accepted ADR, the Handbook, or a
   ratified standard; if it changes a prior decision, it does so by explicit supersession.
6. **Category** — the decision is assigned one category from [decision-categories/](decision-categories/).

Ratification is recorded by moving the ADR to **Accepted** in both the record and the
[Index](ADR_INDEX.md). Review uses the same discipline as the framework-wide
[Review Framework](../execution/REVIEW_FRAMEWORK.md) and satisfies Quality Gate G-7 (decision
integrity) in [`../bootstrap/QUALITY_GATES.md`](../bootstrap/QUALITY_GATES.md).

## Integrity over time

- **Immutability.** Accepted ADR text is never edited; change is by supersession only (see
  [ADR Lifecycle](ADR_LIFECYCLE.md)).
- **Supersession bookkeeping.** When an ADR is superseded, the successor names what it supersedes
  and the predecessor's `Superseded By` field is set — and nothing else on the predecessor changes.
- **No orphans.** Every ADR is listed in the [Index](ADR_INDEX.md) and appears in the
  [Traceability Matrix](ADR_TRACEABILITY_MATRIX.md); every supersession link resolves in both
  directions.
- **No gaps.** The number sequence has no gaps other than rejected proposals, which remain recorded.

## Relationship to other decision instruments

The ADR framework is one of three decision instruments in APEF, each with a defined scope:

| Instrument | Scope | Home |
|-----------|-------|------|
| Foundation Architecture Decisions (`AD-`) | The immutable Foundation-phase rulings | [`../bootstrap/ARCHITECTURE_DECISIONS.md`](../bootstrap/ARCHITECTURE_DECISIONS.md) |
| Documentation Conventions (standard) | Standing documentation rules (OD-3) | [`../governance/DOCUMENTATION_CONVENTIONS.md`](../governance/DOCUMENTATION_CONVENTIONS.md) |
| Architecture Decision Records (`ADR-`) | All architecturally significant decisions from here forward | [`decisions/`](decisions/) |

Where a decision spans instruments, the ADR is authoritative for its own record and links to the
others rather than duplicating them.

## Relationships

- Applies the authority of the [Architecture Charter](../governance/ARCHITECTURE_CHARTER.md) and
  [Board](../governance/ARCHITECTURE_BOARD.md).
- Enforces [ADR Lifecycle](ADR_LIFECYCLE.md) transitions and the
  [ADR Framework](ADR_FRAMEWORK.md) principles.
- Feeds the [Index](ADR_INDEX.md) and [Traceability Matrix](ADR_TRACEABILITY_MATRIX.md).
