# ADR-0003 — Chapter 17 is titled "User Experience"

- **Status:** Accepted — see [ADR Lifecycle](../ADR_LIFECYCLE.md)
- **Date:** 2026-07-16
- **Category:** C1 Structural & Documentation
- **Authority:** Architecture Board
- **Supersedes:** —
- **Superseded By:** —

## Decision
Handbook Chapter 17 is titled **"User Experience"** (not "UI/UX"). This formalizes Board Outstanding
Decision **OD-2** within the ADR framework.

## Context
Chapter 17 was originally planned as "UI/UX". During authoring it was determined that the chapter's
subject is the platform's user experience at architectural altitude, not visual/interface design;
the Board renamed the chapter title to "User Experience" as OD-2. The chapter directory remains
`handbook/17-ui-ux/` (a frozen structural path that is not renamed), and the frozen Table of Contents
still lists the original label.

## Options Considered
- **Title "User Experience" (chosen).** Matches the chapter's architectural-altitude content.
- **Retain "UI/UX".** Rejected: implies interface/visual-design scope the chapter deliberately does
  not cover.

## Rationale
The title must describe the chapter's actual subject. "User Experience" is accurate; "UI/UX" implies
implementation-level interface concerns outside the framework's altitude.

## Consequences
The chapter is referred to as "User Experience" throughout new content. A residual label discrepancy
remains in frozen artifacts (the directory name `17-ui-ux/` and the frozen Table of Contents entry),
recorded as an outstanding reconciliation for a governed correction — not resolved here, because
frozen Handbook artifacts are not modified in this milestone.

## Affected Areas
[Chapter 17](../../handbook/17-ui-ux/) and the Handbook Table of Contents.

## Migration Required
Partial — the title decision stands; reconciling the frozen directory name and Table-of-Contents
label is a governed correction the Board directs separately (tracked in the EC-2 Outstanding
Decisions). No frozen artifact is modified by this ADR.

## Traceability
Origin: OD-2, ratified by the Board; see the
[Traceability Matrix](../ADR_TRACEABILITY_MATRIX.md) and the Engineering Assessment finding on the
title/TOC discrepancy. Formalized under the [Migration Plan](../ADR_MIGRATION_PLAN.md).
