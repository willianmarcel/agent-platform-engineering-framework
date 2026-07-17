# Sprint 03 — Compliance

Compliance verification for Chapters 08–12 against the frozen Handbook Architecture. This
is a sprint record, not a chapter.

## Writing Guide

- All five chapters use the twelve mandatory sections in order (verified programmatically);
  the optional Security Considerations section is omitted, with security owned by
  Chapter 15, which the chapters reference rather than pre-empt.
- Each chapter has the ratified directory layout, and its README received a navigation-only
  `Reading` section.
- Register is reference-handbook throughout: no blog or marketing tone, no tutorials, no
  code, no implementation, and no technology or product recommendation.

## Glossary

- Canonical terminology is used; no forbidden synonyms appear as concept terms
  ("engine/executor", "vendor/connector" as a synonym for provider, "bot/assistant",
  "pipeline" are absent).
- Overloaded roots are explicitly qualified and cross-linked: Product Capabilities (02),
  Provider Capabilities (09), and plugin Capabilities (10); governance Policies (11) versus
  Routing Policies (09).
- The Glossary (Chapter 21) remains the terminology standard and owns no concepts.

## Concept Ownership

- **Single ownership verified:** 125 distinct bold concept definitions across Chapters
  00–12, with **zero** concepts defined in more than one chapter.
- Chapters 08–12 reference concepts owned by prior chapters (product capabilities, product
  extensibility, domain events, runtime state/memory/session) without redefining them, and
  draw explicit distinctions where terms are adjacent.
- **One flagged item:** Chapter 11 owns the governance/operation of Identity and
  Authorization while Chapter 15 (frozen Knowledge Graph) owns the security model of
  identity; the split is stated in Chapter 11 and recorded as Risk 1 in the
  [Sprint Summary](SPRINT_03_SUMMARY.md), pending Board ratification.

## Architectural Consistency

- Altitude is consistent: every chapter describes an architectural capability —
  responsibilities, boundaries, relationships — and none descends into implementation.
- Strict separation of concerns holds across the six planes (builder, provider, plugin,
  control, data, atop runtime): creation, execution, intelligence, extension, governance,
  and persistence do not overlap.
- The mandated architectural principles (provider-, framework-, cloud-, runtime-agnostic;
  vendor-neutral; protocol-oriented; extensible, composable, observable, governable by
  design) appear consistently in all five chapters.

## Cross-Reference Integrity

- All internal links across the five chapter directories resolve: **209/209**.
- Forward references target existing chapter directories and name owning chapters; none
  points to a non-existent path.

## Dependency Graph

- Prerequisites match the [Knowledge Graph](KNOWLEDGE_GRAPH.md) (08: 06,07; 09: 06,07; 10:
  06,08; 11: 06; 12: 06). The graph remains acyclic; all prerequisites are authored.

## Technology Neutrality

- Automated scan for programming languages, clouds, frameworks, orchestration libraries,
  and data technologies found **no** occurrences in any chapter. The chapters remain valid
  regardless of technology choice.
- MCP and A2A are described strictly as architectural protocols (the protocol-oriented
  principle), not as products or implementations.

## Vendor Neutrality

- Automated scan for provider and vendor names (of the kind the sprint brief prohibited)
  found **no** occurrences. Chapter 09 establishes provider abstraction as a long-term
  principle without naming any provider; providers are treated as an abstract role defined
  by supplied capability.

## Outstanding Items (for the Board)

- Gate 10 (approval) pending review.
- Ratify the Chapter 11 / Chapter 15 identity-and-authorization split (Risk 1).
- Decide the sprint-record naming convention (Risk 4); Sprint 03 used `SPRINT_03_*` to
  preserve Sprint 02's frozen records.
- Prior governance seams remain open (the README `Reading` exception and the `CHAPTER.md`
  convention are applied but not yet recorded as formal Architecture Decisions).
