# Chapter 05 — Domain-Driven Design

## Introduction

This chapter defines how the problem domain of an AI Agent Platform is modeled, using
Domain-Driven Design. Its prerequisite is
[Chapter 04 — Development Methodology](../04-development-methodology/CHAPTER.md), within
whose specification-first methodology domain modeling is performed. Modeling the domain
well is what lets the platform's structure reflect the problem rather than the accidents of
a particular solution.

This chapter models; it does not architect or implement. The structure the model informs
is owned by [Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md).
The concepts here are the timeless building blocks of domain modeling, applied to agent
platforms; they carry no technology assumptions and no code.

## Objectives

After reading this chapter, a reader will be able to:

- Explain what Domain-Driven Design contributes to an AI Agent Platform.
- Define bounded contexts and establish a ubiquitous language within them.
- Distinguish entities, value objects, and aggregates, and know when each applies.
- Use domain services and domain events to express behavior the model requires.

## Concepts

This chapter **owns** the concepts below; other chapters reference them without redefining
them.

**Domain-Driven Design.** The approach of modeling software around the problem domain and
its language, so that the model — and the structure derived from it — reflects the business
reality rather than technical convenience. It gives the platform a principled way to divide
responsibility and to keep meaning consistent.

**Bounded Contexts.** The explicit boundaries within which a particular model and its terms
have a single, consistent meaning. A bounded context delimits where a word means one thing;
across contexts, the same word may mean something different, and the relationship between
contexts is made deliberate. Bounded contexts are the primary way domain complexity is
divided, and they inform — but are not the same as — architectural boundaries, owned by
[Chapter 06](../06-reference-architecture/CHAPTER.md).

**Ubiquitous Language.** The shared, precise language of a bounded context, used
identically by domain experts and engineers and reflected directly in the model. The
ubiquitous language is the discipline of naming; the canonical terms it produces are
standardized for the whole Handbook by
[Chapter 21 — Glossary](../21-glossary/), which owns terminology but no concepts.

**Entities.** Domain objects defined by a continuous identity that persists through change,
rather than by their attributes. Two entities with identical attributes are still distinct
if their identities differ; an entity's identity is what the model tracks over time.

**Value Objects.** Domain objects defined entirely by their attributes and having no
identity of their own. Value objects are interchangeable when equal, and modeling something
as a value object rather than an entity is a deliberate statement that only its value
matters.

**Aggregates.** Clusters of entities and value objects treated as a single unit of change
and consistency, with one entity serving as the aggregate's root through which the cluster
is accessed. Aggregates define the boundaries of consistency within a bounded context.

**Domain Services.** Domain behavior that does not naturally belong to any single entity or
value object, expressed as a stateless operation in the ubiquitous language. Domain
services capture meaningful actions of the domain that span or fall between the objects.

**Events.** Domain events — records that something meaningful has happened in the domain,
named in the past tense in the ubiquitous language. Domain events express the domain's
significant occurrences and are the domain-level meaning that later architectural and
runtime concerns may carry, without those concerns redefining them.

## Principles

- **Model the domain, not the solution.** Let the model reflect the problem and its
  language, not the convenience of a particular technology.
- **Bound every model.** State the context within which each model and its terms hold, and
  make cross-context relationships explicit.
- **Speak one language.** Use the ubiquitous language identically in conversation and in the
  model; a term means one thing within its context.
- **Make identity and consistency deliberate.** Choose entities, value objects, and
  aggregate boundaries to express exactly the identity and consistency the domain requires.
- **Express meaning as events.** Capture significant domain occurrences as named events so
  the domain's history and intent are explicit.

## Architecture

This section describes the structure of the *domain model*, not the architecture of a
platform, which is owned by
[Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md).

A domain model is organized as follows:

1. The domain is divided into **bounded contexts**, each with its own **ubiquitous
   language**.
2. Within a context, behavior and data are modeled as **entities**, **value objects**, and
   **domain services**.
