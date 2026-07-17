# Chapter 12 — Data Platform

## Introduction

This chapter defines the data plane of an AI Agent Platform: the capability through which
the platform's information is *persisted*. Its prerequisite is
[Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md), which placed
the data plane as one plane within the whole.

The data plane **defines persistent information**; it **never defines runtime execution**.
That boundary is its defining principle and the reciprocal of the runtime plane's: the
[runtime plane](../07-runtime-platform/CHAPTER.md) maintains what execution needs *now* and
delegates durable persistence here; the data plane holds what must *endure*, and delegates
the running of work back to the runtime. This chapter describes an architectural capability —
responsibilities, boundaries, and relationships — not any database, store, or technology. No
product is named and no implementation is prescribed.

## Objectives

After reading this chapter, a reader will be able to:

- Explain what the data plane persists and why it never executes work.
- Distinguish the kinds of platform data the plane is responsible for.
- Reason about data ownership and the data lifecycle.
- Keep persistence separate from execution, governance, and provision.

## Concepts

This chapter **owns** the concepts below; other chapters reference them without redefining
them.

**Platform Data.** The whole of the information the platform must persist to operate and to
be trusted over time. Platform data is the data plane's subject; the plane is responsible
for its durable keeping, not for the work that produces or consumes it.

**State Persistence.** The durable keeping of state that must survive beyond the moment of
execution. State persistence is the reciprocal of the runtime's runtime state (owned by
[Chapter 07](../07-runtime-platform/CHAPTER.md)): the runtime holds execution-time state and
relies on this plane to persist what must endure.

**Memory Persistence.** The durable keeping of the information that constitutes an agent's or
solution's memory across time. Memory persistence is the reciprocal of the runtime's memory
coordination (owned by [Chapter 07](../07-runtime-platform/CHAPTER.md)): the runtime decides
what is available now; this plane keeps what persists.

**Conversation Persistence.** The durable keeping of conversations and the sessions they
belong to, so that interactions can be retained, resumed, and reviewed. It is the persisted
counterpart to the runtime's session concept.

**Knowledge Assets.** The curated bodies of information the platform retains to inform its
work — the durable knowledge a solution can draw upon. Knowledge assets are persisted
information owned here; how a solution uses them at design time or run time belongs to those
planes.

**Vector Data.** Information persisted in a form suited to similarity-based retrieval. Vector
data is one kind of platform data the plane keeps; this chapter defines it as a persistence
responsibility, not as any indexing technology.

**Structured Data.** Information persisted with an explicit, defined shape, so it can be
stored and retrieved by its structure. Structured data complements vector and other data as
part of the plane's responsibility.

**Metadata.** The data that describes other data — its meaning, origin, and relationships —
so that platform data can be understood, found, and governed. Metadata is what makes the
rest of the platform's data intelligible over time.

**Event Storage.** The durable keeping of events for retention, replay, and audit. Event
storage persists events; the *domain events* whose meaning it may carry are owned by
[Chapter 05 — Domain-Driven Design](../05-domain-driven-design/CHAPTER.md), which this plane
stores rather than redefines.

**Audit Data.** The durable, trustworthy record of what happened on the platform, kept so
that actions can be accounted for after the fact. Audit data is persisted here; the act of
observing the running platform is owned by
[Chapter 14 — Observability](../14-observability/).

**Data Ownership.** The principle and structure that establish, for every piece of platform
data, who owns it and under what authority — especially across tenants. Data ownership is how
the data plane upholds governance and trust, applying the multi-tenancy owned by
[Chapter 11 — Control Plane](../11-control-plane/CHAPTER.md).

**Data Lifecycle.** The stages platform data passes through — from creation, through
retention and use, to archival or deletion — governed so that data is kept exactly as long as
it should be. The data lifecycle is how the plane keeps persistence deliberate rather than
unbounded.

## Principles

- **Persist, do not execute.** The data plane keeps information durably; it never runs
  business work, which belongs to the runtime.
- **Own every datum.** Establish clear ownership for all platform data, enforced across
  tenants.
- **Govern the lifecycle.** Retain data deliberately, for exactly as long as it should be
  kept, and no longer.
- **Describe data with metadata.** Keep data intelligible, findable, and governable through
  metadata.
- **Uphold the platform's architectural principles.** Like every core-platform plane, the
  data plane is provider-, framework-, cloud-, and runtime-agnostic; vendor-neutral;
  protocol-oriented; and extensible, composable, observable, and governable by design —
  instantiating the architectural principles owned by
  [Chapter 03](../03-engineering-principles/CHAPTER.md).

## Architecture

