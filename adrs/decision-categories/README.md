# Decision Categories

## Overview
This directory defines the classification taxonomy for Architecture Decision Records — the fixed set
of categories every ADR is assigned to.

## Purpose
To make the decision log navigable and to reveal where architectural decisions concentrate, by
classifying each ADR under exactly one category.

## Responsibilities
- Define the canonical, stable set of ADR categories.
- Provide a single owning category for every recorded decision.

## Contents
- [`CATEGORIES.md`](CATEGORIES.md) — the authoritative category definitions.

## Out of Scope
- The ADR records themselves — those live in [`../decisions/`](../decisions/).
- The lifecycle and governance of ADRs — see [`../ADR_LIFECYCLE.md`](../ADR_LIFECYCLE.md) and
  [`../ADR_GOVERNANCE.md`](../ADR_GOVERNANCE.md).

## Relationships
- [ADR Framework](../ADR_FRAMEWORK.md) — establishes why decisions are categorized.
- [ADR Index](../ADR_INDEX.md) — records each ADR's category.

## References
- [Handbook Summary](../../handbook/HANDBOOK_SUMMARY.md) — the categories align with the Handbook's
  concern areas.

## Conventions
- Categories are stable; adding or changing a category is itself an architecturally significant
  decision recorded as an ADR.
