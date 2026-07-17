# Governance — Architecture Governance Package

## Overview
This directory holds the Architecture Governance Package: the Charter, Board, Operating Model,
Escalation Policy, Team Operating Rules, Version Control Policy, and Documentation Conventions
that govern how the Agent Platform Engineering Framework is built, reviewed, evolved, and
published. The Foundation, Handbook, and all ratified artifacts remain the normative source of
truth; this package governs the *process* by which the framework is produced.

## Purpose
To make the framework's governance — authority, decision boundaries, escalation, lifecycle, and
repository governance — explicit, auditable, and consistently applied.

## Responsibilities
- Define the Architecture Team's authority, constraints, and execution model.
- Define the escalation conditions and the milestone lifecycle.
- Define version-control and documentation standards for the framework.

## Contents
- [Architecture Charter](ARCHITECTURE_CHARTER.md) — authority, constraints, lifecycle, and governance.
- [Architecture Board](ARCHITECTURE_BOARD.md) — the governing authority.
- [Architecture Operating Model](ARCHITECTURE_OPERATING_MODEL.md) — how the Team operates.
- [Architecture Escalation](ARCHITECTURE_ESCALATION.md) — mandatory and optional escalation.
- [Team Operating Rules](TEAM_OPERATING_RULES.md) — how the Team behaves as a senior organization.
- [Version Control Policy](VERSION_CONTROL_POLICY.md) — commit and tagging governance.
- [Documentation Conventions](DOCUMENTATION_CONVENTIONS.md) — the documentation standard.

## Out of Scope
- Normative framework content — that lives in the [`../handbook/`](../handbook/), [`../specifications/`](../specifications/), and the other modules.
- Application code, executable automation, or technology prescription.

## Relationships
- [Master Plan](../bootstrap/MASTER_PLAN.md) and [Architecture Decisions](../bootstrap/ARCHITECTURE_DECISIONS.md) — the frozen constitution this package operates under.
- [Framework Map](../docs/FRAMEWORK_MAP.md) — where this module sits in the framework.

## References
- [Architecture Charter](ARCHITECTURE_CHARTER.md) — the entry point to the governance model.

## Conventions
- Governance documents are authoritative; changes to them are Architecture Board decisions.
- This README documents the module; it does not itself establish governance.
