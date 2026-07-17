# ADR Engineering Framework

This document establishes the Architecture Decision Record (ADR) engineering framework for APEF —
its purpose, philosophy, structure, and the rules that make recorded decisions durable, traceable,
and governable. It is the authoritative entry document for the `adrs/` module; the frozen
[`README.md`](README.md) is the directory contract, and this document, together with its siblings,
carries the framework's substance under the Module Entry Pattern (OD-5).

## Purpose

An ADR captures a single architecturally significant decision — its context, the options weighed,
the choice made, and its consequences — so that future engineers understand *why* the framework is
shaped the way it is. The ADR framework exists to make the framework's decision history:

- **Explicit** — every significant choice is written down, not implied by the artifacts it produced.
- **Traceable** — each decision links to its origin and to everything it affects.
- **Governable** — decisions move through a defined lifecycle under defined ownership.
- **Immutable-by-supersession** — a decision is never rewritten; it is superseded, preserving the
  full history.

## Philosophy

The ADR framework inherits the principles the Architecture Board set for the Foundation register in
[`../bootstrap/ARCHITECTURE_DECISIONS.md`](../bootstrap/ARCHITECTURE_DECISIONS.md) and generalizes
them to all future decisions:

1. **One decision, one record.** Each ADR captures exactly one decision. Compound decisions are
   split so each can be superseded independently.
2. **Permanent identifiers.** ADR numbers are assigned sequentially and never reused or
   renumbered. An identifier outlives the decision it names.
3. **Immutable text.** Once accepted, an ADR's body is not edited. Change happens only by
   authoring a new ADR that supersedes it and setting the old record's `Superseded By` field.
4. **Significance threshold.** Only architecturally significant decisions become ADRs — those that
   are costly to reverse, affect structure or cross-cutting concerns, set a precedent, or bind
   multiple areas. Reversible, local choices do not.
5. **Continuity with Foundation.** The ADR field set mirrors the Foundation AD fields, so the
   `AD-` register and the `ADR-` records form one continuous, comparable decision log.

## What is architecturally significant

A decision warrants an ADR when it does one or more of the following: changes the repository
topology or a module boundary; redefines or relocates concept ownership; establishes or changes a
mandated principle, convention, or gate; sets a precedent other decisions will follow; is costly or
disruptive to reverse; or binds multiple modules or cross-cutting concerns. When in doubt, record
it — an unnecessary ADR costs little; an unrecorded significant decision costs traceability.

## Module structure

| Artifact | Role |
|----------|------|
| [`README.md`](README.md) | Frozen directory contract (eight-section, Module Entry Pattern). |
| [`ADR_FRAMEWORK.md`](ADR_FRAMEWORK.md) | This document — purpose, philosophy, structure. |
| [`ADR_LIFECYCLE.md`](ADR_LIFECYCLE.md) | States, transitions, supersession, retirement. |
| [`ADR_GOVERNANCE.md`](ADR_GOVERNANCE.md) | Ownership, numbering, review, authority. |
| [`ADR_TEMPLATE.md`](ADR_TEMPLATE.md) | The canonical form every ADR is authored from. |
| [`ADR_INDEX.md`](ADR_INDEX.md) | The registry of all ADRs and their status. |
| [`ADR_MIGRATION_PLAN.md`](ADR_MIGRATION_PLAN.md) | How existing ratified decisions become formal ADRs. |
| [`ADR_TRACEABILITY_MATRIX.md`](ADR_TRACEABILITY_MATRIX.md) | Decision → origin → affected-area mapping. |
| [`decision-categories/`](decision-categories/) | The classification taxonomy for ADRs. |
| [`decisions/`](decisions/) | Where authored ADR records live (`NNNN-short-title.md`). |

## Relationship to the Foundation register and to the Documentation Conventions

The Foundation [`ARCHITECTURE_DECISIONS.md`](../bootstrap/ARCHITECTURE_DECISIONS.md) is an immutable
register of the Foundation-phase decisions (AD-0001..AD-0021). It remains the authoritative home of
those decisions; the ADR framework does **not** rewrite them. Standing conventions ratified as the
[Documentation Conventions](../governance/DOCUMENTATION_CONVENTIONS.md) standard (OD-3) likewise
remain a standard, not ADRs. The ADR framework governs decisions **from here forward** and provides
the migration path (see the [Migration Plan](ADR_MIGRATION_PLAN.md)) by which existing ratified
decisions are represented as formal ADRs without altering their originals.

## Relationships

- Governed by the [Architecture Charter](../governance/ARCHITECTURE_CHARTER.md) and the
  [Architecture Board](../governance/ARCHITECTURE_BOARD.md).
- Invoked from the [Workflow](../bootstrap/WORKFLOW.md) whenever a significant decision is made and
  enforced by the [Quality Gates](../bootstrap/QUALITY_GATES.md) (G-7, decision integrity).
- Consistent with the [Documentation Conventions](../governance/DOCUMENTATION_CONVENTIONS.md) and
  the Foundation [Architecture Decisions](../bootstrap/ARCHITECTURE_DECISIONS.md).
