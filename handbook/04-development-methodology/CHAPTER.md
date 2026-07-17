# Chapter 04 — Development Methodology

## Introduction

This chapter defines the methodology by which an AI Agent Platform is developed: the way
engineering work moves from intent to accepted result. Its prerequisite is
[Chapter 03 — Engineering Principles](../03-engineering-principles/CHAPTER.md), whose
principles this methodology puts into practice. Where Chapter 03 states *what standards*
work is held to, this chapter defines *how work proceeds* to meet them.

This is methodology, not principle and not architecture. It describes process and
governance at an enduring level, independent of any specific tool, tracker, or vendor. It
does not prescribe a particular technology and contains no implementation.

## Objectives

After reading this chapter, a reader will be able to:

- Explain Specification-Driven Development and why the framework adopts it.
- Describe how iterative development and specification-first work fit together.
- Explain the role of architecture governance and decision records.
- Apply a definition of done and a review process to accept work.
- Situate a unit of work within the delivery lifecycle.

## Concepts

This chapter **owns** the concepts below; other chapters reference them without redefining
them.

**Spec Driven Development.** The methodology in which intent is captured as specifications
before implementation, and implementation is held accountable to those specifications.
Specification-Driven Development makes decisions explicit and reviewable early, when they
are cheapest to change, and gives every later artifact a source of truth to satisfy. It is
the framework's central methodology, referenced in orientation by
[Chapter 00](../00-introduction/CHAPTER.md) and owned here.

**Iterative Development.** The practice of advancing in small, complete increments, each of
which delivers reviewable value and improves understanding. Iteration and
specification-first work are complementary: specifications state intent; iterations refine
both the intent and its realization as understanding grows.

**Architecture Governance.** The set of practices that keep architectural decisions
coherent with the principles and the reference architecture over time — deciding which
choices need scrutiny, who reviews them, and how consistency is maintained. Governance
guides architecture without centralizing every decision.

**Decision Records.** Durable, numbered records of significant decisions — their context,
the options considered, and their consequences — preserved so that the reasoning behind the
platform remains available. Decision records make governance auditable and decisions
traceable.

**Definition of Done.** The explicit, agreed criteria a unit of work must satisfy to be
considered complete. A definition of done makes "finished" objective rather than a matter
of opinion, and it is where quality-by-design is enforced.

**Engineering Workflow.** The repeatable flow a unit of work follows from proposal to
accepted result: how it is specified, decided, produced, reviewed, and integrated. The
workflow is the connective tissue of the methodology.

**Review Process.** The practice by which work is examined against the specifications,
principles, and definition of done before it is accepted. Review is how the methodology
turns individual work into shared, trusted results.

**Delivery Lifecycle.** The stages a body of work passes through over its life — from
discovery and specification, through iterative development and review, to release and
subsequent evolution. The lifecycle situates every activity in a larger, repeatable arc.

## Principles

- **Specify before building.** Capture intent as a specification before implementation, so
  decisions are explicit and reviewable early.
- **Iterate in complete increments.** Advance in small steps that each deliver reviewable
  value and improve understanding.
- **Record significant decisions.** Preserve the context and consequences of decisions that
  shape the platform.
- **Define done explicitly.** Agree the criteria for completeness before work is accepted.
- **Review against intent.** Judge work against its specification, the principles, and the
  definition of done — not against preference.
- **Govern for coherence.** Keep architectural decisions consistent with the principles and
  the reference architecture, without centralizing every choice.

## Architecture

This section describes the structure of the *methodology*, not the architecture of a
platform, which is owned by
[Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md).

The methodology connects its concepts into one repeatable flow:

1. **Discovery** frames a need and its intent.
2. **Specification** (Spec-Driven Development) states what must be true, backed by
   **decision records** where the choices are significant.
3. **Iterative development** realizes the specification in small, complete increments.
4. **Review**, against the **definition of done**, accepts or returns the work.
5. **Delivery** integrates and releases the result, after which **evolution** returns the
   cycle to discovery.

