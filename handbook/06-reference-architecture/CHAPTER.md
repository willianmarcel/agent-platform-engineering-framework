# Chapter 06 — Reference Architecture

## Introduction

This chapter defines the canonical reference architecture of an AI Agent Platform: the
structure that ties its parts into a coherent whole. Its prerequisites are
[Chapter 01 — Platform Vision](../01-platform-vision/CHAPTER.md),
[Chapter 03 — Engineering Principles](../03-engineering-principles/CHAPTER.md), and
[Chapter 05 — Domain-Driven Design](../05-domain-driven-design/CHAPTER.md): the architecture
serves the vision, applies the engineering and architectural principles, and is built on
the domain model's boundaries.

This chapter is the hub of the Handbook. It establishes the shared mental model that every
platform-plane and cross-cutting chapter depends on and must not contradict. It describes
structure at the level of layers, views, building blocks, planes, and boundaries — not
implementation, not runtime behavior, and not the internals of any single plane, each of
which is owned by its own chapter. It recommends no technology and contains no code.

## Objectives

After reading this chapter, a reader will be able to:

- Explain what a reference architecture is and why the platform needs one.
- Distinguish platform layers, architectural views, and building blocks.
- Name the platform planes and the concern each addresses.
- Reason about architectural quality attributes and architectural boundaries.

## Concepts

This chapter **owns** the concepts below; other chapters reference them without redefining
them.

**Reference Architecture.** The canonical, technology-neutral structure that describes how
an AI Agent Platform is organized and how its parts relate. It is a shared model to design
against and to judge conformance to, not a specific system: many concrete platforms may
realize it. It exists to keep independently built parts coherent over the platform's life.

**Platform Layers.** The horizontal levels of abstraction into which the platform is
organized, each depending only on those beneath it, so that concerns are separated by level
of abstraction and change is contained. Layers express *how abstract* a part is.

**Architectural Views.** The distinct perspectives from which the architecture is described
— for example, structural, behavioral, deployment, and information views — each answering a
different set of questions for a different audience. No single view captures the whole;
together they do. The concrete models that render these views are kept as the framework's
[architecture](../../architecture/) material.

**Building Blocks.** The named, reusable architectural units from which the platform is
composed, each with a defined responsibility and interface. Building blocks are the
vocabulary of the architecture; they realize the domain model's aggregates and services as
structural elements without prescribing their implementation.

**Platform Planes.** The vertical divisions of the platform by concern, each a cohesive
area of responsibility with its own chapter. The reference architecture defines the
following planes and delegates their detail to their owners: the
[runtime plane](../07-runtime-platform/CHAPTER.md), the
[builder plane](../08-builder-platform/), the [provider plane](../09-provider-platform/),
the [plugin plane](../10-plugin-platform/), the [control plane](../11-control-plane/), the
[data plane](../12-data-platform/), and the [API plane](../13-api-platform/). A plane is a
concern; a layer is a level of abstraction; the two are orthogonal.

**Architectural Quality Attributes.** The system-level qualities the architecture must
achieve — such as performance, scalability, reliability, and evolvability — against which
structural decisions are judged. These are the architectural counterpart to the product
quality attributes owned by [Chapter 02](../02-product-thinking/CHAPTER.md); security as a
quality is owned by [Chapter 15 — Security](../15-security/), and observability of the
running system by [Chapter 14 — Observability](../14-observability/).

**Architectural Boundaries.** The deliberate seams between parts of the architecture across
which interaction happens only through explicit contracts. Architectural boundaries derive
from the domain's bounded contexts (owned by
[Chapter 05](../05-domain-driven-design/CHAPTER.md)) and realize the architectural
principle of making boundaries explicit; they are what allow planes and building blocks to
evolve independently.

## Principles

The reference architecture applies the architectural principles owned by
[Chapter 03](../03-engineering-principles/CHAPTER.md). The architecture-specific principles
that follow govern how those are expressed structurally.

- **Separate planes by concern.** Give each plane one cohesive responsibility, and let
  planes interact only across explicit boundaries.
- **Layer by abstraction.** Depend downward through layers; do not let a lower layer depend
  on a higher one.
- **Contract at every boundary.** Make each architectural boundary an explicit contract, so
  parts can change behind it.
- **Describe with multiple views.** Use complementary views rather than one diagram to
  capture the architecture.
- **Design for the quality attributes.** Judge structural decisions against the
  architectural quality attributes, and make the trade-offs among them explicit.
- **Keep the reference technology-neutral.** Express the architecture so that it outlives
  any particular technology that realizes it.

## Architecture

This section describes the structure of the *reference architecture* itself.

The architecture is understood along two orthogonal dimensions and rendered from several
views:

1. **Planes** divide the platform by concern (runtime, builder, provider, plugin, control,
   data, API), each owned by its chapter.
2. **Layers** divide it by abstraction, each depending only downward.
3. **Building blocks** populate the planes and layers, each with a defined responsibility
   and contract.
