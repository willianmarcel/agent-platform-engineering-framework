# Chapter 21 — Glossary

## Introduction

This chapter is the Handbook's glossary: the canonical vocabulary shared across every
chapter. It has **no prerequisites** and is a reference to be consulted at any point. It
standardizes *terminology* — the words the Handbook uses and how they are used — and it owns
**no engineering concepts**: the meaning of every concept belongs to its owning chapter, and
this chapter points to that owner.

This chapter defines terminology standards and provides canonical terms and acronyms. It does
not define engineering concepts, prescribe technology, or contain implementation. The full,
per-concept index of the Handbook — every concept, its owner, and its referencing chapters —
is maintained in [`../HANDBOOK_INDEX.md`](../HANDBOOK_INDEX.md).

## Objectives

After reading this chapter, a reader will be able to:

- Explain what the glossary standardizes and what it deliberately does not own.
- Apply the Handbook's naming standards and acronym conventions.
- Use canonical terms consistently and avoid forbidden synonyms.
- Find the owning chapter for any concept.

## Concepts

This chapter **owns** the terminology-management concepts below. It owns no engineering
concepts; each engineering term points to its owning chapter.

**Canonical Terminology.** The single, agreed set of terms the Handbook uses, each with one
meaning. Canonical terminology is what keeps the whole Handbook speaking one language; the
practice that produces it is the ubiquitous-language discipline owned by
[Chapter 05](../05-domain-driven-design/CHAPTER.md).

**Definitions.** The short glosses this chapter provides for canonical terms, each paired with
a pointer to the chapter that owns and fully defines the concept. A glossary definition
locates and summarizes a term; it never replaces the authoritative definition in the owning
chapter.

**Vocabulary.** The whole body of terms the Handbook employs, standardized so that the same
word means the same thing everywhere it appears. Vocabulary is the scope over which canonical
terminology applies.

**Acronyms.** The abbreviations the Handbook uses, each expanded on first use and standardized
here. Acronyms are part of the vocabulary and follow the same one-meaning rule.

**Naming Standards.** The rules by which terms, concepts, and artifacts are named across the
Handbook — casing, form, and consistency — so that names are predictable and unambiguous.
Naming standards are the conventions the [Glossary Guidelines](../GLOSSARY_GUIDELINES.md)
codify and this chapter applies.

## Principles

- **One term, one meaning.** Every canonical term denotes exactly one concept across the whole
  Handbook.
- **Own terminology, not concepts.** Standardize words here; leave the meaning of each concept
  to its owning chapter.
- **Point to the owner.** Pair every term with the chapter that owns and defines it.
- **Name consistently.** Apply the naming standards so terms are predictable and unambiguous.
- **Uphold the platform's architectural principles.** As a part of the Handbook, the glossary
  is consistent with the [Platform Capability Model](../PLATFORM_CAPABILITY_MODEL.md) and the
  principles owned by [Chapter 03](../03-engineering-principles/CHAPTER.md), remaining
  vendor-neutral and technology-neutral.

## Architecture

This section describes the structure of the *glossary*, within the
[Platform Capability Model](../PLATFORM_CAPABILITY_MODEL.md) and consistent with the reference
architecture owned by [Chapter 06](../06-reference-architecture/CHAPTER.md).

The glossary is organized as terminology over owned meaning:

1. **Canonical terminology** and **vocabulary** establish the shared words; **acronyms** and
   **naming standards** govern their form.
2. **Definitions** provide a short gloss and a pointer to the owning chapter for each term.
3. The complete per-concept mapping — concept, owner, referencing chapters — is maintained in
   [`../HANDBOOK_INDEX.md`](../HANDBOOK_INDEX.md), which the glossary complements.

The glossary standardizes the language produced by the ubiquitous-language discipline owned by
[Chapter 05](../05-domain-driven-design/CHAPTER.md); the two agree by construction.

## Patterns

- **Term with owner.** *Context:* introducing any term. Pair it with a short gloss and a link
  to the chapter that owns it.
- **Expand on first use.** *Context:* using an acronym. Expand it on first use, then use the
  acronym consistently.
- **Canonical over synonym.** *Context:* choosing a word. Use the canonical term and avoid its
  forbidden synonyms.

## Anti-patterns

