# Chapter 08 — Builder Platform

## Introduction

This chapter defines the builder plane of an AI Agent Platform: the capability through
which solutions are *created*. Its prerequisites are
[Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md), which placed
the builder as one plane, and
[Chapter 07 — Runtime Platform](../07-runtime-platform/CHAPTER.md), whose execution the
builder targets. The builder plane is where intent becomes a defined solution, before that
solution ever runs.

This chapter describes an architectural capability — its responsibilities, boundaries, and
relationships — not any tool, editor, framework, or technology. It maintains a strict
separation of concerns: the **builder creates**; the **runtime executes**. Nothing here
describes how a solution runs, integrates providers, is extended, governed, or persisted;
those concerns belong to their own planes. No product is named and no implementation is
prescribed.

## Objectives

After reading this chapter, a reader will be able to:

- Explain what the builder plane is responsible for and where its boundary with the runtime
  lies.
- Distinguish the design-time experience and its creator-facing modes of composition.
- Reason about the reusable design-time assets a builder plane provides.
- Keep creation concerns separate from execution, provision, extension, governance, and
  persistence.

## Concepts

This chapter **owns** the concepts below; other chapters reference them without redefining
them.

**Builder Experience.** The overall capability the platform offers for creating solutions:
everything a creator uses at design time to assemble agents and workflows. The builder
experience is judged by how well it lets creators express intent, not by any particular
interface.

**Design-Time Experience.** The set of concerns that apply while a solution is being
created, as opposed to while it runs. Design time is the builder plane's domain; run time
is the runtime plane's. The distinction is the plane's defining boundary.

**Creator Experience.** The builder experience seen from the perspective of the people who
create solutions — their ability to compose, understand, and refine what they are building.
It is the builder plane's counterpart to the product personas owned by
[Chapter 02](../02-product-thinking/CHAPTER.md).

**Visual Composition.** The capability to assemble a solution by arranging and connecting
its parts as a visible structure rather than solely in text. Visual composition is an
architectural affordance of the builder plane, independent of any specific canvas or
editor.

**No-Code Development.** Creation that requires no programming, expressing a solution
entirely through composition and configuration. It broadens who can create on the platform.

**Low-Code Development.** Creation that is primarily compositional but admits limited,
bounded authored logic where composition alone is insufficient. No-code and low-code are
points on one continuum of creator control, both owned here.

**Agent Assembly.** The composition of an individual agent from its constituent parts at
design time — defining what the agent is meant to do and from what it is built, without
specifying how it will run. Assembly produces a definition; execution of that definition is
owned by [Chapter 07](../07-runtime-platform/CHAPTER.md).

**Workflow Composition.** The design-time arrangement of agents, steps, and their relations
into a workflow. Workflow composition defines the intended structure of coordinated work;
carrying that structure out is the runtime's responsibility, not the builder's.

**Prompt Assets.** The reusable, versioned units of instruction authored at design time and
managed as first-class assets of a solution. Prompt assets are design-time artifacts owned
here; their durable persistence is a concern of the
[data plane](../12-data-platform/CHAPTER.md).

**Templates.** Predefined, parameterized starting points for common solutions, from which a
creator begins rather than starting empty. Builder templates accelerate correct, consistent
creation.

**Blueprints.** Complete, opinionated compositions that express a proven way to solve a
class of problem, ready to be adopted and adapted. A blueprint is a larger, more prescriptive
starting point than a template.

**Reusable Components.** The named, self-contained building units a creator composes with
across solutions — the shared vocabulary of the builder plane. Reusable components let
solutions be assembled from trusted parts rather than rebuilt each time.

## Principles

- **Separate creation from execution.** The builder defines solutions; it never runs them.
  Every builder concern ends at a solution definition handed to the runtime.
- **Compose over construct.** Prefer assembling solutions from reusable parts to authoring
  them from nothing.
- **Meet creators where they are.** Support a continuum from no-code to low-code so control
  matches the creator's need.
- **Treat design-time assets as first-class.** Manage prompt assets, templates, blueprints,
  and components as durable, versioned artifacts.
- **Uphold the platform's architectural principles.** Like every core-platform plane, the
  builder is provider-, framework-, cloud-, and runtime-agnostic; vendor-neutral;
  protocol-oriented; and extensible, composable, observable, and governable by design —
  instantiating the architectural principles owned by
  [Chapter 03](../03-engineering-principles/CHAPTER.md).

## Architecture

This section describes the structure of the *builder plane*, within the reference
architecture owned by [Chapter 06](../06-reference-architecture/CHAPTER.md).

The builder plane is organized around the act of creation:

1. A **creator**, through the **builder experience**, works at **design time**.
2. They perform **agent assembly** and **workflow composition**, often through **visual
   composition**, across a **no-code to low-code** continuum.
