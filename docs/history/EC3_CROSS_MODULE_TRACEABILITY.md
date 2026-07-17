# EC-3 — Cross-Module Traceability Matrix

Maps each architecture-modeling discipline to its dependencies, its owning Handbook chapters, its
specification areas, its decisions, and the concepts it references (owned elsewhere). It demonstrates
that the Architecture Modeling Framework integrates with the rest of APEF and preserves concept
single-ownership — every depicted concept has exactly one owner, always in the Handbook.

## Module dependency map

| Module | Upstream | Downstream | Related |
|--------|----------|------------|---------|
| c4 | Ch 06; architecture-requirements | deployment, sequences, state-machines, integrations | all structural |
| deployment | c4, runtime; runtime + architecture-requirements specs | network | integrations |
| event-storming | discovery spec; product intent | domains spec; state-machines, sequences | runtime |
| integrations | c4; architecture-requirements | sequences, network | runtime, deployment |
| network | deployment; security spec | integrations | c4 |
| runtime | event-storming, runtime spec, c4 | state-machines, sequences, deployment | integrations; Execution Framework |
| sequences | runtime, integrations, event-storming | c4 (Dynamic views) | state-machines |
| state-machines | runtime, event-storming, runtime spec | c4 (Dynamic views) | sequences |

## Handbook, specification, and decision traceability

| Module | Owning Handbook chapter(s) | Specification area(s) | Decisions |
|--------|---------------------------|-----------------------|-----------|
| c4 | [06 Reference Architecture](../../handbook/06-reference-architecture/CHAPTER.md) | architecture-requirements | AD-0010, AD-0008 |
| deployment | [19 DevOps](../../handbook/19-devops/CHAPTER.md), [06](../../handbook/06-reference-architecture/CHAPTER.md) | runtime, architecture-requirements, releases | AD-0010 |
| event-storming | [05 Domain-Driven Design](../../handbook/05-domain-driven-design/CHAPTER.md) | discovery, domains | AD-0011 |
| integrations | [13 API Platform](../../handbook/13-api-platform/CHAPTER.md), [09 Provider](../../handbook/09-provider-platform/CHAPTER.md), [05](../../handbook/05-domain-driven-design/CHAPTER.md) | architecture-requirements | ADR framework |
| network | [15 Security](../../handbook/15-security/CHAPTER.md), [06](../../handbook/06-reference-architecture/CHAPTER.md) | security, architecture-requirements | ADR framework; security-review |
| runtime | [07 Runtime Platform](../../handbook/07-runtime-platform/CHAPTER.md), [11 Control Plane](../../handbook/11-control-plane/CHAPTER.md) | runtime | ADR framework |
| sequences | [06](../../handbook/06-reference-architecture/CHAPTER.md), [07](../../handbook/07-runtime-platform/CHAPTER.md) | architecture-requirements, runtime | AD-0010 |
| state-machines | [07](../../handbook/07-runtime-platform/CHAPTER.md), [05](../../handbook/05-domain-driven-design/CHAPTER.md) | runtime | AD-0010 |

## Shared concepts and their single owners

Every concept an architecture model depicts is owned by exactly one Handbook chapter; the architecture
module references it and defines none.

| Shared concept | Single owner | Referencing modules |
|----------------|--------------|---------------------|
| Platform structure & planes | Ch 06 | c4, deployment, sequences, network |
| Runtime execution, state, lifecycle | Ch 07 | runtime, state-machines, sequences |
| Orchestration, configuration, administration | Ch 11 | runtime |
| Bounded contexts, domain events, aggregates, ubiquitous language | Ch 05 | event-storming, state-machines, integrations |
| API contracts, versioning, API edge | Ch 13 | integrations |
| Provider integration contract | Ch 09 | integrations |
| Threat model, identity, isolation, trust boundaries | Ch 15 | network |
| Delivery, infrastructure, operational excellence | Ch 19 | deployment |
| Telemetry, tracing, SLOs | Ch 14 | (referenced where models annotate observability) |

## Worked-examples linkage

| Module | Related worked examples | Model instances |
|--------|-------------------------|-----------------|
| event-storming, state-machines | [agents](../../examples/agents) | Ready-structure (Phase 5) |
| runtime, sequences | [workflows](../../examples/workflows), [supervisors](../../examples/supervisors) | Ready-structure (Phase 5) |
| integrations | [providers](../../examples/providers) | Ready-structure (Phase 5) |

## Completeness statement

All eight modules are mapped to their upstream/downstream/related modules, owning Handbook chapters,
specification areas, and decisions. Every shared concept resolves to exactly one Handbook owner.
**Concept single-ownership is preserved; no architecture module owns a concept.**
