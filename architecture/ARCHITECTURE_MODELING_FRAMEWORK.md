# Architecture Modeling Framework

This document establishes the **Architecture Modeling Framework** of APEF: the canonical guidance for
how architecture is **modeled, represented, reviewed, and communicated** across the framework. It is
the authoritative entry document for the [`architecture/`](README.md) module; the frozen `README.md`
remains the directory contract, and this document with its per-discipline siblings carries the
substance (Module Entry Pattern, [ADR-0004](../adrs/decisions/0004-adopt-module-entry-pattern.md)).

The `architecture/` module is **not** a collection of diagrams. It is the methodology layer for
architectural modeling. It complements — and never duplicates — the Handbook, the Specification
Framework, the Execution Framework, the ADR Library, the Reference Studies, and the Worked Examples.

## Purpose

Architecture modeling turns the platform's architecture into explicit, reviewable, communicable
models. This framework exists to make that practice **consistent, disciplined, and traceable**: one
way to decide which model to build, how to build it, how to review it, and how it connects to the
rest of APEF — independent of any drawing tool or technology.

## The ownership boundary (what this module owns, and what it does not)

The Architecture Modeling Framework **owns modeling methodology** — the disciplines of C4 view
modeling, deployment modeling, event storming, integration modeling, network modeling, runtime
modeling, interaction (sequence) modeling, and lifecycle (state-machine) modeling: *how* each is
performed, reviewed, and communicated.

It **does not own, define, or redefine** the architectural, domain, or platform **concepts** those
models depict. Those concepts are owned by the Handbook and are referenced here, never restated:

| The model depicts… | Owned by (Handbook) |
|--------------------|---------------------|
| Platform structure and planes | [06 — Reference Architecture](../handbook/06-reference-architecture/CHAPTER.md) |
| Runtime execution, state, lifecycle | [07 — Runtime Platform](../handbook/07-runtime-platform/CHAPTER.md) |
| Domain model (bounded contexts, events) | [05 — Domain-Driven Design](../handbook/05-domain-driven-design/CHAPTER.md) |
| Orchestration, configuration, administration | [11 — Control Plane](../handbook/11-control-plane/CHAPTER.md) |
| API contracts, versioning, the API edge | [13 — API Platform](../handbook/13-api-platform/CHAPTER.md) |
| Threat model, identity, isolation, trust boundaries | [15 — Security](../handbook/15-security/CHAPTER.md) |
| Delivery, infrastructure, operational excellence | [19 — DevOps](../handbook/19-devops/CHAPTER.md) |
| Telemetry, tracing, SLOs | [14 — Observability](../handbook/14-observability/CHAPTER.md) |

This is the same separation the Specification Framework observes (it owns the specification method,
not the concepts specified). Concept single-ownership is thereby preserved: no modeling document
defines a concept the Handbook owns.

## Relationship to the rest of APEF

- **Handbook** — the normative source of the concepts models depict. Modeling references it.
- **Specifications** — models satisfy and visualize normative requirements, especially
  [`architecture-requirements`](../specifications/architecture-requirements/); event storming feeds
  [`domains`](../specifications/domains/).
- **Execution Framework** — architectural models are produced and reviewed within
  [commands, skills, and reviews](../execution/EXECUTION_FRAMEWORK.md); runtime modeling relates
  directly to it.
- **ADR Library** — significant modeling decisions are recorded as [ADRs](../adrs/ADR_FRAMEWORK.md);
  models make ADR context visible.
- **Reference Studies** — the [studies](../reference/REFERENCE_INDEX.md) illustrate real
  architectural approaches analytically; modeling abstracts, never copies, them.
- **Worked Examples** — the [examples](../examples/EXAMPLES_INDEX.md) demonstrate concepts; model
  instances of them are ready-structure for Phase 5.

## The modeling disciplines

Each discipline is defined in its module's `MODELING.md` entry document, using one consistent
structure (see below).

