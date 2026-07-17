# C4 View Modeling

The methodology for modeling platform **structure** as a hierarchy of architectural views. It is the
entry document for [`c4/`](README.md) (the frozen README remains the contract).

## Overview
C4 view modeling describes the platform's structure at successive levels of abstraction — Context,
Container, Component, and Code — plus the Deployment and Dynamic view types that complete the picture.
It answers "what are the pieces, how do they fit, and how do they run and interact?" The structure it
depicts is owned by [06 — Reference Architecture](../../handbook/06-reference-architecture/CHAPTER.md);
this module owns only the modeling method.

## Purpose
To give the framework one canonical, layered view model so structure is described consistently and at
the right altitude — from a system-in-its-environment overview down to internal building blocks —
without mixing levels or drawing the same fact twice.

## Scope
**In scope:** the view-model methodology — the six view types, their abstraction levels, naming, and
review. **Out of scope:** the architectural concepts themselves (Handbook), and normative requirements
([`architecture-requirements`](../../specifications/architecture-requirements/)).

## Principles
Applications of the [shared modeling principles](../ARCHITECTURE_MODELING_FRAMEWORK.md#shared-modeling-principles):
one abstraction level per view; a consistent element vocabulary; every element and relationship
labeled with intent; and technology-neutral naming.

## Modeling Process
1. **Context** — model the platform as one system in its environment: its users, external systems,
   and the value exchanged. No internals.
2. **Container** — decompose the system into its deployable/executable units and their
   responsibilities and interactions (still no internals of each).
3. **Component** — decompose a container into its major components and their responsibilities.
4. **Code** — only where it adds durable value, model the internal structure of a component
   (produced sparingly and kept close to the design it documents).
5. **Choose additional views as needed** — a Deployment view for runtime placement, and Dynamic
   views for behavior (see *Views & Artifacts*).

## Guidelines & Notation
- Start at Context and descend only as far as decisions require; not every element needs a Code view.
- Keep one level per diagram; if a diagram needs two levels to be understood, split it.
- Label every relationship with the nature and direction of the interaction.
- Author in a C4-capable diagram-as-code notation (for example Structurizr DSL or a C4-style Mermaid
  diagram). Naming is generic and role-based, never product-based.

## Views & Artifacts
The canonical view model defines six view types. Per **AD-0010**, the `c4/` directory holds the four
core structural views; the Deployment and Dynamic views are **modeled in their dedicated modules**,
which this view model references so the picture is complete:

| View type | Abstraction | Home |
|-----------|-------------|------|
| Context | System in its environment | `c4/` |
| Container | Deployable/executable units | `c4/` |
| Component | Components within a container | `c4/` |
| Code | Internal structure of a component | `c4/` (sparingly) |
| Deployment | Placement onto infrastructure | [`deployment/`](../deployment/MODELING.md) (AD-0010) |
| Dynamic | Behavior over time (interactions, lifecycles) | [`sequences/`](../sequences/MODELING.md) and [`state-machines/`](../state-machines/MODELING.md) (AD-0010) |

## Patterns & Anti-patterns
**Patterns:** descend level-by-level; one system per Context view; stable container names reused
across views. **Anti-patterns:** mixing abstraction levels in one diagram; modeling Code for
everything; embedding deployment or interaction detail into structural views (they belong to the
dedicated modules); naming products instead of roles.

## Review Checklist & Quality Criteria
- [ ] Each view holds exactly one abstraction level.
- [ ] Context has no internals; Code views exist only where they earn their keep.
- [ ] Element and relationship labels state intent and direction.
- [ ] Deployment/Dynamic detail is referenced to its module, not duplicated here (AD-0010).
- [ ] Naming is technology-neutral and consistent across views.
- [ ] Each view traces to a requirement or decision.

## Cross-Module Integration
- **Upstream:** [Reference Architecture (Ch 06)](../../handbook/06-reference-architecture/CHAPTER.md) —
  the structure depicted; [`architecture-requirements`](../../specifications/architecture-requirements/) —
  what the structure must satisfy.
- **Downstream:** [`deployment/`](../deployment/MODELING.md) (Deployment view),
  [`sequences/`](../sequences/MODELING.md) and [`state-machines/`](../state-machines/MODELING.md)
  (Dynamic views), [`integrations/`](../integrations/MODELING.md) (container-to-container integration).
- **Related:** all structural disciplines.
- **Shared concepts (owned elsewhere):** platform planes and structure (Ch 06). This module defines
  none of them.

## Traceability & References
- **Handbook:** [06 — Reference Architecture](../../handbook/06-reference-architecture/CHAPTER.md).
- **Specifications:** [`architecture-requirements`](../../specifications/architecture-requirements/).
- **ADRs:** [AD-0010](../../bootstrap/ARCHITECTURE_DECISIONS.md) (C4 directory scope),
  [AD-0008](../../bootstrap/ARCHITECTURE_DECISIONS.md) (no catch-all).
- **Worked Examples:** platform structure appears across the [examples](../../examples/EXAMPLES_INDEX.md);
  C4 view instances are ready-structure for Phase 5.
