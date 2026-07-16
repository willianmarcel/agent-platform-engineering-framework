# Architecture — C4 Models

## Overview
Holds the C4 model views that describe the platform's structure at increasing levels of detail.

## Purpose
To provide a shared structural model from system context down to code.

## Responsibilities
- Hold the c4 models for the reference platform as diffable diagram-as-code.
- Stay consistent with the architecture requirements.

## Contents
- C4 diagrams for the Context, Container, Component, and Code views only, as diffable diagram-as-code, plus supporting notes.

## Out of Scope
- [Rendered image exports.](../../assets/)
- Deployment, network, sequence, or state diagrams — those have dedicated directories.
- [Normative requirements.](../../specifications/architecture-requirements/)

## Relationships
- [Deployment](../deployment/)
- [Sequences](../sequences/)
- [State machines](../state-machines/)

## References
- [Master Plan](../../bootstrap/MASTER_PLAN.md) — the constitution governing the framework
- [Architecture Decisions](../../bootstrap/ARCHITECTURE_DECISIONS.md) — the ratified Foundation decision record

## Conventions
- Prefer text-based, diffable diagram formats so reviews happen in pull requests.
