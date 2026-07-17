# Playbooks — Repeatable Engineering Procedures

## Overview
Playbooks are step-by-step procedures for recurring engineering activities: reviews of architecture, security, performance, and observability; production-readiness assessment; and release and incident reviews.

## Purpose
To turn expert judgment into repeatable, checklist-driven practice with consistent outcomes.

## Responsibilities
- Standardize how reviews and readiness assessments are conducted.
- Encode the criteria, inputs, and outputs of each procedure.

## Contents
- [architecture-review](architecture-review/)
- [security-review](security-review/)
- [performance-review](performance-review/)
- [observability-review](observability-review/)
- [production-readiness](production-readiness/)
- [release-review](release-review/)
- [incident-review](incident-review/)

## Out of Scope
- [One-off decisions — use an ADR.](../adrs/)
- [Narrative teaching — use the handbook.](../handbook/)
- Application, API, frontend, or backend code.

## Relationships
- [Quality Gates](../bootstrap/QUALITY_GATES.md) — the gates playbooks help enforce.
- [Workflows](../execution/workflows/) — AI orchestrations that may assist these procedures.

## References
- [Master Plan](../bootstrap/MASTER_PLAN.md) — the constitution governing the framework
- [Architecture Decisions](../bootstrap/ARCHITECTURE_DECISIONS.md) — the ratified Foundation decision record

## Conventions
- Each playbook defines its trigger, prerequisites, steps, decision criteria, and the artifact it produces.
