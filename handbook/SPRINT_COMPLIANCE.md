# Sprint 02 — Compliance

Compliance verification for Chapters 03–07 against the frozen Handbook Architecture. This
is a sprint record, not a chapter.

## Writing Guide Compliance

- **Canonical template:** all five chapters use the twelve mandatory sections in order
  (Introduction, Objectives, Concepts, Principles, Architecture, Patterns, Anti-patterns,
  Best Practices, Examples, Checklist, References, Summary). Verified programmatically.
- **Optional Security Considerations:** omitted in every chapter; these are foundational
  chapters whose security implications are owned by Chapter 15, which they reference rather
  than pre-empt. Omission is permitted.
- **Chapter directory layout:** each chapter has `README.md`, `CHAPTER.md`, `examples/`,
  `images/`, `references/`; the READMEs received navigation-only `Reading` sections.
- **Style:** reference-handbook register throughout — no blog or marketing tone, no
  tutorials, no code, no technology recommendations, no vendor terms. Principles are stated
  to remain valid independent of technology evolution.

## Quality Criteria Compliance

All five chapters satisfy Gates 1–9 of the [Quality Criteria](QUALITY_CRITERIA.md);
Gate 10 (review and approval) is pending the Architecture Board. Specifically: structure
and contract conformance, architectural consistency, no duplicated concepts, dependency
integrity, validated references, terminology compliance, non-executable examples, and
completeness with no prohibited placeholders. Evidence is recorded in the
[Sprint Summary](SPRINT_SUMMARY.md) Quality Gates table.

## Glossary Compliance

- Chapters use canonical terminology and no forbidden synonyms (checked against the
  [Glossary Guidelines](GLOSSARY_GUIDELINES.md)): "AI Agent Platform", "Provider",
  "Plugin", "Runtime", "Control Plane", and "Reference Architecture" are used in their
  canonical forms; "engine/executor", "vendor/connector", "extension/add-on", "pipeline",
  and "bot/assistant" do not appear as concept terms.
- Chapter 05 owns the *ubiquitous-language method*; Chapter 21 (Glossary) standardizes the
  resulting terms and owns no concepts — consistent with the ratified clarification.
- Specialized terms are used in the sense their owning chapter defines; the Glossary
  chapter remains the terminology standard.

## Concept Ownership Compliance

- **Single ownership verified:** 66 distinct bold concept definitions across Chapters
  00–07, with **zero** concepts defined in more than one chapter.
- **No redefinition of prior chapters:** Chapters 03–07 reference concepts owned by 00–02
  (for example product evolution, product quality attributes, product boundaries) without
  redefining them, and draw explicit distinctions where terms are adjacent (Evolvability vs
  Product Evolution; Architectural vs Product Quality Attributes; Architectural vs Product
  vs Runtime Boundaries).
- **No redefinition of later chapters:** planes and cross-cutting concerns (08–16) are
  named and delegated to their owners, not defined here.
- **Intra-sprint boundaries hold:** Architectural Boundaries (06) derive from Bounded
  Contexts (05); Runtime Boundaries (07) realize Architectural Boundaries (06); Decision
  Records (04) are referenced by 03 and 06 as a practice, defined only in 04.

## Cross-Reference Validation

- All internal links across the five chapter directories resolve: **220/220**.
- Forward references (from 06 and 07) target existing chapter directories and name owning
  chapters; no reference points to a non-existent path.
- Prerequisite links match the [Knowledge Graph](KNOWLEDGE_GRAPH.md); the graph stays
  acyclic.

## Architectural Consistency

- **Altitude is consistent within each chapter and ascends correctly across the sprint:**
  principles (03) → methodology (04) → domain modeling (05) → architecture (06) → runtime
  plane (07). No chapter descends into implementation, code, or technology choice.
- **The hub holds:** Chapter 06 sets the frame (planes, layers, building blocks, views,
  boundaries, quality attributes); Chapter 07 fills the runtime plane without contradicting
  it.
- **Boundary lineage is coherent:** domain → architectural → runtime boundaries form one
  consistent model.
- **No conflicting terminology** was found across the five chapters or against Chapters
  00–02.

## Outstanding Items (for the Board)

- Gate 10 (approval) pending review.
- Reciprocal cross-links deferred until the counterpart chapters exist: product ↔
  architectural quality attributes (02 ↔ 06); runtime ↔ data persistence seam (07 ↔ 12).
- Governance seams noted in prior chapters remain open (README `Reading` exception and the
  `CHAPTER.md` convention are applied but not yet recorded as formal Architecture
  Decisions).
