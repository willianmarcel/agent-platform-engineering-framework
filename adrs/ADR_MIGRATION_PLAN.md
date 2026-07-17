# ADR Migration Plan

This plan defines how the ratified architectural decisions APEF already contains are represented
within the ADR framework — **without rewriting any existing decision and without inventing
historical ADRs**. It identifies every existing ratified decision, states how each is treated, and
proposes the seed set of ADR records to author on the Architecture Board's approval. Execution of
this plan is gated on Board approval; this document establishes the strategy, not the records.

## Migration principles

1. **Do not rewrite.** No existing decision's text is altered or duplicated. The Foundation
   register `AD-0001..AD-0021` remains immutable in its own document; ratified standards remain
   standards.
2. **Represent, don't reinvent.** Where an existing ratified decision is a *standing* architectural
   decision, a new ADR may be authored that **references** the original as its source (in its
   Traceability field) rather than restating it. The ADR records that the decision is now part of
   the ADR-governed log; it does not re-decide it.
3. **Preserve identity.** `AD-` and `OD-` identifiers are permanent and unchanged. New ADRs carry
   new `ADR-` identifiers and cite the originals.
4. **No back-dated fiction.** ADRs are dated to when they are authored (their entry into the ADR
   framework), not back-dated to the original decision. The original decision's date lives with the
   original record and is cited in Traceability.
5. **Gated execution.** Records are authored only after the Board approves this plan.

## Inventory of existing ratified decisions

### Foundation Architecture Decisions (`AD-0001..AD-0021`)
Immutable, in [`../bootstrap/ARCHITECTURE_DECISIONS.md`](../bootstrap/ARCHITECTURE_DECISIONS.md).

**Treatment:** *Retain in place; represent by reference.* These are not re-authored as ADR records.
They remain the authoritative, immutable Foundation register. They are entered into the
[Traceability Matrix](ADR_TRACEABILITY_MATRIX.md) with their category so the ADR log is complete.
The register's own supersession clause (§8) currently continues the `AD-` series; whether future
supersessions of a Foundation decision should be authored as `ADR-` records or continue as `AD-` is
raised as an outstanding governance question (see Outstanding Decisions in the milestone closure).

### Board Outstanding Decisions (`OD-1..OD-6`)
Recorded across milestone approvals; see the [Traceability Matrix](ADR_TRACEABILITY_MATRIX.md).

| OD | Decision | Treatment |
|----|----------|-----------|
| OD-1 | Creator Experience is owned by Chapter 08 | **Author a formal ADR** (standing concept-ownership decision). |
| OD-2 | Chapter 17 is titled "User Experience" | **Author a formal ADR** (standing structural/naming decision). |
| OD-3 | Standing documentation conventions ratified as a standard | **Keep as a standard**; reference the [Documentation Conventions](../governance/DOCUMENTATION_CONVENTIONS.md). No ADR re-records it; the ADR framework cites it. |
| OD-4 | Single authoritative home for the mandated architectural principles (deferred to Release 1.1) | **Author an ADR when resolved.** Deferred; not migrated now. |
| OD-5 | The Module Entry Pattern (frozen READMEs + entry documents) | **Author a formal ADR** (standing structural pattern). |
| OD-6 | Commits deferred until Publication Readiness approval | **No ADR** — a process/release-timing gate, not an architectural decision; governed by the [Version Control Policy](../governance/VERSION_CONTROL_POLICY.md). |

### Board-initiated topology and version-control decisions
Made during the Publication Readiness milestone; recorded in the docs assessments.

| Decision | Treatment |
|----------|-----------|
| Establish `governance/` as a top-level module (relocation of the Architecture Governance Package) | **Author a formal ADR** (repository-topology decision — a Board matter by the Charter). |
| Adopt the Version Control Policy (commit/tag timing, one-milestone-one-commit) | **Author a formal ADR** referencing the [Version Control Policy](../governance/VERSION_CONTROL_POLICY.md). |

## Proposed seed ADR set

On approval, the following ADRs are authored into [`decisions/`](decisions/), in this order. Each
references its source decision in Traceability and restates nothing that lives elsewhere.

| Proposed ID | Title | Category | Source | Status on authoring |
|-------------|-------|----------|--------|---------------------|
| ADR-0001 | Adopt the ADR engineering framework | C6 Governance & Lifecycle | This milestone (EC-1 / G2) | Accepted |
| ADR-0002 | Creator Experience is owned by Chapter 08 | C5 Cross-Cutting | OD-1 | Accepted |
| ADR-0003 | Chapter 17 is titled "User Experience" | C1 Structural & Documentation | OD-2 | Accepted |
| ADR-0004 | Adopt the Module Entry Pattern | C1 Structural & Documentation | OD-5 | Accepted |
| ADR-0005 | Establish the `governance/` top-level module | C1 Structural & Documentation | Board topology change | Accepted |
| ADR-0006 | Adopt the Version Control Policy | C6 Governance & Lifecycle | Board VC decision | Accepted |

ADR-0001 is the framework's own adoption decision and is therefore first. It is a present decision,
not a historical invention: it records that, as of EC-1, APEF governs architecturally significant
decisions through this framework.

## What is deliberately *not* migrated

- **AD-0001..AD-0021** are not re-authored; they remain immutable in the Foundation register.
- **OD-3** is not re-recorded as an ADR; the Documentation Conventions standard stands and is
  referenced.
- **OD-4** is deferred; its ADR is authored when the decision is resolved (Release 1.1).
- **OD-6** is a process gate, not an architectural decision.
- **Postponed Foundation items** (AD-0004 line-wrapping, AD-0019 NOTICE file) remain postponed in
  the register.

## Execution and sequencing

1. Board approves this plan.
2. The Architecture Team authors ADR-0001 (adopt framework), then ADR-0002..ADR-0006 for the
   standing decisions above, each from the [template](ADR_TEMPLATE.md).
3. The [Index](ADR_INDEX.md) and [Traceability Matrix](ADR_TRACEABILITY_MATRIX.md) are updated as
   each record is authored.
4. The Board rules on the `AD-` vs `ADR-` supersession-continuity question (Outstanding Decision)
   so that any future supersession of a Foundation decision has an unambiguous instrument.

## Relationships

- Established by the [ADR Framework](ADR_FRAMEWORK.md); governed by [ADR Governance](ADR_GOVERNANCE.md).
- References the Foundation [Architecture Decisions](../bootstrap/ARCHITECTURE_DECISIONS.md) and the
  [Documentation Conventions](../governance/DOCUMENTATION_CONVENTIONS.md).
- Feeds the [Traceability Matrix](ADR_TRACEABILITY_MATRIX.md).
