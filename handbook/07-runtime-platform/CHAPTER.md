# Chapter 07 — Runtime Platform

## Introduction

This chapter defines the runtime plane of an AI Agent Platform: the part responsible for
executing agents and workflows. Its prerequisite is
[Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md), which placed
the runtime as one plane within the whole; this chapter details that plane's
responsibilities and the model by which it runs work.

This chapter describes the runtime at the level of responsibilities and execution model —
what the runtime must account for and why — not how any runtime is implemented. It contains
no code and recommends no technology. It stays within the runtime plane: authoring is owned
by the [builder plane](../08-builder-platform/), external integration by the
[provider plane](../09-provider-platform/), extension by the
[plugin plane](../10-plugin-platform/), governance by the
[control plane](../11-control-plane/), and durable storage by the
[data plane](../12-data-platform/).

## Objectives

After reading this chapter, a reader will be able to:

- Explain what the runtime plane is responsible for and what lies outside it.
- Describe the agent runtime and the agent lifecycle it manages.
- Reason about the execution model, including scheduling of work.
- Distinguish runtime state, session, and memory coordination, and their runtime
  boundaries.

## Concepts

This chapter **owns** the concepts below; other chapters reference them without redefining
them.

**Runtime Platform.** The plane that executes agents and workflows: it accepts work,
carries it through to a result, and maintains the conditions under which that work runs
reliably. The runtime platform is where the platform's intent becomes running behavior,
within the frame set by [Chapter 06](../06-reference-architecture/CHAPTER.md).

**Agent Runtime.** The environment the platform provides for an individual agent to run:
the context, resources, and guarantees an agent depends on while it operates. The agent
runtime is what an agent runs *within*; how an agent is authored is owned by the
[builder plane](../08-builder-platform/).

**Agent Lifecycle.** The stages an agent passes through while under the runtime's care —
from admission, through active operation, to completion or termination — and the transitions
between them. The lifecycle defines when an agent exists, when it is doing work, and when it
is finished, so its resources and state can be managed accordingly.

**Runtime Responsibilities.** The obligations the runtime plane accepts on behalf of the
work it runs: admitting and placing work, upholding its lifecycle, isolating concurrent
work, and maintaining reliability. Runtime responsibilities mark what the runtime is
accountable for, and by exclusion what it delegates to other planes.

**Execution Model.** The conceptual model of how work is carried out: how units of work are
represented, how they progress, how concurrency and isolation are handled, and how results
and failures are propagated. The execution model is technology-neutral; it describes the
semantics of running work, not a mechanism.

**Scheduling.** The runtime responsibility of deciding when and where units of work run,
given finite resources and competing demands. Scheduling governs order, concurrency, and
resource allocation among work, according to policy set through the
[control plane](../11-control-plane/).

**State.** The information the runtime maintains about work in progress so that execution
can proceed correctly across steps. Runtime state is execution-time information; its durable
persistence and storage are owned by the [data plane](../12-data-platform/), which the
runtime relies on rather than reimplements.

**Session.** The bounded context of continuity within which a related sequence of work
occurs, holding the state relevant to that interaction for its duration. A session groups
work that belongs together in time and scope, and defines when that grouping begins and
ends.

**Memory Coordination.** The runtime responsibility of making the right information
available to work as it runs — assembling, scoping, and bounding what each unit of work can
draw on — while delegating the durable storage and retrieval of that information to the
[data plane](../12-data-platform/). Memory coordination is a runtime concern (what is
available, now, to this work); persistence is a data concern.

**Runtime Boundaries.** The seams that separate the runtime plane from the others and that
isolate one unit of running work from another. Runtime boundaries determine what the
runtime is responsible for versus what it delegates, and they keep concurrent work from
interfering — realizing the architectural boundaries of
[Chapter 06](../06-reference-architecture/CHAPTER.md) within the runtime.

## Principles

- **Own execution, delegate the rest.** The runtime is accountable for running work
  reliably, and delegates authoring, integration, extension, governance, and storage to
  their planes.
- **Make the lifecycle explicit.** Define the stages an agent passes through so its
  resources and state are managed deliberately.
- **Isolate concurrent work.** Keep units of running work from interfering with one another
  through clear runtime boundaries.
- **Separate runtime state from durable storage.** Maintain what execution needs now, and
  rely on the data plane for what must persist.
- **Schedule by policy.** Let scheduling decisions follow policy defined through the control
  plane, not ad hoc preference.
- **Coordinate memory, do not store it.** Assemble and bound what work can draw on at
  runtime, leaving persistence to the data plane.

## Architecture

This section describes the structure of the *runtime plane*, within the reference
architecture owned by [Chapter 06](../06-reference-architecture/CHAPTER.md).

The runtime plane organizes its responsibilities around the flow of work:

