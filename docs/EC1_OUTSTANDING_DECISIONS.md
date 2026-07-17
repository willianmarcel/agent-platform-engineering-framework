# EC-1 — Outstanding Decisions

Decisions that EC-1 surfaces for the Architecture Board. Following the "surface, don't silently
resolve" discipline, the Architecture Team records these rather than deciding them unilaterally. They
carry forward the existing OD series (OD-1..OD-6); EC-1 raises OD-7 through OD-9. Prior ODs are
recapped for continuity.

## New — raised by EC-1

### OD-7 — `adrs/` internal structure vs the frozen directory README
- **Question:** The EC-1-mandated structure places ADR records in [`../adrs/decisions/`](../adrs/decisions/)
  and the taxonomy in [`../adrs/decision-categories/`](../adrs/decision-categories/). The frozen
  [`adrs/README.md`](../adrs/README.md) illustrates records living at the directory root (e.g.,
  `0001-record-architecture-decisions.md`). This is an **addition** consistent with the Module Entry
  Pattern, not a contradiction — but it extends what the frozen README depicts.
- **Ask:** Acknowledge the `decisions/` and `decision-categories/` subdirectories as the record and
  taxonomy homes. No modification of the frozen README is proposed; if the Board wishes the README's
  illustrative example updated, that is a governed change the Board would direct.
- **Recommendation:** Acknowledge as-is (the frozen README's "Contents" is not violated; records are
  still numbered ADR documents, now organized in `decisions/`).

### OD-8 — `AD-` vs `ADR-` supersession continuity
- **Question:** The Foundation register's immutability clause (§8) says a superseding decision takes
  "the next available identifier (AD-0022, …)". The ADR framework introduces the `ADR-` series for
  all decisions from EC-1 forward. When a **Foundation** decision must someday be superseded, does the
  successor continue the `AD-` series (per the frozen register) or become an `ADR-` record (per the
  new framework)?
- **Ask:** Rule on the instrument for future supersession of Foundation decisions.
- **Recommendation:** Author future supersessions as `ADR-` records that reference the superseded
  `AD-`, keeping one forward-looking instrument while honoring the frozen register (which is not
  edited; its `Superseded By` field simply points to an `ADR-`). The register's §8 wording is
  satisfied in spirit — supersession by a new, higher-identified record — with the series unified
  going forward.

### OD-9 — Authorize execution of the ADR Migration Plan
- **Question:** The [Migration Plan](../adrs/ADR_MIGRATION_PLAN.md) proposes six seed ADRs. They are
  **not** authored (gated on approval).
- **Ask:** Approve the plan and authorize authoring ADR-0001..ADR-0006 as specified.
- **Recommendation:** Approve; author on the same approval that ratifies EC-1.

## Carried forward — prior ODs

- **OD-1 — Creator Experience owned by Chapter 08.** Standing; proposed as seed **ADR-0002**.
- **OD-2 — Chapter 17 titled "User Experience".** Standing; proposed as seed **ADR-0003**. *Note:*
  the chapter directory remains `handbook/17-ui-ux/`; the Engineering Assessment (finding G6) flagged
  that the frozen Table of Contents still lists "UI/UX". This title-vs-TOC reconciliation is a Low
  item best handled together with authoring ADR-0003.
- **OD-3 — Documentation Conventions standard.** Discharged; remains a standard, referenced by the
  ADR framework. No ADR.
- **OD-4 — Single home for the mandated architectural principles.** Deferred to Release 1.1; an ADR
  is authored when resolved.
- **OD-5 — Module Entry Pattern.** Standing; proposed as seed **ADR-0004**.
- **OD-6 — Commits deferred.** Process gate under the [Version Control Policy](../governance/VERSION_CONTROL_POLICY.md);
  no commit performed in EC-1. Remains in force until the Board lifts it.

## Summary

| OD | Status | Disposition sought |
|----|--------|--------------------|
| OD-1, OD-2, OD-5 | Standing | Formalize as seed ADRs (part of OD-9) |
| OD-3 | Discharged | None |
| OD-4 | Deferred (1.1) | None now |
| OD-6 | In force | Remains until Board lifts |
| OD-7 | New | Acknowledge `adrs/` structure |
| OD-8 | New | Rule on supersession continuity |
| OD-9 | New | Authorize migration execution |
