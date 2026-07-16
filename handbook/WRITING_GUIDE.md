# Engineering Handbook — Writing Guide

This guide defines the writing standards every handbook chapter must follow. Its goal is
uniformity: every chapter uses the **same structure**, so readers always know where to
find each kind of information and reviewers can check chapters mechanically. This guide
defines the standard; it does not contain chapter content.

## Canonical Chapter Template

Every chapter is a single document that uses the following twelve **mandatory** sections,
in this order, plus one **optional** section (Security Considerations, see below). No
chapter may remove, reorder, or rename a mandatory section, and no section other than the
optional one may be added.

1. **Introduction** — Frame the chapter: what it covers, why it matters, and where it
   sits in the platform. State the prerequisites (with links) and the chapter's place in
   the reading order.
2. **Objectives** — What the reader will be able to understand or do after the chapter.
   Written as a short list of concrete outcomes.
3. **Concepts** — The vocabulary and mental models the chapter introduces. Concepts are
   defined here only if this chapter *owns* them (see the Knowledge Graph); otherwise
   link to the owning chapter.
4. **Principles** — The durable rules and values that govern this area, derived from
   [`03-engineering-principles`](03-engineering-principles/).
5. **Architecture** — How this area is structured, consistent with
   [`06-reference-architecture`](06-reference-architecture/). Diagrams are referenced
   from [`../architecture/`](../architecture/), not embedded as binaries.
6. **Patterns** — Recommended, reusable approaches, each with the context in which it
   applies and its trade-offs.
7. **Anti-patterns** — Approaches to avoid, each with why it fails and what to do
   instead. Every anti-pattern names its corresponding pattern.
8. **Best Practices** — Actionable guidance distilled from the principles and patterns.
   - **Security Considerations** *(optional; when present, placed here — immediately after
     Best Practices)* — Security is a cross-cutting concern. Any chapter may include this
     section to describe the **implementation implications** of its topic for security. It
     describes implications only; it never restates security **principles**, which are owned
     by [`15-security`](15-security/) and must be linked, not duplicated. Recommended for the
     platform-plane chapters; optional for the rest.
9. **Examples** — Illustrative, **non-executable** examples (specifications, DSL, JSON,
   YAML, diagrams, configuration, or decision trees), consistent with the
   [`../examples/`](../examples/) policy. No production or runnable application code.
10. **Checklist** — A short, verifiable list a reader uses to confirm they have applied
    the chapter correctly. Feeds the chapter's Definition of Done.
11. **References** — Links to the specifications, architecture, templates, reference
    studies, and other chapters this chapter relies on. All links are relative and must
    resolve.
12. **Summary** — A concise recap of the chapter's key points and a pointer to the
    logical next chapter.

## Chapter Directory Layout

Every chapter directory uses the following layout:

- `README.md` — the chapter landing page (the directory-contract README). It may include a
  **Reading** section that links to `CHAPTER.md`; that navigation link is the only
  permitted addition to a frozen chapter README.
- `CHAPTER.md` — the complete chapter content, following the canonical template above.
- `examples/` — the chapter's non-executable examples.
- `images/` — image assets specific to the chapter.
- `references/` — reference material specific to the chapter.

The layout is materialized for a chapter when that chapter is authored; `CHAPTER.md` is
never created empty.

## Concept Ownership

Every concept has exactly one owning chapter. Within the handbook:

- Other chapters **may** reference, introduce, or contextualize a concept.
- Other chapters **must never** redefine, fully explain, or duplicate a concept they do
  not own.

The owning chapter holds the authoritative definition; every other chapter links to it.
The ownership table is maintained in the [Knowledge Graph](KNOWLEDGE_GRAPH.md).

## General Writing Standards

- **Voice:** clear, direct, and instructional. Prefer short sentences and concrete
  language. Address the reader as an engineer.
- **One owner per concept:** define a concept only in its owning chapter; elsewhere,
  link. This is the primary defense against duplicated knowledge.
- **Links, not paths:** every reference to another artifact is a relative Markdown link.
- **Diagrams as code:** reference diagram sources in [`../architecture/`](../architecture/);
  do not paste binary images into chapters.
- **Terminology:** use only the canonical terms defined in the
  [Glossary Guidelines](GLOSSARY_GUIDELINES.md); never use a forbidden synonym.
- **No placeholders:** a chapter is never merged with `TODO`, `TBD`, or `Coming Soon`.
- **Normative vs explanatory:** the handbook explains and connects; it does not restate
  normative requirements that belong in [`../specifications/`](../specifications/).
  Link to the specification instead.

## Relationship to Other Standards

- Structure of the handbook and reading policy: [Master Index](HANDBOOK.md).
- Per-chapter contracts (objective, scope, prerequisites): [Table of Contents](TABLE_OF_CONTENTS.md).
- Dependencies and concept ownership: [Knowledge Graph](KNOWLEDGE_GRAPH.md).
- Terminology rules: [Glossary Guidelines](GLOSSARY_GUIDELINES.md).
- Definition of Done and gates: [Quality Criteria](QUALITY_CRITERIA.md).
