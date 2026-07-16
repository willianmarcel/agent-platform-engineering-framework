# Engineering Handbook — Glossary Guidelines

This document defines the language rules the handbook uses so that terminology is
consistent across every chapter. It governs how terms are named, capitalized, and
abbreviated, establishes canonical terms, and forbids synonyms that would fragment the
vocabulary.

**The Glossary owns no concepts.** The Glossary chapter ([`21-glossary`](21-glossary/))
standardizes *terminology* only: for each canonical term it gives a short gloss and a link
to the chapter that owns the concept. The authoritative *definition* of every concept
belongs to that owning chapter (see the ownership table in the
[Knowledge Graph](KNOWLEDGE_GRAPH.md)), never to the Glossary. This document governs how
terms are *used*.

## Terminology Rules

- **Single source of truth for terminology:** every domain term has one canonical form,
  standardized in [`21-glossary`](21-glossary/). The concept behind the term is defined in
  its owning chapter; the Glossary gives the term a short gloss and links to that owner.
- **Ubiquitous language:** terms follow the domain model established in
  [`05-domain-driven-design`](05-domain-driven-design/). The glossary and the domain
  model must agree.
- **Define on first use:** when a chapter first uses a specialized term, it links to the
  glossary entry.
- **One term, one meaning:** a term denotes exactly one concept across the whole
  handbook. If two concepts differ, they get two distinct terms.

## Naming Conventions

- **Concept names** are written in prose using their canonical form (for example, *AI
  Agent Platform*, *Control Plane*, *Provider*).
- **Directory and file names** follow the repository convention: lowercase
  kebab-case (for example, `provider-platform`).
- **Chapter references** use the form `NN — Title` linked to the chapter directory.

## Capitalization Rules

- **Proper APEF concepts** are capitalized when referring to the specific APEF construct:
  *Runtime Platform*, *Builder Platform*, *Provider Platform*, *Plugin Platform*,
  *Control Plane*, *Data Platform*, *API Platform*, *Reference Architecture*.
- **Generic use** is lowercase (for example, "the runtime executes the agent" uses the
  general sense; "the Runtime Platform chapter" names the construct).
- **Acronyms** are uppercase: *API*, *SDD*, *ADR*, *DDD*, *SLO*, *SLI*, *UI*, *UX*.
- Sentence case is used for headings; title case is reserved for proper concept names.

## Abbreviations

- Expand an abbreviation on first use in a chapter, followed by the abbreviation in
  parentheses — for example, "Architecture Decision Record (ADR)" — then use the
  abbreviation thereafter.
- Approved abbreviations: **APEF**, **SDD** (Specification-Driven Development),
  **ADR** (Architecture Decision Record), **DDD** (Domain-Driven Design),
  **SLO/SLI** (Service-Level Objective/Indicator), **CI/CD**, **UI/UX**, **API**.
- Do not invent new abbreviations without adding them to the glossary.

## Canonical Terms

Use these canonical terms consistently across the handbook:

| Canonical term | Refers to |
|----------------|-----------|
| AI Agent Platform | the system APEF guides teams to build |
| Agent | an autonomous unit that performs work within the platform |
| Workflow | a coordinated composition of agents, tools, and steps |
| Supervisor | an agent that coordinates and governs other agents |
| Provider | an integrated external model or service behind the provider abstraction |
| Plugin | a unit of extension conforming to the plugin contract |
| Runtime | the execution environment for agents and workflows |
| Control Plane | the governance, configuration, and administration layer |
| Reference Architecture | the canonical structural model in Chapter 06 |
| Specification | a normative SDD artifact under `specifications/` |

## Forbidden Synonyms

Do not use these synonyms; use the canonical term instead:

| Forbidden | Use instead |
|-----------|-------------|
| bot, assistant (as the unit of work) | Agent |
| pipeline, chain (for the coordinated composition) | Workflow |
| vendor, connector, model backend | Provider |
| extension, add-on, module (for extensibility units) | Plugin |
| engine, executor (for the execution environment) | Runtime |
| admin plane, management plane | Control Plane |
| blueprint, base design | Reference Architecture |
| spec sheet, requirement doc (for SDD artifacts) | Specification |

## Relationship to Other Standards

- Where terms are defined: [`21-glossary`](21-glossary/).
- Where the domain model is established: [`05-domain-driven-design`](05-domain-driven-design/).
- How terms are applied in writing: [Writing Guide](WRITING_GUIDE.md).
- How terminology compliance is checked: [Quality Criteria](QUALITY_CRITERIA.md).
