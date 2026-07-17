# ADR Records

## Overview
This directory holds the authored Architecture Decision Records — one file per accepted, proposed,
rejected, superseded, or deprecated decision.

## Purpose
To be the single home of the framework's ADR records, so the decision log is in one place and each
decision is one addressable document.

## Responsibilities
- Hold every ADR record as `NNNN-short-title.md`, authored from the ADR template.
- Preserve superseded and rejected records for history, clearly marked by status.

## Contents
- Numbered ADR record files (for example, `0001-adopt-adr-framework.md`).

## Out of Scope
- The framework, lifecycle, governance, template, index, categories, and migration documents — those
  live one level up in [`../`](../).
- The immutable Foundation decisions — those remain in
  [`../../bootstrap/ARCHITECTURE_DECISIONS.md`](../../bootstrap/ARCHITECTURE_DECISIONS.md).

## Relationships
- [ADR Template](../ADR_TEMPLATE.md) — the form each record starts from.
- [ADR Index](../ADR_INDEX.md) — the registry that lists every record here.
- [ADR Governance](../ADR_GOVERNANCE.md) — the numbering and ratification rules.

## References
- [ADR Framework](../ADR_FRAMEWORK.md) — the establishing document for this module.

## Conventions
- Records are numbered sequentially and never renumbered; once Accepted, a record's body is
  immutable and changes only by supersession (status fields excepted).
