# Deployment Modeling

The methodology for modeling how the platform is **placed onto infrastructure and operated**. Entry
document for [`deployment/`](README.md) (frozen README remains the contract). It provides the
Deployment view of the [C4 view model](../c4/MODELING.md) (AD-0010).

## Overview
Deployment modeling describes where the platform's units run, the environments they run in, the
boundaries between infrastructure, and the arrangements that keep the platform available under
failure and load. The delivery, infrastructure, and operational concepts it depicts are owned by
[19 — DevOps](../../handbook/19-devops/CHAPTER.md) and [06 — Reference Architecture](../../handbook/06-reference-architecture/CHAPTER.md);
this module owns the modeling method.

## Purpose
To make runtime placement and operational resilience explicit and reviewable before delivery, so
topology, boundaries, and availability arrangements are deliberate rather than incidental.

## Scope
**In scope:** modeling environments, topology, infrastructure boundaries, resiliency, scalability,
high availability, and disaster recovery. **Out of scope:** the operational practices themselves
(Ch 19), and the network internals ([`network/`](../network/MODELING.md)).

## Principles
One environment model per environment class; boundaries drawn explicitly; availability and recovery
expressed as arrangements, not products; technology-neutral (capacities and zones, not vendors).

## Modeling Process
1. **Environments** — model the environment classes (for example development, staging, production)
   and what differs between them.
2. **Topology** — place the platform's units (from the [Container view](../c4/MODELING.md)) onto
   infrastructure nodes and zones.
3. **Boundaries** — draw the infrastructure boundaries (isolation, tenancy, availability zones,
   regions) the topology crosses.
4. **Resilience** — model redundancy, failover, and degradation behavior against defined failure
   modes.
5. **Recovery** — model the disaster-recovery arrangement (recovery objectives, replication,
   fallback) at the level of strategy, not product configuration.

## Guidelines & Notation
- Model capacity and placement in generic terms (nodes, zones, regions, replicas) — never named
  products or providers.
- Separate the *deployment* boundary (this module) from the *network* boundary
  ([`network/`](../network/MODELING.md)); reference, do not redraw.
- Author as diagram-as-code (a C4 Deployment diagram or equivalent). Express availability and DR as
  annotated topology, with recovery objectives stated as targets.

## Views & Artifacts
- **Environment model** — the environment classes and their differences.
- **Deployment topology** — units placed on nodes/zones/regions.
- **Resiliency & availability annotations** — redundancy, failover, degradation.
- **Disaster-recovery arrangement** — objectives and strategy.

## Patterns & Anti-patterns
**Patterns:** redundancy across independent zones; stateless units scaled horizontally; explicit
recovery objectives; graceful degradation. **Anti-patterns:** a single point of failure left
implicit; conflating deployment topology with network segmentation; naming a specific cloud/product;
modeling capacity without a stated load assumption.

## Review Checklist & Quality Criteria
- [ ] Every platform unit has a placement; no unit is unplaced.
- [ ] Failure modes are named and each has a resilience response.
- [ ] High-availability and DR arrangements state their objectives (targets, not products).
- [ ] Deployment boundaries reference the network model rather than redrawing it.
- [ ] Naming is technology-neutral.
- [ ] The topology traces to runtime and requirement sources.

## Cross-Module Integration
- **Upstream:** [`c4/`](../c4/MODELING.md) (Container view — the units placed),
  [`runtime/`](../runtime/MODELING.md) (what runs), and
  [`architecture-requirements`](../../specifications/architecture-requirements/) and
  [`runtime` specifications](../../specifications/runtime/) (availability/scalability requirements).
- **Downstream:** [`network/`](../network/MODELING.md) (connectivity across the topology).
- **Related:** [`integrations/`](../integrations/MODELING.md) (cross-boundary communication).
- **Shared concepts (owned elsewhere):** delivery/operations (Ch 19), platform structure (Ch 06).

## Traceability & References
- **Handbook:** [19 — DevOps](../../handbook/19-devops/CHAPTER.md),
  [06 — Reference Architecture](../../handbook/06-reference-architecture/CHAPTER.md).
- **Specifications:** [`runtime`](../../specifications/runtime/),
  [`architecture-requirements`](../../specifications/architecture-requirements/),
  [`releases`](../../specifications/releases/).
- **ADRs:** [AD-0010](../../bootstrap/ARCHITECTURE_DECISIONS.md) (Deployment view is modeled here).
- **Worked Examples:** deployment instances are ready-structure for Phase 5;
  [examples](../../examples/EXAMPLES_INDEX.md) illustrate the units deployed.
