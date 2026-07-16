# Specifications — Specification-Driven Development Artifacts

## Overview
This directory holds the normative Specification-Driven Development artifacts of the framework: precise statements of what must be true, detailed enough to drive architecture, implementation, and evaluation in later phases.

## Purpose
To capture agreed intent as versioned, normative specifications that serve as the source of truth for downstream work.

## Responsibilities
- Record vision, domains, capabilities, runtime, security, observability, UI, and release specifications.
- Sequence work through discovery, backlog, roadmap, and releases.

## Contents
- [vision](vision/)
- [discovery](discovery/)
- [domains](domains/)
- [capabilities](capabilities/)
- [runtime](runtime/)
- [architecture-requirements](architecture-requirements/)
- [security](security/)
- [observability](observability/)
- [ui](ui/)
- [roadmap](roadmap/)
- [backlog](backlog/)
- [releases](releases/)

## Out of Scope
- [Explanatory prose — that belongs in the handbook.](../handbook/)
- [Diagram sources — those live in architecture.](../architecture/)
- Application, API, frontend, or backend code.

## Relationships
- [Architecture](../architecture/) — expresses the structure that satisfies these specifications.
- [Templates](../templates/specification/) — the base template specifications are authored from.
- [ADRs](../adrs/) — record significant choices made within specifications.

## References
- [Master Plan](../bootstrap/MASTER_PLAN.md) — the constitution governing the framework
- [Architecture Decisions](../bootstrap/ARCHITECTURE_DECISIONS.md) — the ratified Foundation decision record

## Conventions
- Author specifications from the base specification template; back significant choices with an ADR.
