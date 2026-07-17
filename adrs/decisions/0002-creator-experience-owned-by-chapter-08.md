# ADR-0002 — Creator Experience is owned by Chapter 08

- **Status:** Accepted — see [ADR Lifecycle](../ADR_LIFECYCLE.md)
- **Date:** 2026-07-16
- **Category:** C5 Cross-Cutting Concerns
- **Authority:** Architecture Board
- **Supersedes:** —
- **Superseded By:** —

## Decision
The **Creator Experience** concept is owned by Handbook Chapter 08 (Builder Platform). Chapter 17
(User Experience) references it but does not define it. This formalizes Board Outstanding Decision
**OD-1** within the ADR framework.

## Context
During the Handbook authoring (Sprint 04), a concept-ownership conflict was surfaced between
Chapter 08 and Chapter 17 over the Creator Experience concept. The Board resolved it as OD-1,
assigning ownership to Chapter 08. The decision was recorded in milestone summaries; the ADR
framework now represents it as a formal, discoverable record without altering the frozen chapters.

## Options Considered
- **Chapter 08 owns Creator Experience (chosen).** The builder/creator is the subject of the Builder
  Platform chapter.
- **Chapter 17 owns it.** Rejected by the Board: Chapter 17 concerns the end-user experience;
  placing creator concerns there would split builder ownership across two chapters.

## Rationale
Single concept ownership requires exactly one owning chapter. The creator is a first-class subject of
the Builder Platform (Chapter 08); Chapter 17 consumes the concept for the experience layer.

## Consequences
Concept single-ownership holds framework-wide (220 concepts, zero duplicates). Chapter 17 references
Chapter 08 for Creator Experience rather than redefining it.

## Affected Areas
[Chapter 08](../../handbook/08-builder-platform/), [Chapter 17](../../handbook/17-ui-ux/).

## Migration Required
No — the frozen chapters already reflect this ownership; this ADR represents the ratified decision in
the ADR log. No chapter is modified.

## Traceability
Origin: OD-1, ratified by the Board; see the
[Traceability Matrix](../ADR_TRACEABILITY_MATRIX.md). Formalized under the
[Migration Plan](../ADR_MIGRATION_PLAN.md).