This section describes the structure of the *data plane*, within the reference architecture
owned by [Chapter 06](../06-reference-architecture/CHAPTER.md).

The data plane is organized around durable, governed information:

1. **Platform data** spans **state persistence**, **memory persistence**, **conversation
   persistence**, **knowledge assets**, **vector data**, **structured data**, **event
   storage**, and **audit data**, each described by **metadata**.
2. **Data ownership** establishes authority over every datum, applying control-plane
   multi-tenancy.
3. The **data lifecycle** governs how long each is kept.

The data plane serves the other planes without doing their work: it persists what the
[runtime](../07-runtime-platform/CHAPTER.md) must keep beyond execution, the design-time
assets of the [builder](../08-builder-platform/CHAPTER.md), and the configuration, policy,
and audit data of the [control plane](../11-control-plane/CHAPTER.md) — while the meaning of
what it stores (for example, domain events) remains owned by its defining chapter.

## Patterns

- **Runtime–data handoff.** *Context:* information that must endure. Let the runtime maintain
  execution-time state and hand durable persistence to the data plane, keeping the boundary
  clean.
- **Ownership-first data.** *Context:* any persisted datum. Establish its owner and authority
  before it is kept, so governance is intrinsic.
- **Lifecycle-governed retention.** *Context:* all data. Attach a lifecycle to data so it is
  retained and removed deliberately.

## Anti-patterns

- **Execution in the data plane.** *Why it fails:* running business work where data lives
  collapses the boundary and duplicates the runtime. *Instead:* persist, do not execute.
- **Ownerless data.** *Why it fails:* data without clear ownership cannot be governed or
  trusted, especially across tenants. *Instead:* own every datum.
- **Unbounded retention.** *Why it fails:* keeping everything forever creates risk and cost
  and erodes trust. *Instead:* govern the lifecycle.
- **Redefining meaning.** *Why it fails:* restating what stored events or domain concepts
  mean duplicates their owners and will diverge. *Instead:* store meaning owned elsewhere
  without redefining it.

## Best Practices

- Keep the data plane strictly to persistence; delegate execution to the runtime.
- Persist runtime state, memory, and conversation as the durable counterpart to the
  runtime's execution-time concerns.
- Establish ownership and a lifecycle for every piece of platform data.
- Describe platform data with metadata so it stays intelligible and governable.
- Store events and other meaning-bearing data without redefining the concepts their owning
  chapters hold.

## Examples

The following are illustrative, non-executable aids.

**Kinds of platform data (persistence responsibilities):**

| Kind | What it keeps |
|------|---------------|
| State persistence | State that must survive beyond execution |
| Memory / conversation persistence | Durable memory and retained conversations |
| Knowledge assets / vector data | Curated knowledge, kept for retrieval |
| Structured data / metadata | Shaped data and the data that describes it |
| Event storage / audit data | Retained events and the trustworthy record of what happened |

**Runtime and data, reciprocally (illustrative):** the runtime maintains what a unit of work
needs while it runs and asks the data plane to persist what must endure; the data plane keeps
it, owns it, and governs its lifecycle, and returns it when the runtime needs it again —
neither plane performing the other's role.

## Checklist

A reader is ready to proceed to the next chapter when they can confirm:

- [ ] I can explain what the data plane persists and why it never executes work.
- [ ] I can distinguish the kinds of platform data the plane keeps.
- [ ] I can reason about data ownership and the data lifecycle.
- [ ] I can keep persistence separate from execution, governance, and provision.

## References

- [Chapter 05 — Domain-Driven Design](../05-domain-driven-design/CHAPTER.md) — owns the
  domain events that event storage persists.
- [Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md) — the frame
  that places the data plane.
- [Chapter 07 — Runtime Platform](../07-runtime-platform/CHAPTER.md) — maintains
  execution-time state and delegates persistence here.
- [Chapter 11 — Control Plane](../11-control-plane/CHAPTER.md) — owns the multi-tenancy that
  data ownership applies.
- [Chapter 14 — Observability](../14-observability/) — owns observing the running platform,
  distinct from audit data.
- [Glossary](../21-glossary/) — canonical terms used in this chapter.

## Summary

The data plane persists the platform's information: state, memory, conversation, knowledge
assets, vector and structured data, metadata, event storage, and audit data — each owned,
described by metadata, and governed through a data lifecycle. It is the durable, reciprocal
counterpart to the runtime plane: the runtime keeps what execution needs now, and the data
plane keeps what must endure, neither performing the other's role. With the core platform
planes established — builder, provider, plugin, control, and data, atop the runtime — the
Handbook continues with the cross-cutting concerns that apply across them all.
