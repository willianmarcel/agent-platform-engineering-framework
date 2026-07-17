# ADR Traceability Matrix

This matrix records every ratified architectural decision APEF contains — its origin, its category,
the areas it affects, and how it is treated under the [Migration Plan](ADR_MIGRATION_PLAN.md). It
makes the decision log complete and auditable before any `ADR-` record is authored, and it is the
map maintained thereafter. No decision text is reproduced here; each row links to the authoritative
source.

## Legend

- **Category** — one of the [decision categories](decision-categories/CATEGORIES.md) (C1–C6).
- **Treatment** — *In place* (remains in its immutable/standard home), *Seed ADR* (a formal ADR is
  authored on approval, referencing the source), *Deferred*, or *Process* (governed elsewhere, not
  an ADR).

## Foundation Architecture Decisions (immutable — retained in place)

Source: [`../bootstrap/ARCHITECTURE_DECISIONS.md`](../bootstrap/ARCHITECTURE_DECISIONS.md). Status
as recorded there; not re-authored as ADRs.

| Decision | Subject | Category | Status (register) | Treatment |
|----------|---------|----------|-------------------|-----------|
| AD-0001 | README eight-section contract | C1 | Approved | In place |
| AD-0002 | Relative-link cross-references | C1 | Approved | In place |
| AD-0003 | Canonical documentation vocabulary | C1 | Approved | In place |
| AD-0004 | Line-wrapping standard | C1 | Postponed | In place (postponed) |
| AD-0005 | Roadmap ownership (bootstrap authoritative) | C6 | Approved (mod.) | In place |
| AD-0006 | Repeated directory names retained | C1 | Rejected | In place |
| AD-0007 | `architecture-requirements` rename | C1 | Approved | In place |
| AD-0008 | Removal of generic `diagrams/` | C1 | Approved | In place |
| AD-0009 | Docs derived from Handbook | C1 | Approved | In place |
| AD-0010 | C4 scope bounded to four views | C3 | Approved | In place |
| AD-0011 | Event Storming placement | C3 | Rejected | In place |
| AD-0012 | Template base/extension hierarchy | C2 | Approved | In place |
| AD-0013 | Planning-trio adjacency | C2 | No action | In place |
| AD-0014 | Examples contain no executable code | C2 | Approved | In place |
| AD-0015 | Scripts are maintenance-only | C2 | Approved | In place |
| AD-0016 | adrs README typo correction | C1 | Approved | In place |
| AD-0017 | Replace placeholder URLs | C1 | Approved (dep. open) | In place |
| AD-0018 | Link MASTER_PLAN reference | C1 | Approved | In place |
| AD-0019 | NOTICE / copyright file | C6 | Postponed | In place (postponed) |
| AD-0020 | Add `.gitignore` | C1 | Approved | In place |
| AD-0021 | Mandatory Conventions section | C1 | Approved (subsumed) | In place |

## Board Outstanding Decisions

Sources: the milestone assessments in [`../docs/`](../docs/) and the
[Documentation Conventions](../governance/DOCUMENTATION_CONVENTIONS.md).

| Decision | Subject | Category | Affected areas | Treatment | Proposed ADR |
|----------|---------|----------|----------------|-----------|--------------|
| OD-1 | Creator Experience owned by Chapter 08 | C5 | [Ch 08](../handbook/08-builder-platform/), [Ch 17](../handbook/17-ui-ux/) | Seed ADR | ADR-0002 |
| OD-2 | Chapter 17 titled "User Experience" | C1 | [Ch 17](../handbook/17-ui-ux/), Handbook TOC | Seed ADR | ADR-0003 |
| OD-3 | Documentation conventions ratified as a standard | C6 | [Documentation Conventions](../governance/DOCUMENTATION_CONVENTIONS.md) | In place (standard) | — |
| OD-4 | Single home for mandated architectural principles | C6 | Handbook (per-chapter restatement) | Deferred (Release 1.1) | future |
| OD-5 | Module Entry Pattern | C1 | All modules with frozen READMEs | Seed ADR | ADR-0004 |
| OD-6 | Commits deferred until Publication Readiness approval | — | Repository (version control) | Process (Version Control Policy) | — |

## Board-initiated topology and version-control decisions

Source: [`../docs/PUBLICATION_READINESS.md`](../docs/PUBLICATION_READINESS.md) and
[`../docs/FINAL_ARCHITECTURE_REVIEW.md`](../docs/FINAL_ARCHITECTURE_REVIEW.md).

| Decision | Subject | Category | Affected areas | Treatment | Proposed ADR |
|----------|---------|----------|----------------|-----------|--------------|
| Governance module | Establish `governance/` as a top-level module | C1 | [`governance/`](../governance/), repository topology | Seed ADR | ADR-0005 |
| Version Control Policy | Commit/tag timing; one milestone → one commit | C6 | [Version Control Policy](../governance/VERSION_CONTROL_POLICY.md), all commits | Seed ADR | ADR-0006 |

## The ADR framework's own adoption

| Decision | Subject | Category | Affected areas | Treatment | Proposed ADR |
|----------|---------|----------|----------------|-----------|--------------|
| Adopt ADR framework | Govern significant decisions through ADRs from EC-1 forward | C6 | [`adrs/`](.), the Workflow, the Quality Gates | Seed ADR | ADR-0001 |

## Completeness statement

Every ratified architectural decision known to the framework at EC-1 appears in this matrix: the 21
Foundation ADs, the 6 Board ODs, and the 2 Board-initiated topology/version-control decisions, plus
the ADR framework's own adoption. Six are proposed as seed ADRs; the 21 Foundation ADs and OD-3
remain authoritative in place; OD-4 is deferred; OD-6 is a process gate. No decision is left
unaccounted for, and none is rewritten by this milestone.

## Relationships

- Built from the [Migration Plan](ADR_MIGRATION_PLAN.md); classified by the
  [decision categories](decision-categories/CATEGORIES.md).
- References the immutable Foundation
  [Architecture Decisions](../bootstrap/ARCHITECTURE_DECISIONS.md) and the milestone assessments in
  [`../docs/`](../docs/).
- Maintained per [ADR Governance](ADR_GOVERNANCE.md) as ADRs are authored.