3. **Aggregates** group these into units of consistency, each accessed through its root.
4. **Domain events** record what has meaningfully happened.

Bounded contexts and aggregates are the seams the reference architecture builds on:
[Chapter 06](../06-reference-architecture/CHAPTER.md) derives architectural boundaries from
domain boundaries, and the exploratory practice that surfaces domain events is recorded
under the framework's [event-storming](../../architecture/event-storming/) material.

## Patterns

- **Context mapping.** *Context:* several models interact. Make the relationships between
  bounded contexts explicit, so each context keeps its own language and meaning.
- **Aggregate-scoped consistency.** *Context:* deciding what must change together. Draw
  aggregate boundaries around exactly the invariants that must hold, and no wider.
- **Event-first domain expression.** *Context:* capturing behavior. Identify the meaningful
  domain events first; they reveal the entities, aggregates, and services the model needs.

## Anti-patterns

- **Anemic model.** *Why it fails:* a model that holds data but no domain meaning pushes
  behavior elsewhere and loses the value of modeling. *Instead:* express behavior in
  entities, value objects, and domain services.
- **Unbounded language.** *Why it fails:* using one term to mean several things across the
  platform creates ambiguity and error. *Instead:* bound every model and speak one
  language within it.
- **Oversized aggregates.** *Why it fails:* aggregates drawn too large couple unrelated
  changes and harm evolvability. *Instead:* scope aggregates to the true invariants.
- **Model driven by technology.** *Why it fails:* shaping the domain model around a
  technology distorts the problem. *Instead:* model the domain, not the solution.

## Best Practices

- Establish bounded contexts and their ubiquitous language before modeling within them.
- Choose entities versus value objects by asking whether identity matters.
- Scope aggregates to the invariants that must hold together, and access them through the
  root.
- Name domain events in the past tense in the ubiquitous language.
- Let domain boundaries inform architectural boundaries in
  [Chapter 06](../06-reference-architecture/CHAPTER.md) rather than the reverse.

## Examples

The following are illustrative, non-executable aids.

**Choosing a modeling element:**

| If the domain cares about… | Model it as… |
|----------------------------|--------------|
| A thing's continuous identity over time | An entity |
| Only a thing's value, interchangeable when equal | A value object |
| A set of objects that must stay consistent together | An aggregate (accessed via its root) |
| Behavior spanning objects, belonging to none | A domain service |
| Something meaningful that has happened | A domain event |

**Bounded context boundary (illustrative):** the term used for a concept in one context
may legitimately differ from its meaning in another; the boundary is where that meaning is
allowed to change, and the relationship across it is stated deliberately.

## Checklist

A reader is ready to proceed to
[Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md) when they can
confirm:

- [ ] I can explain what Domain-Driven Design contributes and why the framework uses it.
- [ ] I can define a bounded context and its ubiquitous language.
- [ ] I can choose between entities, value objects, and aggregates for a given need.
- [ ] I can use domain services and domain events appropriately.

## References

- [Chapter 04 — Development Methodology](../04-development-methodology/CHAPTER.md) — the
  methodology within which domain modeling is performed.
- [Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md) — derives
  architectural boundaries from domain boundaries.
- [Chapter 21 — Glossary](../21-glossary/) — standardizes the terms the ubiquitous language
  produces.
- [Domain specifications](../../specifications/domains/) — the normative counterpart to this
  chapter.
- [Event-storming material](../../architecture/event-storming/) — the practice that surfaces
  domain events.
- [Glossary](../21-glossary/) — canonical terms used in this chapter.

## Summary

Domain-Driven Design models an AI Agent Platform around its problem domain and language, so
structure reflects reality. The domain is divided into bounded contexts, each speaking one
ubiquitous language; within them, entities, value objects, aggregates, and domain services
express identity, consistency, and behavior, and domain events record what has meaningfully
happened. These models are not architecture, but they are the seams the architecture is
built on: the next chapter,
[Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md), turns the
domain model and the engineering principles into the canonical structure of the platform.
