# Chapter 00 — Introduction

> **Note on placement.** The Foundation phase froze this chapter's
> [`README.md`](README.md) as a directory-contract README (bound by Architecture Decision
> AD-0001). The chapter content therefore lives in this sibling `CHAPTER.md` rather than
> in the frozen README. See the Self-Review for the authorization path to establish a
> chapter-content-file convention.

## Introduction

This is the opening chapter of the Agent Platform Engineering Framework (APEF)
Engineering Handbook. Its purpose is to establish context: what APEF is, why it exists,
who it serves, and how to read the handbook that follows. It does not describe how a
platform is built — architecture, runtime behavior, and the platform's building blocks
are the subject of later chapters.

APEF is an **engineering framework**: a body of principles, specifications,
architecture, playbooks, templates, and reference research that guides the construction
of enterprise-grade AI Agent Platforms. It is deliberately *not* a platform, a software
development kit, or a runnable system. The distinction between a framework and a platform
is the single most important idea to carry out of this chapter, and it defines the
boundary of everything the handbook covers: the handbook explains how to design and
reason about such a platform; it does not ship one.

This chapter has **no prerequisites**. It is the entry point to the handbook and to the
wider repository, and every reader — regardless of role — should begin here.

What is intentionally outside the scope of this chapter, and of APEF as a whole:

- **Implementation.** APEF produces specifications and architecture, not application,
  API, frontend, or backend code.
- **A specific product.** APEF is technology- and vendor-neutral guidance, not a
  particular platform release.
- **The platform's internals.** The runtime, the building blocks of a platform, and how
  they are orchestrated are introduced in dedicated later chapters, not here.

## Objectives

After reading this chapter, a reader will be able to:

- Explain what APEF is and how a framework differs from a platform.
- State the problems APEF is intended to solve and the outcomes it targets.
- Determine whether they are within APEF's intended audience, and whether APEF fits
  their situation.
- Choose an effective reading path through the handbook for their role.
- Describe, at a high level, the philosophy that guides the framework and how the
  framework is organized.
- Recognize what APEF intentionally leaves out.

## Concepts

This chapter introduces only the orientation-level vocabulary needed to navigate the
handbook. Deeper concepts are defined in the chapters that own them; this chapter links
to those owners rather than defining their concepts here.

- **Engineering framework.** A durable, reusable body of engineering knowledge and
  standards that guides how systems in a domain are designed and built. APEF applies this
  idea to AI Agent Platforms. Comparable established examples — offered only as
  familiar reference points — include the Spring Framework, .NET Aspire, Backstage, the
  Kubernetes documentation, and the AWS Well-Architected Framework.
- **AI Agent Platform.** The class of system APEF guides teams to build. The term is a
  canonical term of the handbook; its definition and the platform's building blocks are
  the subject of later chapters and the [Glossary](../21-glossary/). This chapter names
  the term but does not elaborate the platform's internals.
- **Specification-Driven Development (SDD).** The development methodology APEF adopts, in
  which intent is captured as specifications and architecture before implementation. It
  is introduced here only as context; the methodology itself is owned by
  [Chapter 04 — Development Methodology](../04-development-methodology/).
- **Single source of truth.** The handbook is the authored, authoritative body of
  knowledge; published documentation is derived from it. This is a property of how the
  framework is maintained, not a platform concept.

For the canonical terms and forbidden synonyms used across the handbook, see the
[Glossary Guidelines](../GLOSSARY_GUIDELINES.md) and [Chapter 21 — Glossary](../21-glossary/).

## Principles

APEF is guided by a small set of durable commitments. This chapter states them at an
orientation level; the full treatment of engineering principles is owned by
[Chapter 03 — Engineering Principles](../03-engineering-principles/), and the methodology
that operationalizes them by [Chapter 04 — Development Methodology](../04-development-methodology/).

- **Guidance over implementation.** The framework exists to inform decisions that outlast
  any single product, not to provide code.
- **Specification before implementation.** Decisions are captured as specifications and
  architecture first, so that intent is explicit and reviewable.
- **Longevity.** The framework is written to be maintained for years; maintainability,
  extensibility, and long-term evolution take precedence over short-term convenience.
- **Documentation as a first-class artifact.** Knowledge is a deliverable, held to the
  same quality standard as any engineered component.
- **Define once, reference everywhere.** Each concept has a single owning chapter; other
  chapters link to it rather than restating it, which keeps the knowledge base coherent.

## Architecture

This section describes how the *framework* is organized — its structure as a body of
knowledge. It does not describe the architecture of an AI Agent Platform, which is the
subject of [Chapter 06 — Reference Architecture](../06-reference-architecture/).

The repository is organized into distinct areas, each with a documented responsibility:
the [handbook](../../README.md) (the narrative knowledge base you are reading), the
normative [specifications](../../specifications/), the
[architecture](../../architecture/) models, and supporting areas for playbooks,
templates, examples, reference studies, and decisions. The authoritative account of the
repository and its governance is the
[Master Plan](../../bootstrap/MASTER_PLAN.md).

The handbook itself is organized as an ordered sequence of chapters grouped into
progressive tiers, from orientation, through the framework's vision and working methods,
to the reference architecture, the platform's concerns, and its direction. The full
per-chapter contract is defined in the [Table of Contents](../TABLE_OF_CONTENTS.md), the
dependencies between chapters in the [Knowledge Graph](../KNOWLEDGE_GRAPH.md), and the
reading policy in the [Master Index](../HANDBOOK.md). The topics that describe a platform
directly — its runtime, its building blocks, and how they are composed and operated —
each have their own later chapter and are not previewed here.

## Patterns