1. Work is **admitted** and placed by **scheduling** according to policy.
2. Each agent runs within its **agent runtime**, progressing through its **agent
   lifecycle** under the **execution model**.
3. **State**, **session**, and **memory coordination** maintain what running work needs,
   drawing durable persistence from the [data plane](../12-data-platform/).
4. **Runtime boundaries** isolate units of work from each other and separate the runtime
   from the other planes.

The runtime observes and is governed through the cross-cutting concerns owned elsewhere:
observability by [Chapter 14](../14-observability/), security by
[Chapter 15](../15-security/), and evaluation of what it runs by
[Chapter 16](../16-evaluation/). This chapter defines the runtime's responsibilities; those
chapters define how it is seen, secured, and assessed.

## Patterns

- **Lifecycle-managed execution.** *Context:* running any agent. Manage the agent through
  explicit lifecycle stages, so resources and state are acquired and released
  deliberately.
- **Policy-driven scheduling.** *Context:* finite resources and competing work. Let
  scheduling follow policy defined through the control plane rather than fixed order.
- **Runtime–data separation.** *Context:* handling information. Keep execution-time state in
  the runtime and delegate durable persistence to the data plane.

## Anti-patterns

- **Runtime as storage.** *Why it fails:* persisting durable data inside the runtime blurs
  planes and undermines both reliability and the data plane's ownership. *Instead:* separate
  runtime state from durable storage.
- **Implicit lifecycle.** *Why it fails:* running work without explicit lifecycle stages
  leaks resources and obscures state. *Instead:* make the lifecycle explicit.
- **Shared mutable runtime.** *Why it fails:* letting concurrent work share state without
  boundaries causes interference and non-determinism. *Instead:* isolate concurrent work.
- **Plane overreach.** *Why it fails:* a runtime that authors, integrates, or governs
  duplicates other planes and breaks cohesion. *Instead:* own execution and delegate the
  rest.

## Best Practices

- Define the agent lifecycle explicitly and manage resources against it.
- Keep runtime state distinct from durable storage, relying on the
  [data plane](../12-data-platform/) for persistence.
- Coordinate memory as a runtime concern; delegate its storage and retrieval.
- Let scheduling follow policy set through the [control plane](../11-control-plane/).
- Enforce runtime boundaries so concurrent work stays isolated, and delegate observability,
  security, and evaluation to their owning chapters.

## Examples

The following are illustrative, non-executable aids.

**Runtime responsibility versus delegated concern:**

| The runtime owns… | It delegates… |
|-------------------|---------------|
| Executing work and upholding the agent lifecycle | Authoring of agents (builder plane) |
| Scheduling and isolating concurrent work | Governance and policy definition (control plane) |
| Runtime state, session, and memory coordination | Durable persistence and retrieval (data plane) |
| Runtime boundaries between units of work | External model and service integration (provider plane) |

**Agent lifecycle (illustrative stages):** an agent is *admitted*, becomes *active* while it
works, may be *suspended* and *resumed* within a session, and finally reaches *completion*
or *termination*, at which point its runtime state and resources are released.

## Checklist

A reader is ready to proceed to the next chapter when they can confirm:

- [ ] I can state what the runtime plane is responsible for and what it delegates.
- [ ] I can describe the agent runtime and the agent lifecycle.
- [ ] I can reason about the execution model and scheduling.
- [ ] I can distinguish runtime state, session, and memory coordination from durable
  storage.

## References

- [Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md) — the frame
  that places the runtime plane.
- [Chapter 08 — Builder Platform](../08-builder-platform/) — owns how agents are authored.
- [Chapter 11 — Control Plane](../11-control-plane/) — owns the policy that governs
  scheduling.
- [Chapter 12 — Data Platform](../12-data-platform/) — owns durable persistence and
  retrieval.
- [Chapter 14 — Observability](../14-observability/),
  [Chapter 15 — Security](../15-security/), and
  [Chapter 16 — Evaluation](../16-evaluation/) — own the cross-cutting concerns applied to
  the runtime.
- [Runtime specifications](../../specifications/runtime/) — the normative counterpart to
  this chapter.
- [Glossary](../21-glossary/) — canonical terms used in this chapter.

## Summary

The runtime platform is the plane that executes agents and workflows. It provides each
agent a runtime and manages its lifecycle, runs work under an explicit execution model,
schedules that work by policy, and maintains the runtime state, session, and memory
coordination that execution needs — while delegating authoring, integration, extension,
governance, and durable storage to their planes, and observability, security, and
evaluation to their cross-cutting owners. Runtime boundaries keep concurrent work isolated
and the plane cohesive. With the runtime established, the Handbook continues with the
remaining platform planes and cross-cutting concerns that build upon this foundation.