| Discipline | Models | Module |
|-----------|--------|--------|
| C4 view model | Structure at four abstraction levels + the deployment and dynamic view types | [`c4/`](c4/MODELING.md) |
| Deployment | Environments, topology, infrastructure boundaries, resiliency | [`deployment/`](deployment/MODELING.md) |
| Event storming | Domain exploration — events, commands, policies, aggregates | [`event-storming/`](event-storming/MODELING.md) |
| Integrations | Synchronous/asynchronous integration, contracts, reliability | [`integrations/`](integrations/MODELING.md) |
| Network | Trust boundaries, segmentation, connectivity, ingress/egress | [`network/`](network/MODELING.md) |
| Runtime | Execution model, lifecycle, orchestration, failure handling | [`runtime/`](runtime/MODELING.md) |
| Sequences | Interaction flows — synchronous, asynchronous, event | [`sequences/`](sequences/MODELING.md) |
| State machines | Lifecycle — states, transitions, guards, terminal states | [`state-machines/`](state-machines/MODELING.md) |

## Shared modeling principles

These are applications of the existing [Engineering Principles](../handbook/03-engineering-principles/CHAPTER.md)
to modeling; they introduce no new architectural principle.

1. **Model with intent.** Build a model to answer a question or support a decision — never for its
   own sake. If a model informs no decision and clarifies nothing, do not build it.
2. **Right abstraction.** Each model sits at one abstraction level; do not mix levels within a view.
3. **Single source of truth.** A fact appears in one model that owns it; other models reference it.
   No fact is drawn twice.
4. **Technology-neutral.** Models express structure and behavior, not products; naming stays generic
   (see Notation).
5. **Diffable and reviewable.** Models are authored as diagram-as-code so they are versioned,
   reviewed in pull requests, and traceable.
6. **Traceable.** Every model traces to the requirement, decision, or concept it serves.

## Notation policy

Models are authored as **diagram-as-code** in text-based, diffable notations — Mermaid, PlantUML, or
Structurizr DSL — consistent with the frozen [`architecture/README.md`](README.md) convention. The
notation is an authoring format, not a technology prescription for the platform. Choose the notation
that fits the view (for example, C4-friendly notations for structural views, sequence notation for
interactions, state notation for lifecycles). Rendered exports, when needed, go to
[`assets/`](../assets/).

## The common modeling process

Every discipline specializes this generic process:

1. **Frame** — state the question the model answers and its audience.
2. **Bound** — fix the scope and the abstraction level; identify the concepts (by their Handbook
   owners) the model will depict.
3. **Model** — build the model in the appropriate notation, at one abstraction level.
4. **Relate** — link the model to its requirements, decisions (ADRs), and neighboring models.
5. **Review** — apply the discipline's review checklist and quality criteria.
6. **Communicate** — publish the model where its audience will find it; export a rendering if needed.

## Model quality gates

A model is accepted only when it satisfies the framework-authoring
[Quality Gates](../bootstrap/QUALITY_GATES.md) as they apply to models:

- **Consistency** — agrees with the Handbook, Specifications, Execution Framework, ADRs, Reference
  Studies, and Worked Examples; no contradiction.
- **Traceability** — links to the requirement/decision/concept it serves.
- **Ownership** — depicts concepts owned elsewhere by reference; defines none.
- **Neutrality** — names no vendor, product, or technology.
- **No duplication** — repeats no fact or content owned by another model or module.

## Module structure and consistency

Each module's `MODELING.md` follows one consistent structure, merging the Board's required elements
where sensible: **Overview · Purpose · Scope · Principles · Modeling Process · Guidelines & Notation ·
Views & Artifacts · Patterns & Anti-patterns · Review Checklist & Quality Criteria · Cross-Module
Integration · Traceability & References**. Documents are not created merely to satisfy the structure;
sections are merged to keep each module readable and non-repetitive.

## Relationships

- Governed by the [Architecture Charter](../governance/ARCHITECTURE_CHARTER.md); models reviewed via
  the [architecture-review playbook](../playbooks/architecture-review/PROCEDURE.md).
- Complements the [Handbook](../handbook/HANDBOOK_SUMMARY.md),
  [Specification Framework](../specifications/SPECIFICATION_FRAMEWORK.md),
  [Execution Framework](../execution/EXECUTION_FRAMEWORK.md), and [ADR Framework](../adrs/ADR_FRAMEWORK.md).
- Consistent with the Foundation decisions on architecture: AD-0008 (no catch-all; every artifact
  categorized), AD-0010 (C4 directory scope), AD-0011 (event storming placement).
