# APEF Construction Roadmap

## Overview
This is the single authoritative roadmap for building the Agent Platform Engineering
Framework. It defines the phases the framework moves through, their deliverables, and
their exit criteria. It is intentionally phase-based rather than date-based: each phase
completes only when its exit criteria are met.

## Purpose
To hold, in one place, the authoritative phase content that governs how the framework
is constructed, so that no roadmap content is duplicated elsewhere.

## Phases

### Phase 1 — Foundation (current)
Establish the repository: the complete directory structure, a README following the
ratified contract in every directory, root governance files, and purpose-defined
bootstrap documents. No application, API, frontend, or backend code.

**Exit criteria:** repository structure exists, every directory has a clear
responsibility, and the repository is ready for the Engineering phase.

### Phase 2 — Engineering
Author the handbook chapters, fill in the bootstrap governance documents, and produce
the core specifications and architecture that define the reference platform.

### Phase 3 — Specification
Expand Specification-Driven Development artifacts: domains, capabilities, runtime,
security, observability, and release specifications, backed by ADRs.

### Phase 4 — Reference & Examples
Complete the reference studies of external frameworks and provide worked,
non-executable examples of agents, workflows, providers, plugins, supervisors, and
evaluations.

### Phase 5 — Evolution
Maintain, version, and evolve the framework through the defined release process.

## Relationships
- [Master Plan](MASTER_PLAN.md) — the constitution this roadmap serves.
- [Architecture Decisions](ARCHITECTURE_DECISIONS.md) — the ratified decisions that shape the phases.
- [Release Process](RELEASE_PROCESS.md) — how each phase's output is released.
- [Root roadmap](../ROADMAP.md) — the navigation document that points here.

## References
- [Roadmap chapter](../handbook/20-roadmap/) — how platform roadmaps are shaped.
- [Roadmap specifications](../specifications/roadmap/) — the platform roadmap artifacts.

## Conventions
- This document owns all phase content; other roadmap documents navigate to it and never duplicate it.
- Detailed per-phase milestones are authored in the Engineering phase.