Recommended ways to use the handbook effectively:

- **Read linearly on the first pass.** *Context:* you are new to APEF. The chapter
  numbering encodes a deliberate progression; reading in order builds a complete mental
  model. *Trade-off:* slower than jumping to a topic, but avoids missing foundational
  context.
- **Read by dependency for targeted study.** *Context:* you need one specific topic.
  Read that chapter after completing its declared prerequisites, listed in the
  [Table of Contents](../TABLE_OF_CONTENTS.md). *Trade-off:* faster to a specific answer,
  provided prerequisites are respected.
- **Treat the handbook as the source of truth.** *Context:* you need authoritative
  guidance. Rely on the handbook and follow its links to specifications rather than on
  derived or external copies.

## Anti-patterns

Approaches to avoid, and what to do instead:

- **Treating APEF as a platform or SDK to install.** *Why it fails:* APEF ships no
  runnable software; expecting an artifact to deploy leads to misuse. *Instead:* use it
  as guidance — apply the *guidance over implementation* principle.
- **Skipping declared prerequisites.** *Why it fails:* later chapters assume the mental
  models established earlier; skipping them produces misunderstanding. *Instead:* follow
  the *read by dependency* pattern.
- **Duplicating knowledge across chapters.** *Why it fails:* restating a concept where it
  is not owned causes drift and contradiction. *Instead:* apply *define once, reference
  everywhere* and link to the owning chapter.
- **Reading the introduction as a product pitch.** *Why it fails:* it invites
  expectations of features rather than engineering guidance. *Instead:* read it as the
  opening chapter of a technical book that establishes context.

## Best Practices

- Confirm which reading path fits your role before diving in (see Examples below).
- Respect each chapter's prerequisites; use the [Knowledge Graph](../KNOWLEDGE_GRAPH.md)
  to plan a path.
- Use the canonical vocabulary from the [Glossary Guidelines](../GLOSSARY_GUIDELINES.md);
  avoid synonyms that fragment meaning.
- When contributing, follow Specification-Driven Development and the process in
  [`CONTRIBUTING.md`](../../CONTRIBUTING.md) and
  [`bootstrap/WORKFLOW.md`](../../bootstrap/WORKFLOW.md); record significant decisions as
  Architecture Decision Records.
- Return to the handbook as the source of truth rather than relying on derived copies.

## Examples

The following are illustrative, non-executable aids for orientation.

**Role-based reading paths (starting points after this chapter):**

| Role | Suggested starting focus after Chapter 00 |
|------|-------------------------------------------|
| Software Engineer | [01 Platform Vision](../01-platform-vision/) → [03 Engineering Principles](../03-engineering-principles/) → [04 Development Methodology](../04-development-methodology/) |
| Solution / Enterprise Architect | [01 Platform Vision](../01-platform-vision/) → [06 Reference Architecture](../06-reference-architecture/) |
| AI Engineer | [01 Platform Vision](../01-platform-vision/) → [06 Reference Architecture](../06-reference-architecture/) |
| Engineering Manager / Technical Leader | [01 Platform Vision](../01-platform-vision/) → [02 Product Thinking](../02-product-thinking/) → [20 Roadmap](../20-roadmap/) |

The full ordering and dependencies are authoritative in the
[Table of Contents](../TABLE_OF_CONTENTS.md) and [Knowledge Graph](../KNOWLEDGE_GRAPH.md).

**Decision aid — is APEF the right fit?**

- APEF fits when: you are designing or governing an AI Agent Platform and want durable,
  vendor-neutral engineering guidance and specifications.
- APEF does not fit when: you are looking for a runnable platform, an SDK, or copy-paste
  implementation code — APEF intentionally provides none of these.

## Checklist

A reader is ready to proceed to [Chapter 01 — Platform Vision](../01-platform-vision/)
when they can confirm:

- [ ] I can explain that APEF is an engineering framework, not a platform or SDK.
- [ ] I can state, in one sentence, the problem APEF addresses.
- [ ] I know whether I am within APEF's intended audience.
- [ ] I have chosen a reading path suited to my role.
- [ ] I understand what APEF intentionally leaves out.

## References

- [Master Index](../HANDBOOK.md) — reading strategy, audience, and policy.
- [Table of Contents](../TABLE_OF_CONTENTS.md) — the official chapter structure.
- [Knowledge Graph](../KNOWLEDGE_GRAPH.md) — chapter dependencies and reading tiers.
- [Writing Guide](../WRITING_GUIDE.md) — the canonical chapter template this chapter follows.
- [Glossary Guidelines](../GLOSSARY_GUIDELINES.md) — canonical terminology.
- [Chapter 01 — Platform Vision](../01-platform-vision/) — the next chapter.
- [Chapter 21 — Glossary](../21-glossary/) — the term reference.
- [Repository overview](../../README.md) — the repository entry point.
- [Master Plan](../../bootstrap/MASTER_PLAN.md) — the governing plan for the framework.

## Summary

APEF is an engineering framework that guides the construction of enterprise-grade AI
Agent Platforms; it is not itself a platform, an SDK, or runnable software. It exists to
make platform-engineering decisions explicit, durable, and coherent, using
Specification-Driven Development and a single authoritative body of knowledge. It serves
software engineers, solution and enterprise architects, AI engineers, engineering
managers, and technical leaders; it is not suited to those seeking runnable software or
implementation code. The handbook is best read linearly on a first pass and by
dependency for targeted study, guided by the canonical vocabulary and the framework's
core commitments. With this context established, the next chapter,
[Chapter 01 — Platform Vision](../01-platform-vision/), sets out the long-term vision and
success criteria for the platforms APEF guides teams to build.