**Architecture governance** runs across the whole flow, keeping decisions coherent with
[Chapter 03](../03-engineering-principles/CHAPTER.md) and
[Chapter 06](../06-reference-architecture/CHAPTER.md). Measurement of results and testing
are delegated to [Chapter 16 — Evaluation](../16-evaluation/) and
[Chapter 18 — Testing](../18-testing/).

## Patterns

- **Specification-first change.** *Context:* any significant change. Write or update the
  specification before implementing, so intent leads and implementation follows.
- **Decision record at the fork.** *Context:* a choice with lasting consequences. Capture
  the decision and its rationale where the reasoning must survive.
- **Definition-of-done gating.** *Context:* accepting work. Admit work only when it meets
  the agreed criteria, making completeness objective.

## Anti-patterns

- **Implementation-first development.** *Why it fails:* building before intent is explicit
  buries decisions in code where they cannot be reviewed. *Instead:* specify before
  building.
- **Undocumented decisions.** *Why it fails:* decisions without records are relitigated and
  their rationale is lost. *Instead:* record significant decisions.
- **Implicit done.** *Why it fails:* "done" without agreed criteria invites inconsistency
  and rework. *Instead:* define done explicitly.
- **Big-bang delivery.** *Why it fails:* large, infrequent integration hides risk until it
  is expensive. *Instead:* iterate in complete increments.

## Best Practices

- Lead every significant change with a specification, authored from the framework's
  templates.
- Record decisions that shape the platform, and keep them where governance can find them.
- Agree the definition of done before starting, and review against it before accepting.
- Keep increments small and complete, integrating often.
- Delegate measurement to [Chapter 16](../16-evaluation/) and testing to
  [Chapter 18](../18-testing/) rather than duplicating them here.

## Examples

The following are illustrative, non-executable aids.

**The delivery lifecycle at a glance:**

| Stage | Question it answers |
|-------|---------------------|
| Discovery | What need are we addressing, and why? |
| Specification | What must be true for this to be right? |
| Iterative development | What is the next complete increment? |
| Review | Does the work meet its specification and definition of done? |
| Delivery | Is it integrated, released, and communicated? |
| Evolution | What did we learn, and what changes next? |

**A definition of done (illustrative shape, not a fixed list):**

- The specification is satisfied and its acceptance criteria are met.
- Significant decisions are recorded.
- The work is reviewed and consistent with the principles and reference architecture.

## Checklist

A reader is ready to proceed to
[Chapter 05 — Domain-Driven Design](../05-domain-driven-design/CHAPTER.md) when they can
confirm:

- [ ] I can explain Specification-Driven Development and why it is used.
- [ ] I understand how iteration and specification-first work complement each other.
- [ ] I know when to write a decision record and what it preserves.
- [ ] I can state a definition of done and review work against it.
- [ ] I can place a unit of work within the delivery lifecycle.

## References

- [Chapter 03 — Engineering Principles](../03-engineering-principles/CHAPTER.md) — the
  principles this methodology applies.
- [Chapter 05 — Domain-Driven Design](../05-domain-driven-design/CHAPTER.md) — the modeling
  approach used within specification.
- [Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md) — the
  architecture governance keeps coherent.
- [Chapter 16 — Evaluation](../16-evaluation/) — owns how results are measured.
- [Chapter 18 — Testing](../18-testing/) — owns how software is tested.
- [Workflow](../../bootstrap/WORKFLOW.md) and
  [Quality Gates](../../bootstrap/QUALITY_GATES.md) — the governance counterparts to this
  chapter.
- [Glossary](../21-glossary/) — canonical terms used in this chapter.

## Summary

The development methodology puts the engineering principles into practice: intent is
captured as specifications before implementation, realized through iterative development,
governed by architecture governance and preserved in decision records, and accepted only
against an explicit definition of done through a review process — all situated in a
repeatable delivery lifecycle. Methodology decides how work proceeds; the next chapter,
[Chapter 05 — Domain-Driven Design](../05-domain-driven-design/CHAPTER.md), defines how the
problem domain is modeled within that methodology.