- **Redefining in the glossary.** *Why it fails:* a full definition here competes with the
  owning chapter and diverges. *Instead:* own terminology, not concepts.
- **Term without owner.** *Why it fails:* a term with no owner cannot be authoritative.
  *Instead:* point to the owner.
- **Synonym drift.** *Why it fails:* multiple words for one concept fragment the vocabulary.
  *Instead:* use canonical over synonym.

## Best Practices

- Standardize terms here and delegate their meaning to the owning chapter.
- Provide a short gloss and an owner link for each canonical term.
- Expand acronyms on first use and apply the naming standards consistently.
- Consult [`../HANDBOOK_INDEX.md`](../HANDBOOK_INDEX.md) for the complete per-concept mapping.
- Follow the [Glossary Guidelines](../GLOSSARY_GUIDELINES.md) for terminology and naming rules.

## Examples

The following are illustrative reference tables; the authoritative definition of each concept
lives in its owning chapter.

**Selected canonical terms and their owning chapters:**

| Canonical term | Owning chapter |
|----------------|----------------|
| AI Agent Platform | [01 Platform Vision](../01-platform-vision/CHAPTER.md) |
| Product Capability | [02 Product Thinking](../02-product-thinking/CHAPTER.md) |
| Engineering Principle | [03 Engineering Principles](../03-engineering-principles/CHAPTER.md) |
| Specification-Driven Development | [04 Development Methodology](../04-development-methodology/CHAPTER.md) |
| Bounded Context | [05 Domain-Driven Design](../05-domain-driven-design/CHAPTER.md) |
| Reference Architecture | [06 Reference Architecture](../06-reference-architecture/CHAPTER.md) |
| Runtime | [07 Runtime Platform](../07-runtime-platform/CHAPTER.md) |
| Provider Abstraction | [09 Provider Platform](../09-provider-platform/CHAPTER.md) |
| Plugin | [10 Plugin Platform](../10-plugin-platform/CHAPTER.md) |
| Control Plane | [11 Control Plane](../11-control-plane/CHAPTER.md) |
| Platform Data | [12 Data Platform](../12-data-platform/CHAPTER.md) |
| Observability | [14 Observability](../14-observability/CHAPTER.md) |
| Security Principle | [15 Security](../15-security/CHAPTER.md) |
| AI Evaluation | [16 Evaluation](../16-evaluation/CHAPTER.md) |

**Selected acronyms:**

| Acronym | Expansion |
|---------|-----------|
| APEF | Agent Platform Engineering Framework |
| PCM | [Platform Capability Model](../PLATFORM_CAPABILITY_MODEL.md) |
| SDD | Specification-Driven Development ([04](../04-development-methodology/CHAPTER.md)) |
| DDD | Domain-Driven Design ([05](../05-domain-driven-design/CHAPTER.md)) |
| ADR | Architecture Decision Record ([04](../04-development-methodology/CHAPTER.md)) |
| SLO | Service-Level Objective ([14](../14-observability/CHAPTER.md)) |

## Checklist

A reader has finished the Handbook's chapters when they can confirm:

- [ ] I understand the glossary standardizes terminology and owns no engineering concepts.
- [ ] I can apply the naming standards and acronym conventions.
- [ ] I use canonical terms and avoid forbidden synonyms.
- [ ] I can find any concept's owning chapter, via this glossary or the Handbook Index.

## References

- [Chapter 05 — Domain-Driven Design](../05-domain-driven-design/CHAPTER.md) — owns the
  ubiquitous-language discipline the glossary standardizes.
- [Glossary Guidelines](../GLOSSARY_GUIDELINES.md) — the terminology and naming rules this
  chapter applies.
- [Handbook Index](../HANDBOOK_INDEX.md) — the complete per-concept mapping.
- [Platform Capability Model](../PLATFORM_CAPABILITY_MODEL.md) — the canonical model the
  vocabulary describes.

## Summary

The glossary is the Handbook's shared vocabulary. It standardizes canonical terminology,
vocabulary, acronyms, and naming standards, and provides short definitions that point to the
chapter owning each concept — for the glossary owns terminology, never engineering concepts.
With the vocabulary consolidated and every concept traceable to its owner, the Handbook's
twenty-two chapters form one complete, internally consistent engineering framework.
