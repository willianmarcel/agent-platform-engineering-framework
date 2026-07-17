# Runtime Modeling

The methodology for modeling the platform's **runtime architecture** — how work executes, progresses,
and recovers. Entry document for [`runtime/`](README.md) (frozen README remains the contract).

## Overview
Runtime modeling describes the execution model: how workflows and agents run, how they are
orchestrated, how concurrency is handled, and how the system behaves under retry, recovery, and
failure. The runtime concepts it depicts — execution, state, lifecycle — are owned by
[07 — Runtime Platform](../../handbook/07-runtime-platform/CHAPTER.md), and orchestration/administration
by [11 — Control Plane](../../handbook/11-control-plane/CHAPTER.md). This module owns the modeling
method.

## Purpose
To make execution and failure behavior explicit and reviewable, so orchestration, concurrency, and
recovery are designed deliberately rather than discovered in production.

## Scope
**In scope:** modeling the execution model, runtime lifecycle, workflows, agents, orchestration,
concurrency, retries, recovery, and failure handling. **Out of scope:** defining runtime/control-plane
concepts (Ch 07/11) and the deployment placement ([`deployment/`](../deployment/MODELING.md)).

## Relationship to the Execution Framework
Runtime modeling and the [Execution Framework](../../execution/EXECUTION_FRAMEWORK.md) are complementary
and distinct. The Execution Framework is *how APEF engineering work is executed* — the commands,
skills, and workflows that produce the framework's artifacts. Runtime modeling is *how the modeled
platform executes at run time* — the execution architecture of the platform being built. This module
models the latter and references the former only where an engineering workflow produces or reviews a
runtime model; it never redefines the Execution Framework's commands or workflows.

## Principles
Model the execution model explicitly; make failure a first-class design input; prefer idempotent,
recoverable steps; bound concurrency deliberately; separate orchestration from the work orchestrated.

## Modeling Process
1. **Execution model** — model how a unit of work runs (its steps, inputs, outputs).
2. **Lifecycle** — model the runtime lifecycle of workflows and agents (created → running →
   completed/failed), referencing [`state-machines/`](../state-machines/MODELING.md) for detailed
   lifecycles.
3. **Orchestration** — model how work is coordinated (sequencing, branching, supervision).
4. **Concurrency** — model parallelism, ordering constraints, and shared-state access.
5. **Failure handling** — model retries (with idempotency), recovery, compensation, and terminal
   failure.

## Guidelines & Notation
- Model orchestration separately from the orchestrated work; reference, don't merge.
- Every step that can fail has a defined behavior (retry, compensate, fail, escalate).
- Author as diagram-as-code: workflow/orchestration diagrams for structure, and reference
  [`sequences/`](../sequences/MODELING.md) for ordered interactions and
  [`state-machines/`](../state-machines/MODELING.md) for lifecycles. Name no technology.

## Views & Artifacts
- **Execution model** — the shape of a unit of work.
- **Orchestration model** — coordination of workflows and agents.
- **Concurrency model** — parallelism and ordering constraints.
- **Failure-handling model** — retry/recovery/compensation/terminal behavior.

## Patterns & Anti-patterns
**Patterns:** idempotent steps; bounded retries with backoff; compensation for partial progress;
supervision hierarchies; explicit terminal states. **Anti-patterns:** unbounded or non-idempotent
retries; hidden shared mutable state; orchestration entangled with work; failure paths left
unmodeled; naming a specific runtime or engine.

## Review Checklist & Quality Criteria
- [ ] The execution model states inputs, outputs, and steps.
- [ ] Every failure-prone step has defined recovery behavior.
- [ ] Retries are bounded and paired with idempotency.
- [ ] Concurrency constraints and shared state are explicit.
- [ ] Lifecycles/interactions are referenced to their modules, not duplicated.
- [ ] Naming is technology-neutral; Execution Framework workflows are referenced, not redefined.

## Cross-Module Integration
- **Upstream:** [`event-storming/`](../event-storming/MODELING.md) (domain behavior),
  [`runtime` specifications](../../specifications/runtime/) (runtime requirements),
  [`c4/`](../c4/MODELING.md) (containers that host execution).
- **Downstream:** [`state-machines/`](../state-machines/MODELING.md) (lifecycles),
  [`sequences/`](../sequences/MODELING.md) (interaction flows),
  [`deployment/`](../deployment/MODELING.md) (where it runs).
- **Related:** [`integrations/`](../integrations/MODELING.md) (external calls and their failure
  behavior); the [Execution Framework](../../execution/EXECUTION_FRAMEWORK.md) (engineering workflows).
- **Shared concepts (owned elsewhere):** execution, state, lifecycle (Ch 07); orchestration (Ch 11).
  This module defines none of them.

## Traceability & References
- **Handbook:** [07 — Runtime Platform](../../handbook/07-runtime-platform/CHAPTER.md),
  [11 — Control Plane](../../handbook/11-control-plane/CHAPTER.md).
- **Specifications:** [`runtime`](../../specifications/runtime/).
- **Execution Framework:** [EXECUTION_FRAMEWORK.md](../../execution/EXECUTION_FRAMEWORK.md) (complementary).
- **ADRs:** runtime decisions are recorded via the [ADR framework](../../adrs/ADR_FRAMEWORK.md).
- **Worked Examples:** [workflow](../../examples/workflows/) and [supervisor](../../examples/supervisors/)
  examples illustrate runtime behavior; model instances are ready-structure for Phase 5.
