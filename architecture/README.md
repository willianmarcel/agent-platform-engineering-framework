# Architecture — Models, Diagrams, and Structural Design

## Overview
This directory holds the architectural models and diagram sources for the framework's reference platform. Every architectural artifact belongs to a well-defined category; there is no general-purpose catch-all.

## Purpose
To design and make visible the platform's structure at multiple levels of abstraction.

## Responsibilities
- Express platform structure as diffable, reviewable diagram-as-code.
- Connect specifications to concrete structural decisions.

## Contents
- [c4](c4/) — Context, Container, Component, and Code views only.
- [event-storming](event-storming/)
- [deployment](deployment/)
- [runtime](runtime/)
- [network](network/)
- [integrations](integrations/)
- [state-machines](state-machines/)
- [sequences](sequences/)

## Out of Scope
- [Rendered binary images intended for reuse — export those to assets.](../assets/)
- [Normative requirements.](../specifications/architecture-requirements/)
- Application, API, frontend, or backend code.

## Relationships
- [Architecture requirements](../specifications/architecture-requirements/) — the normative constraints these models satisfy.
- [Assets](../assets/) — holds rendered exports of these diagrams.

## References
- [Master Plan](../bootstrap/MASTER_PLAN.md) — the constitution governing the framework
- [Architecture Decisions](../bootstrap/ARCHITECTURE_DECISIONS.md) — the ratified Foundation decision record

## Conventions
- Prefer text-based, diffable diagram formats (Mermaid, PlantUML, Structurizr DSL) so reviews happen in pull requests.
- There is no generic diagrams directory; every diagram belongs to one of the categories above.
