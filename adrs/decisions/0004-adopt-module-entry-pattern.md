# ADR-0004 — Adopt the Module Entry Pattern

- **Status:** Accepted — see [ADR Lifecycle](../ADR_LIFECYCLE.md)
- **Date:** 2026-07-16
- **Category:** C1 Structural & Documentation
- **Authority:** Architecture Board
- **Supersedes:** —
- **Superseded By:** —

## Decision
Every module in the repository follows the **Module Entry Pattern**: the directory `README.md` is a
frozen eight-section contract that is never modified after freezing, and the module's authoritative
content lives in named **entry documents** authored beside it (for example `HANDBOOK.md`,
`CHAPTER.md`, `*_SPECIFICATIONS.md`, `ADR_FRAMEWORK.md`). This formalizes Board Outstanding Decision
**OD-5** within the ADR framework.

## Context
Repeatedly across milestones, a tension arose between Board instructions to "create" or "modify" a
module's README and the rule that Foundation-frozen READMEs are immutable. The resolution — never
overwrite a frozen README; add entry documents beside it — was ratified as OD-5 and applied
framework-wide. The ADR framework itself is delivered this way (frozen `adrs/README.md` plus
`ADR_FRAMEWORK.md` and siblings).

## Options Considered
- **Frozen README + entry documents (chosen).** Preserves the immutable directory contract while
  allowing content to grow.
- **Edit READMEs in place as content grows.** Rejected: violates the frozen-artifact rule and the
  eight-section contract's stability.
- **Put all content in the README.** Rejected: overloads the directory contract and breaks the
  eight-section shape.

## Rationale
The pattern reconciles two firm requirements — immutable directory contracts (AD-0001) and growing
module content — by separating the contract (README) from the substance (entry documents).

## Consequences
Frozen READMEs remain stable and mechanically checkable; module substance evolves in entry documents.
Contributors know to look past the README to the entry documents for authoritative content.

## Affected Areas
All modules with a frozen `README.md`, repository-wide.

## Migration Required
No — the pattern is already applied across the framework; this ADR records the ratified pattern in
the decision log.

## Traceability
Origin: OD-5, ratified by the Board; see the
[Traceability Matrix](../ADR_TRACEABILITY_MATRIX.md). Consistent with AD-0001 (README contract) in
the Foundation [Architecture Decisions](../../bootstrap/ARCHITECTURE_DECISIONS.md).