4. **Architectural boundaries**, derived from the domain's bounded contexts, separate these
   parts so they can evolve independently.
5. **Architectural views** describe the result from complementary perspectives, and
   **architectural quality attributes** are the standard every structural decision is held
   to.

Cross-cutting concerns — observability, security, evaluation, and the others — are not
planes; they are addressed within every plane and owned by their own chapters
([Chapter 14](../14-observability/), [Chapter 15](../15-security/),
[Chapter 16](../16-evaluation/), and beyond). This chapter defines the frame; the plane
chapters fill it in without contradicting it.

## Patterns

- **Plane-and-layer placement.** *Context:* situating a new part. Locate it by its concern
  (which plane) and its abstraction (which layer), so responsibility and dependencies are
  clear.
- **Boundary from bounded context.** *Context:* drawing an architectural seam. Derive it
  from a domain bounded context, so structure follows meaning.
- **View-per-audience.** *Context:* communicating the architecture. Present the view that
  answers the audience's questions rather than one diagram for all.

## Anti-patterns

- **Concern leakage across planes.** *Why it fails:* a plane that reaches into another's
  responsibility destroys cohesion and independent evolution. *Instead:* separate planes by
  concern and contract at boundaries.
- **Layer inversion.** *Why it fails:* a lower layer depending on a higher one couples
  abstraction levels and blocks change. *Instead:* depend only downward.
- **Single-view architecture.** *Why it fails:* one diagram cannot answer every question and
  hides important structure. *Instead:* describe with multiple views.
- **Technology-shaped reference.** *Why it fails:* a reference architecture built around a
  specific technology dates as the technology does. *Instead:* keep the reference
  technology-neutral.

## Best Practices

- Place every part by both plane and layer, and give it an explicit contract.
- Derive architectural boundaries from domain bounded contexts.
- Maintain complementary architectural views rather than a single diagram, keeping their
  models in the [architecture](../../architecture/) material.
- Judge structural decisions against the architectural quality attributes, and record the
  trade-offs.
- Delegate each plane's detail to its owning chapter and each cross-cutting concern to its
  own, without redefining them here.

## Examples

The following are illustrative, non-executable aids.

**Planes and the concern each addresses (detail owned by each plane's chapter):**

| Plane | Concern |
|-------|---------|
| Runtime | Executing agents and workflows |
| Builder | Authoring solutions on the platform |
| Provider | Integrating external models and services |
| Plugin | Extending the platform safely |
| Control | Governing, configuring, and operating the platform |
| Data | Storing, retrieving, and governing data |
| API | The contracts through which the platform is consumed |

**Planes versus layers (illustrative):** a plane names *what concern* a part serves; a
layer names *how abstract* it is. A single plane spans several layers, and a single layer
crosses several planes; placing a part requires both coordinates.

## Checklist

A reader is ready to proceed to
[Chapter 07 — Runtime Platform](../07-runtime-platform/CHAPTER.md) when they can confirm:

- [ ] I can explain what a reference architecture is and why it exists.
- [ ] I can distinguish planes, layers, and building blocks.
- [ ] I can name the platform planes and the concern each addresses.
- [ ] I can reason about architectural quality attributes and boundaries.

## References

- [Chapter 01 — Platform Vision](../01-platform-vision/CHAPTER.md) — the vision the
  architecture serves.
- [Chapter 03 — Engineering Principles](../03-engineering-principles/CHAPTER.md) — the
  architectural principles applied here.
- [Chapter 05 — Domain-Driven Design](../05-domain-driven-design/CHAPTER.md) — the domain
  boundaries architectural boundaries derive from.
- [Chapter 07 — Runtime Platform](../07-runtime-platform/CHAPTER.md) and the other plane
  chapters ([08](../08-builder-platform/), [09](../09-provider-platform/),
  [10](../10-plugin-platform/), [11](../11-control-plane/), [12](../12-data-platform/),
  [13](../13-api-platform/)) — own each plane's detail.
- [Chapter 14 — Observability](../14-observability/) and
  [Chapter 15 — Security](../15-security/) — own cross-cutting concerns addressed in every
  plane.
- [Architecture requirements](../../specifications/architecture-requirements/) and the
  [architecture](../../architecture/) models — the normative and visual counterparts.
- [Glossary](../21-glossary/) — canonical terms used in this chapter.

## Summary

The reference architecture is the canonical, technology-neutral structure of an AI Agent
Platform, serving the vision and applying the engineering principles and domain model. It
organizes the platform by concern into planes, by abstraction into layers, and by
responsibility into building blocks, separated by architectural boundaries derived from
domain bounded contexts, described through complementary architectural views, and judged
against architectural quality attributes. It is the frame the rest of the Handbook fills
in: the next chapter,
[Chapter 07 — Runtime Platform](../07-runtime-platform/CHAPTER.md), details the first plane,
the runtime that executes agents and workflows.