3. They draw on reusable **templates**, **blueprints**, **reusable components**, and
   **prompt assets**.
4. The output is a solution *definition*, which crosses the plane boundary to the
   [runtime plane](../07-runtime-platform/CHAPTER.md) for execution.

The builder relies on other planes without absorbing them: providers supply intelligence
([Chapter 09](../09-provider-platform/CHAPTER.md)), plugins supply extensions
([Chapter 10](../10-plugin-platform/CHAPTER.md)), the control plane governs what may be
built ([Chapter 11](../11-control-plane/CHAPTER.md)), and the data plane persists design-time
assets ([Chapter 12](../12-data-platform/CHAPTER.md)).

## Patterns

- **Definition, then execution.** *Context:* creating any solution. Produce a complete
  solution definition at design time and hand it to the runtime, keeping the boundary clean.
- **Start from a blueprint.** *Context:* a familiar class of problem. Begin from a blueprint
  or template and adapt, rather than composing from empty.
- **Assets as shared vocabulary.** *Context:* many solutions. Curate reusable components and
  prompt assets so solutions are built from trusted, versioned parts.

## Anti-patterns

- **Execution in the builder.** *Why it fails:* running or simulating real workloads inside
  the builder collapses the design-time/run-time boundary and duplicates the runtime.
  *Instead:* separate creation from execution.
- **Bespoke everything.** *Why it fails:* composing every solution from nothing forfeits
  consistency and reuse. *Instead:* compose over construct.
- **Code smuggled into no-code.** *Why it fails:* unbounded authored logic in a no-code
  surface erodes its guarantees and its audience. *Instead:* keep the no-code/low-code
  continuum explicit and bounded.
- **Orphan assets.** *Why it fails:* prompt assets and components managed ad hoc drift and
  cannot be trusted. *Instead:* treat design-time assets as first-class and delegate their
  persistence to the data plane.

## Best Practices

- End every builder concern at a solution definition; delegate execution to the
  [runtime plane](../07-runtime-platform/CHAPTER.md).
- Offer a clear no-code to low-code continuum and keep authored logic bounded.
- Curate templates, blueprints, and reusable components so creation is consistent.
- Manage prompt assets as versioned artifacts, delegating their storage to the
  [data plane](../12-data-platform/CHAPTER.md).
- Draw provider intelligence and plugin extensions from their planes rather than embedding
  them in the builder.

## Examples

The following are illustrative, non-executable aids.

**Creation continuum (illustrative):**

| Mode | Creator control | Typical use |
|------|-----------------|-------------|
| No-code | Composition and configuration only | Broad creation without programming |
| Low-code | Composition plus bounded authored logic | Where composition alone is insufficient |

**Design-time reusable assets and what they start from:**

| Asset | What it provides |
|-------|------------------|
| Template | A parameterized starting point for a common solution |
| Blueprint | A complete, opinionated composition for a class of problem |
| Reusable component | A self-contained unit composed across solutions |
| Prompt asset | A reusable, versioned unit of instruction |

## Checklist

A reader is ready to proceed to
[Chapter 09 — Provider Platform](../09-provider-platform/CHAPTER.md) when they can confirm:

- [ ] I can state what the builder plane creates and where it hands off to the runtime.
- [ ] I can distinguish design-time from run-time concerns.
- [ ] I can describe the no-code to low-code continuum and the design-time assets.
- [ ] I can keep creation separate from execution, provision, extension, governance, and
  persistence.

## References

- [Chapter 02 — Product Thinking](../02-product-thinking/CHAPTER.md) — owns the personas the
  creator experience serves.
- [Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md) — the frame
  that places the builder plane.
- [Chapter 07 — Runtime Platform](../07-runtime-platform/CHAPTER.md) — executes the solution
  definitions the builder produces.
- [Chapter 09 — Provider Platform](../09-provider-platform/CHAPTER.md),
  [Chapter 10 — Plugin Platform](../10-plugin-platform/CHAPTER.md),
  [Chapter 11 — Control Plane](../11-control-plane/CHAPTER.md), and
  [Chapter 12 — Data Platform](../12-data-platform/CHAPTER.md) — the planes the builder draws
  on without absorbing.
- [Glossary](../21-glossary/) — canonical terms used in this chapter.

## Summary

The builder plane is the capability through which solutions are created. It provides a
design-time, creator-facing experience — spanning no-code to low-code, often through visual
composition — for agent assembly and workflow composition, drawing on reusable templates,
blueprints, components, and prompt assets. Its defining boundary is that it produces
solution *definitions* and never executes them: the builder creates, and the runtime
executes. The next chapter,
[Chapter 09 — Provider Platform](../09-provider-platform/CHAPTER.md), defines the plane that
supplies the intelligence those solutions draw on.
