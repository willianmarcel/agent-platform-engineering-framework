# Engineering Handbook — Architecture Overview

This document is the architectural overview of the APEF Engineering Handbook. It
summarizes the philosophy, organization, dependency model, concept ownership, and the
writing and reading strategies that govern the handbook. It is a design summary; it
contains no chapter content and defines no new rules — it consolidates what the companion
documents specify in detail.

Companion documents:
[Master Index](HANDBOOK.md) ·
[Table of Contents](TABLE_OF_CONTENTS.md) ·
[Knowledge Graph](KNOWLEDGE_GRAPH.md) ·
[Writing Guide](WRITING_GUIDE.md) ·
[Glossary Guidelines](GLOSSARY_GUIDELINES.md) ·
[Quality Criteria](QUALITY_CRITERIA.md)

## Handbook Philosophy

The handbook is the authoritative, narrative knowledge base for building AI Agent
Platforms with APEF. It is explanatory and connective where the
[`../specifications/`](../specifications/) are precise and normative: it teaches concepts,
principles, and architecture, then links out to the specifications, architecture models,
templates, and examples that make them concrete. It is the single source of truth from
which [`../docs/`](../docs/) is derived, and it is bound by four commitments — teach once
(no duplicated knowledge), stay consistent with the reference architecture, use one
canonical vocabulary, and remain mechanically checkable against measurable quality gates.

## Chapter Organization

The handbook's twenty-two chapters are organized into progressive tiers:

- **Orientation** — Chapter 00.
- **Why the platform exists** — Chapters 01–02 (vision, product thinking).
- **How we work** — Chapters 03–05 (principles, methodology, domain-driven design).
- **Architecture core** — Chapter 06 (the reference architecture).
- **Platform planes** — Chapters 07–13 (runtime, builder, provider, plugin, control,
  data, API).
- **Cross-cutting concerns** — Chapters 14–19 (observability, security, evaluation, UI/UX,
  testing, DevOps).
- **Direction** — Chapter 20 (roadmap).
- **Reference** — Chapter 21 (glossary), consulted at any time.

The full per-chapter contract (objective, scope, prerequisites, expected outputs, related
chapters, complexity, mandatory reading) is defined in the
[Table of Contents](TABLE_OF_CONTENTS.md).

## Dependency Model

- Each chapter declares **prerequisites** (its mandatory reading). Prerequisites are
  **acyclic**: a prerequisite always points to a lower-numbered chapter, so the numeric
  order is a valid reading order.
- A reference to a higher-numbered chapter is always a non-binding **related** link, never
  a prerequisite. This keeps the graph acyclic while allowing rich cross-linking.
- **Chapter 06 is intentionally the architecture hub.** Twelve chapters depend on it; this
  concentration is a ratified design choice that gives every plane and cross-cutting
  chapter one consistent anchor. Chapter 06 must therefore stay stable and authoritative.
- **Security is not modeled as a dependency.** It is cross-cutting: Chapter 15 owns
  security principles, and any chapter may carry an optional *Security Considerations*
  section describing implementation implications.

The graph, adjacency table, and reading tiers are in the
[Knowledge Graph](KNOWLEDGE_GRAPH.md).

## Concept Ownership

The primary defense against duplicated knowledge is single ownership: **each concept is
defined once, by exactly one owning chapter**, and every other chapter links to the owner
rather than restating it. Two ratified boundaries sharpen this model:

- **Evaluation vs Testing** — Chapter 16 (Evaluation) owns the quality of AI systems
  (model-dependent, non-deterministic behavior); Chapter 18 (Testing) owns the correctness
  of software systems (deterministic behavior). They are distinct disciplines and never
  merge.
- **The Glossary owns no concepts** — Chapter 21 standardizes terminology only. It gives
  each canonical term a short gloss and a link to the owning chapter; concept definitions
  live with their owners.

The ownership table is maintained in the [Knowledge Graph](KNOWLEDGE_GRAPH.md); terminology
rules are in the [Glossary Guidelines](GLOSSARY_GUIDELINES.md).

## Writing Strategy

- Every chapter uses one canonical template: twelve mandatory sections in fixed order,
  plus the optional *Security Considerations* section. The template and writing standards
  are in the [Writing Guide](WRITING_GUIDE.md).
- Chapters explain and connect; they never restate normative requirements that belong in
  the specifications — they link to them.
- Examples are illustrative and **non-executable**, consistent with the
  [`../examples/`](../examples/) policy.
- A chapter is "done" only when it passes every measurable gate in the
  [Quality Criteria](QUALITY_CRITERIA.md): structural and contract conformance,
  architectural consistency, no duplicated concepts, dependency integrity, validated
  references, terminology compliance, reviewed examples, completeness, and approval.

## Reading Strategy

- **Linear first pass:** read chapters in numeric order for a complete mental model.
- **Targeted reading:** to study one plane or concern, read its chapter after completing
  its mandatory prerequisites.
- **Reference use:** consult the Glossary at any time.

The authoritative reading policy is in the [Master Index](HANDBOOK.md).
