# Documentation Conventions

The canonical documentation standard of the APEF, established by Architecture Board decision
OD-3 (Reference Studies milestone). It records the documentation conventions ratified in
practice across the framework so they are a single, auditable standard rather than scattered
decisions. It introduces no new architectural intent; it documents standing conventions.

This standard is governed by the [Architecture Charter](ARCHITECTURE_CHARTER.md) and is one of
the compliance references every milestone must satisfy.

## 1. The README contract

Every directory `README.md` follows the eight-section contract ratified in
[`../bootstrap/ARCHITECTURE_DECISIONS.md`](../bootstrap/ARCHITECTURE_DECISIONS.md) (AD-0001):
Overview · Purpose · Responsibilities · Contents · Out of Scope · Relationships · References ·
Conventions. Directory READMEs created in the Foundation are **frozen** and are never modified.

## 2. The navigation exception

A frozen chapter README may carry a single navigation-only `## Reading` section linking to the
chapter's content file. This is the only permitted addition to a frozen chapter README and does
not constitute an architectural change.

## 3. Chapter content convention

Handbook chapter content lives in `CHAPTER.md` within the chapter directory, following the
twelve-section chapter template in [`../handbook/WRITING_GUIDE.md`](../handbook/WRITING_GUIDE.md).
The directory `README.md` remains the frozen directory contract.

## 4. The Module Entry Pattern (canonical — OD-5)

Every framework module (a directory such as `handbook/`, `specifications/`, `reference/`,
`examples/`, and their areas) is entered through the following pattern:

- the directory `README.md` — the **frozen directory contract** (never modified); and
- one or more **entry documents** — the authoritative, editable entry point for the module's
  content (for example `SPECIFICATION_FRAMEWORK.md`, `*_SPECIFICATIONS.md`,
  `SPECIFICATION_LIBRARY_INDEX.md`, `REFERENCE_INDEX.md`, `STUDY.md`, `*_EXAMPLES.md`, and area
  index documents).

Frozen READMEs are never modified to add module content; the entry documents carry it. This is
the canonical structure for all framework modules.

## 5. Diagrams

Conceptual diagrams are authored as diagram-as-code (Mermaid) inside the documents that use
them; rendered binary exports, where needed, live in the module's `images/` area. Diagrams are
technology-neutral and consistent with the [Platform Capability Model](../handbook/PLATFORM_CAPABILITY_MODEL.md).

## 6. Neutrality and placeholders

- Framework documentation is technology-, cloud-, provider-, framework-, and language-neutral.
  **Reference** material may cite external technologies for comparative and educational purposes
  only; **examples** shall never depend on any vendor-specific technology, product, framework,
  SDK, or implementation detail.
- No document is merged with `TODO`, `TBD`, or `Coming Soon`; every document is useful on merge.

## 7. Terminology

Documentation uses the canonical terminology of the
[Glossary Guidelines](../handbook/GLOSSARY_GUIDELINES.md); every concept references its owning
chapter and is never redefined outside it.
