# APEF Engineering Handbook — Master Index

> **Note on placement.** The Foundation phase froze [`README.md`](README.md) as a
> directory-contract README (bound by Architecture Decision AD-0001). This master index
> is therefore delivered as `HANDBOOK.md` rather than by modifying the frozen README.
> See the Handbook Architecture Review for the authorization path to relocate it.

This is the master index of the APEF Engineering Handbook — the authoritative knowledge
base for the Agent Platform Engineering Framework. It defines how the handbook is read,
written, and versioned. It is an index and policy document; it contains no chapter
content.

Companion design documents:
[Table of Contents](TABLE_OF_CONTENTS.md) ·
[Knowledge Graph](KNOWLEDGE_GRAPH.md) ·
[Writing Guide](WRITING_GUIDE.md) ·
[Glossary Guidelines](GLOSSARY_GUIDELINES.md) ·
[Quality Criteria](QUALITY_CRITERIA.md)

## Handbook Purpose

The handbook is the narrative, book-like body of knowledge that explains how to design
and build enterprise-grade AI Agent Platforms with APEF. Where specifications are
precise and normative, the handbook is explanatory and connective: it teaches concepts,
principles, and architecture, and links outward to the specifications, architecture
models, templates, and examples that make them concrete. It is the single source of
truth from which the [`../docs/`](../docs/) published documentation is derived.

## Intended Audience

- **Platform architects** designing an AI Agent Platform with APEF.
- **Platform builders and engineers** implementing runtimes, providers, and plugins.
- **Operators** running the platform (control plane, observability, DevOps).
- **Product and engineering leaders** shaping vision, roadmap, and quality standards.

Readers are assumed to be practicing software engineers; the handbook does not teach
general programming, but it does not assume prior AI-agent-platform experience.

## Reading Strategy

- **Linear first pass:** read chapters in numeric order for a complete mental model.
  The numbering encodes a deliberate progression from vision to cross-cutting concerns.
- **Targeted reading:** to study one plane or concern, read its chapter after
  completing its mandatory prerequisites, listed per chapter in the
  [Table of Contents](TABLE_OF_CONTENTS.md) and visualized in the
  [Knowledge Graph](KNOWLEDGE_GRAPH.md).
- **Reference use:** the Glossary is a living reference and may be consulted at any time.

## Learning Path

The chapters group into tiers that build on one another:

1. **Orientation** — Chapter 00.
2. **Why the platform exists** — Chapters 01–02.
3. **How we work** — Chapters 03–05.
4. **Architecture core** — Chapter 06 (the hub every later chapter builds on).
5. **Platform planes** — Chapters 07–13.
6. **Cross-cutting concerns** — Chapters 14–19.
7. **Direction** — Chapter 20.
8. **Reference** — Chapter 21 (anytime).

## Chapter Dependency Rules

- Every chapter declares its **prerequisites** (its mandatory reading) in the
  [Table of Contents](TABLE_OF_CONTENTS.md).
- Prerequisites are **acyclic**: a prerequisite always points to a lower-numbered
  chapter. A reference to a higher-numbered chapter is always a non-binding *related*
  link, never a prerequisite.
- A chapter may be written only after its prerequisites are written and approved.
- Chapter 06 (Reference Architecture) is the central hub; the plane and cross-cutting
  chapters depend on it and must not contradict it.

## Cross-Reference Policy

- Every reference to another chapter, specification, or repository artifact is a
  **relative Markdown link** (consistent with the repository-wide convention).
- A concept is defined once, by its **owning chapter** (see the ownership table in the
  [Knowledge Graph](KNOWLEDGE_GRAPH.md)); other chapters link to the owner rather than
  restating it. This is the primary control against duplicated knowledge.
- Cross-references point to the smallest relevant unit (a chapter, or a specific
  specification) and are validated as part of the [Quality Criteria](QUALITY_CRITERIA.md).

## Writing Standards

Every chapter uses the single canonical chapter template and the terminology rules
defined in the companion documents:

- Structure and section-by-section rules: [Writing Guide](WRITING_GUIDE.md).
- Terminology, naming, and canonical terms: [Glossary Guidelines](GLOSSARY_GUIDELINES.md).
- Definition of Done and measurable gates: [Quality Criteria](QUALITY_CRITERIA.md).

Ratified architectural clarifications that all chapters uphold:

- **Architecture hub:** Chapter 06 is intentionally the hub; its dependency concentration
  is accepted (see [Knowledge Graph](KNOWLEDGE_GRAPH.md)).
- **Security is cross-cutting:** Chapter 15 owns security principles; any chapter may add an
  optional *Security Considerations* section for implementation implications only.
- **Evaluation ≠ Testing:** Chapter 16 (AI systems) and Chapter 18 (software systems) are
  distinct disciplines and are kept separate throughout.
- **Glossary owns no concepts:** Chapter 21 standardizes terminology only; concept
  definitions belong to their owning chapters.

## Versioning Policy

- The handbook is versioned as a whole, using Semantic Versioning, and its releases are
  recorded in the repository [`../CHANGELOG.md`](../CHANGELOG.md).
- **Major**: a change that reorganizes chapters, alters dependencies, or changes the
  canonical chapter template.
- **Minor**: adding a chapter's content, or adding substantial new material within the
  existing structure.
- **Patch**: corrections, clarifications, and reference fixes that do not change meaning.
- The handbook's structure (this index and its companions) is itself an artifact under
  version control; structural changes follow the process in
  [`../bootstrap/WORKFLOW.md`](../bootstrap/WORKFLOW.md) and, where they touch frozen
  Foundation artifacts, require an Architecture Decision.
