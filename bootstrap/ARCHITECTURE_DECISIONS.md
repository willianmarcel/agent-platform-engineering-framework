# APEF Foundation — Architecture Decisions

- **Status:** Ratified — Immutable
- **Version:** 1.1.0
- **Date:** 2026-07-16
- **Authority:** Architecture Board
- **Supersedes:** All prior Foundation assumptions and defaults
- **Amendments applied:** Board Amendment 1 (References section in the README
  Contract), Board Amendment 2 (immutability by supersession), Board Amendment 3
  (permanent AD identifiers and the eight-field decision format).

## Preamble

This document is the authoritative, immutable record of the Architecture Board's
rulings for the Foundation phase of the Agent Platform Engineering Framework (APEF).
It is governed by [`MASTER_PLAN.md`](MASTER_PLAN.md) and, together with it, forms the
constitution for Foundation.

Every ruling is registered as a numbered **Architecture Decision (AD)** with a
permanent identifier. An AD is never edited once ratified; it is only ever superseded
by a later AD (see [§8](#8-immutability--amendment-process)). Where an AD changes the
repository, it records what the change is and what it implies for implementation — but
**no change is applied by this document**. Implementation is a separate, subsequently
approved step.

---

## 1. Global Foundation Standards

These standards apply repository-wide and take precedence over any local convention.
They are the normative expression of AD-0001, AD-0002, and AD-0003.

### 1.1 The README Contract

Every `README.md` in the repository — root, section, and leaf alike — MUST use exactly
the following eight sections, in this order. No alternative README structure is
permitted.

1. **Overview** — one paragraph stating what this directory is.
2. **Purpose** — why the directory exists and the value it provides.
3. **Responsibilities** — what the directory is accountable for.
4. **Contents** — what belongs here.
5. **Out of Scope** — what must never be placed here.
6. **Relationships** — how this directory relates to others, expressed as links.
7. **References** — external or cross-repository sources relevant to the directory.
8. **Conventions** — local rules that govern artifacts in this directory.

A section with no content in the Foundation phase is still written with a useful,
non-placeholder statement (for example, a directory with no external references states
that none apply, and a directory with no local rules states the applicable global
convention). The no-placeholder rule from [`MASTER_PLAN.md`](MASTER_PLAN.md) remains in
force.

### 1.2 Documentation Vocabulary

All documentation adopts a single heading vocabulary. Where a heading applies, its
canonical name MUST be used:

`Overview` · `Purpose` · `Responsibilities` · `Contents` · `Out of Scope` ·
`Relationships` · `References` · `Conventions`

The README Contract (§1.1) is the complete, ordered application of this vocabulary;
READMEs and the vocabulary are now fully aligned. Non-README documents use the same
canonical headings where they apply. Any section beyond this vocabulary is permitted
**only when strictly necessary** and is the documented exception, not the rule.

### 1.3 Cross-References

Every reference to another file or directory in the repository MUST be a relative
Markdown link. Plain-text path references are prohibited in all documents. This closes
the gap where unlinked references escaped link validation.

---

## 2. Architecture Decision Register

Every finding from the Foundation review is registered below as a permanently
identified Architecture Decision. Identifiers are never reused and never renumbered.

| AD | Finding | Ruling |
|----|---------|--------|
| [AD-0001](#ad-0001--readme-contract) | A1 — Two README templates | Approved (modified) |
| [AD-0002](#ad-0002--cross-references) | A2 — Plain-text cross-references | Approved |
| [AD-0003](#ad-0003--documentation-vocabulary) | A3 — Multiple vocabularies | Approved |
| [AD-0004](#ad-0004--line-wrapping) | A4 — Line wrapping | Postponed |
| [AD-0005](#ad-0005--roadmap-ownership) | A5 — Roadmap ownership | Approved (modified) |
| [AD-0006](#ad-0006--repeated-directory-names) | B1 — Repeated directory names | Rejected |
| [AD-0007](#ad-0007--architecture-requirements-rename) | B2 — Architecture naming | Approved |
| [AD-0008](#ad-0008--removal-of-the-generic-diagrams-directory) | B3 — Generic diagrams folder | Approved |
| [AD-0009](#ad-0009--docs-derived-from-handbook) | C1 — Docs vs Handbook | Approved |
| [AD-0010](#ad-0010--c4-scope) | C2 — C4 scope | Approved |
| [AD-0011](#ad-0011--event-storming-placement) | C3 — Event Storming placement | Rejected |
| [AD-0012](#ad-0012--template-hierarchy) | C4 — Template hierarchy | Approved |
| [AD-0013](#ad-0013--planning-trio-adjacency) | C5 — Planning-trio adjacency | No action |
| [AD-0014](#ad-0014--examples-contain-no-executable-code) | D1 — Examples form | Approved |
| [AD-0015](#ad-0015--scripts-are-maintenance-only) | D2 — Scripts scope | Approved |
| [AD-0016](#ad-0016--adrs-readme-typo) | E1 — Typo | Approved |
| [AD-0017](#ad-0017--replace-placeholder-urls) | E2 — Placeholder URL | Approved (dependency open) |
| [AD-0018](#ad-0018--link-master_plan-reference) | E3 — Unlinked reference | Approved |
| [AD-0019](#ad-0019--notice--copyright-file) | E4 — NOTICE / copyright | Postponed |
| [AD-0020](#ad-0020--add-gitignore) | E5 — Missing `.gitignore` | Approved |
| [AD-0021](#ad-0021--mandatory-conventions-section) | E6 — Uneven Conventions | Approved |

Each decision below carries the eight mandated fields: **Decision, Status, Context,
Rationale, Consequences, Affected Directories, Migration Required, Superseded By**.

---

### AD-0001 — README Contract

- **Decision:** A single README structure is used throughout the repository: the
  eight-section contract defined in [§1.1](#11-the-readme-contract). No alternative
  README structure is permitted.
- **Status:** Approved (modified).
- **Context:** Two README templates were in use; leaf READMEs dropped the mandated
  "Responsibilities" section, producing two conflicting shapes.
- **Rationale:** One contract removes the split, restores every mandated section to
  every README, and makes READMEs mechanically checkable.
- **Consequences:** All READMEs are rewritten to the eight-section contract; a linter
  can enforce section presence and order.
- **Affected Directories:** All directories containing a `README.md` (repository-wide).
- **Migration Required:** Yes — rewrite every README; map "What belongs here" →
  `Contents`, "What should never be placed here" → `Out of Scope`; add `Overview`,
  `Responsibilities` (where missing), `Relationships`, `References`, `Conventions`.
- **Superseded By:** —

### AD-0002 — Cross-References

- **Decision:** Every reference to another repository file or directory is a relative
  Markdown link; plain-text path references are prohibited ([§1.3](#13-cross-references)).
- **Status:** Approved.
- **Context:** Leaf READMEs used bare, unlinked paths that were both inconsistent and
  invisible to link validation.
- **Rationale:** Navigability and enforceable, repository-wide link checking.
- **Consequences:** All documents are updated; the link checker covers every reference.
- **Affected Directories:** Repository-wide.
- **Migration Required:** Yes — convert all plain-text paths to relative links.
- **Superseded By:** —

### AD-0003 — Documentation Vocabulary

- **Decision:** All documentation adopts the single canonical heading vocabulary in
  [§1.2](#12-documentation-vocabulary). Sections beyond it are permitted only when
  strictly necessary.
- **Status:** Approved.
- **Context:** Three different heading vocabularies were in use across the repository.
- **Rationale:** A shared vocabulary makes documents comparable and lintable.
- **Consequences:** Documents align to the canonical headings; the README contract and
  the vocabulary are fully reconciled.
- **Affected Directories:** All documentation, repository-wide.
- **Migration Required:** Yes — align headings to the canonical vocabulary.
- **Superseded By:** —

### AD-0004 — Line Wrapping

- **Decision:** No line-wrapping standard is imposed by Foundation; the question is
  deferred to the Engineering phase.
- **Status:** Postponed.
- **Context:** Parent documents were hard-wrapped; leaves used single long lines.
- **Rationale:** Cosmetic; not a Foundation blocker.
- **Consequences:** Mixed wrapping persists until the Engineering phase rules on it.
- **Affected Directories:** None (Foundation).
- **Migration Required:** No.
- **Superseded By:** —

### AD-0005 — Roadmap Ownership

- **Decision:** [`ROADMAP.md`](ROADMAP.md) (bootstrap) is the single authoritative
  roadmap and holds all phase content. The repository-root roadmap becomes a
  navigation document that links to it and holds no duplicated phase content.
- **Status:** Approved (modified).
- **Context:** The root roadmap carried the phase content while the bootstrap roadmap,
  declared authoritative, was only a stub — an ownership inversion inviting drift.
- **Rationale:** One owner eliminates drift; the authoritative document must carry the
  authoritative content.
- **Consequences:** Phase content lives in one place; the root roadmap is a pointer.
- **Affected Directories:** [`bootstrap/`](.) (`ROADMAP.md`) and the repository root
  (`ROADMAP.md`).
- **Migration Required:** Yes — move authoritative phase content into the bootstrap
  roadmap; reduce the root roadmap to navigation.
- **Superseded By:** —

### AD-0006 — Repeated Directory Names

- **Decision:** Repeated directory names (for example `runtime`, `roadmap`,
  `architecture`) are retained; they are intentionally contextual.
- **Status:** Rejected (no change).
- **Context:** The same leaf name recurs under different parents.
- **Rationale:** The parent path supplies meaning and the `Relationships` section
  disambiguates; renaming would add noise without adding clarity.
- **Consequences:** Naming stays as-is; disambiguation is the READMEs' responsibility.
- **Affected Directories:** None.
- **Migration Required:** No.
- **Superseded By:** —

### AD-0007 — architecture-requirements Rename

- **Decision:** `specifications/architecture/` is renamed to
  `specifications/architecture-requirements/`.
- **Status:** Approved.
- **Context:** `specifications/architecture/` (normative requirements) collided with
  the top-level `architecture/` (structural models) — the sharpest naming ambiguity in
  the repository.
- **Rationale:** Distinct names make misfiling unlikely and clarify the requirements
  vs models distinction.
- **Consequences:** One directory is renamed; inbound references are repointed.
- **Affected Directories:** [`specifications/`](../specifications/) (the renamed
  subdirectory) and every document that references it, including
  [`specifications/README.md`](../specifications/README.md).
- **Migration Required:** Yes — rename the directory and update all inbound links.
- **Superseded By:** —

### AD-0008 — Removal of the Generic Diagrams Directory

- **Decision:** `architecture/diagrams/` is removed. Every architectural artifact must
  belong to a well-defined category (`c4`, `deployment`, `network`, `runtime`,
  `sequences`, `state-machines`, `event-storming`, `integrations`).
- **Status:** Approved.
- **Context:** A generic catch-all beside categorized diagram directories invited
  ambiguous placement and taxonomy erosion.
- **Rationale:** A precise taxonomy with no catch-all keeps every artifact classifiable.
- **Consequences:** The directory count decreases by one; ambiguous diagrams no longer
  have a home and must be categorized.
- **Affected Directories:** [`architecture/`](../architecture/) (removed
  subdirectory), and references in [`assets/README.md`](../assets/README.md) and
  [`architecture/README.md`](../architecture/README.md).
- **Migration Required:** Yes — remove the directory and repoint its inbound references.
- **Superseded By:** —

### AD-0009 — Docs Derived From Handbook

- **Decision:** The [`handbook/`](../handbook/) is the single source of truth and is
  the edited artifact. [`docs/`](../docs/) contains documentation rendered or curated
  **from** the Handbook; it is generated output, not an authoring surface.
- **Status:** Approved.
- **Context:** The Docs/Handbook boundary was the softest in the repository; it never
  stated how Handbook content becomes Docs.
- **Rationale:** A clear producer/consumer relationship removes the ambiguity.
- **Consequences:** Authors edit the Handbook; Docs is derived and never the origin of
  truth.
- **Affected Directories:** [`handbook/`](../handbook/) and [`docs/`](../docs/).
- **Migration Required:** Yes (documentation) — state the relationship in both
  directories' READMEs.
- **Superseded By:** —

### AD-0010 — C4 Scope

- **Decision:** [`architecture/c4/`](../architecture/c4/) contains only the Context,
  Container, Component, and Code views. Deployment, Network, Sequence, and State
  diagrams remain in their dedicated directories.
- **Status:** Approved.
- **Context:** The C4 model natively includes deployment and dynamic views, overlapping
  the dedicated sibling directories.
- **Rationale:** A bounded C4 scope prevents overlap with the dedicated view
  directories.
- **Consequences:** Contributors have one unambiguous home per view type.
- **Affected Directories:** [`architecture/c4/`](../architecture/c4/).
- **Migration Required:** Yes (documentation) — state the scope in the `c4` README.
- **Superseded By:** —

### AD-0011 — Event Storming Placement

- **Decision:** [`architecture/event-storming/`](../architecture/event-storming/)
  remains under Architecture. Its outputs may influence the Domain Model, but the
  activity belongs to Architecture.
- **Status:** Rejected (no change).
- **Context:** Event Storming is a domain-modeling activity whose outputs feed
  `specifications/domains`, raising a placement question.
- **Rationale:** Placement follows the activity's owner, not its downstream consumers.
- **Consequences:** Event Storming stays in Architecture; its influence on the Domain
  Model is documented via `Relationships`.
- **Affected Directories:** None.
- **Migration Required:** No.
- **Superseded By:** —

### AD-0012 — Template Hierarchy

- **Decision:** The generic [`templates/specification/`](../templates/specification/)
  template is the base template. Specialized templates (`runtime`, `provider`,
  `plugin`, `api`, and others as applicable) extend it. The inheritance relationship is
  to be fully documented in a later phase.
- **Status:** Approved.
- **Context:** It was ambiguous whether a specialized specification is authored from
  the base template or a specialized one.
- **Rationale:** A base-plus-extension model removes the ambiguity and reduces
  duplication across templates.
- **Consequences:** Specialized templates declare their base; a later phase documents
  the inheritance in full.
- **Affected Directories:** [`templates/`](../templates/) and its subdirectories.
- **Migration Required:** Partial — note the base/extension relationship now; document
  the full inheritance later.
- **Superseded By:** —

### AD-0013 — Planning-Trio Adjacency

- **Decision:** No change to `specifications/roadmap`, `specifications/releases`, and
  `specifications/backlog`.
- **Status:** No action.
- **Context:** The three planning directories have defensible but adjacent boundaries.
- **Rationale:** The boundaries are acceptable; no ambiguity requires resolution now.
- **Consequences:** The trio remains as-is; drift is watched, not pre-empted.
- **Affected Directories:** None.
- **Migration Required:** No.
- **Superseded By:** —

### AD-0014 — Examples Contain No Executable Code

- **Decision:** Examples MUST never contain production or executable application code.
  Examples MAY contain specifications, DSL, JSON, YAML, architecture, diagrams,
  configuration, and decision trees.
- **Status:** Approved.
- **Context:** The example READMEs forbade only "production/deployable" code, which
  conflicted with the framework-wide no-code rule.
- **Rationale:** Preserves the no-code rule while keeping examples concrete and useful.
- **Consequences:** Example authors express examples as artifacts and models, never as
  runnable code.
- **Affected Directories:** [`examples/`](../examples/) and its subdirectories.
- **Migration Required:** Yes (documentation) — state the permitted forms and the code
  prohibition in the example READMEs.
- **Superseded By:** —

### AD-0015 — Scripts Are Maintenance-Only

- **Decision:** [`scripts/`](../scripts/) holds repository-maintenance utilities only
  (validation, generation, linting). Scripts are never platform implementation.
- **Status:** Approved.
- **Context:** `scripts/` sits close to the no-code rule and needed an explicit
  carve-out.
- **Rationale:** A bounded carve-out keeps maintenance automation legitimate without
  admitting platform code.
- **Consequences:** Scripts are scoped to maintaining this repository; no platform code
  is admitted.
- **Affected Directories:** [`scripts/`](../scripts/).
- **Migration Required:** No (the current README already scopes this; the Engineering
  Guide will restate the carve-out).
- **Superseded By:** —

### AD-0016 — adrs README Typo

- **Decision:** In [`adrs/README.md`](../adrs/README.md), "diagrams sources" is
  corrected to "diagram sources".
- **Status:** Approved.
- **Context:** A typographical error in the ADR directory README.
- **Rationale:** Correctness.
- **Consequences:** The text is corrected.
- **Affected Directories:** [`adrs/`](../adrs/).
- **Migration Required:** Yes — apply the correction.
- **Superseded By:** —

### AD-0017 — Replace Placeholder URLs

- **Decision:** Placeholder URLs (for example the `example.com` link in
  [`CHANGELOG.md`](../CHANGELOG.md)) are replaced with the actual repository URL.
- **Status:** Approved (dependency open — accepted by the Board).
- **Context:** The repository has no configured remote, so no canonical URL exists yet.
- **Rationale:** Real links must not carry placeholder hosts.
- **Consequences:** The replacement is applied once the repository URL is available; the
  open dependency is recorded in [§5](#5-open-inputs).
- **Affected Directories:** Repository root ([`CHANGELOG.md`](../CHANGELOG.md)).
- **Migration Required:** Yes — pending the repository URL.
- **Superseded By:** —

### AD-0018 — Link MASTER_PLAN Reference

- **Decision:** The plain-text `MASTER_PLAN.md` mention in the root
  [`README.md`](../README.md) becomes a relative link, consistent with AD-0002.
- **Status:** Approved.
- **Context:** An unlinked reference inconsistent with the cross-reference rule.
- **Rationale:** Consistency with AD-0002.
- **Consequences:** The reference is clickable.
- **Affected Directories:** Repository root ([`README.md`](../README.md)).
- **Migration Required:** Yes — convert to a link.
- **Superseded By:** —

### AD-0019 — NOTICE / Copyright File

- **Decision:** A `NOTICE` file and explicit copyright line are deferred.
- **Status:** Postponed.
- **Context:** Apache-2.0 convention favors a NOTICE file; the copyright holder appears
  only in prose today.
- **Rationale:** Not a Foundation blocker.
- **Consequences:** Copyright remains in prose until a later phase adds a NOTICE.
- **Affected Directories:** None (Foundation).
- **Migration Required:** No.
- **Superseded By:** —

### AD-0020 — Add .gitignore

- **Decision:** A repository `.gitignore` is added to exclude OS and editor artifacts.
- **Status:** Approved.
- **Context:** No `.gitignore` exists; incidental OS/editor files could be committed.
- **Rationale:** Repository hygiene.
- **Consequences:** Incidental files are ignored by default.
- **Affected Directories:** Repository root.
- **Migration Required:** Yes — add the file.
- **Superseded By:** —

### AD-0021 — Mandatory Conventions Section

- **Decision:** The `Conventions` section is mandatory in every README, by virtue of
  the README Contract (AD-0001).
- **Status:** Approved (subsumed by AD-0001).
- **Context:** The "Conventions" section was present on some READMEs and absent on
  peers.
- **Rationale:** Uniform structure by construction.
- **Consequences:** Every README carries a `Conventions` section; uniformity is a
  side-effect of AD-0001 and requires no separate migration.
- **Affected Directories:** All directories containing a `README.md`.
- **Migration Required:** No (delivered by the AD-0001 rewrite).
- **Superseded By:** —

---

## 3. Definitive Foundation Directory Structure

The ratified Foundation structure after the approved rename (AD-0007) and removal
(AD-0008). It is the target the implementation step must realize; it is not yet
applied.

```
agent-platform-engineering-framework/
├── .claude/
│   ├── commands/
│   ├── personas/
│   ├── skills/
│   ├── hooks/
│   └── workflows/
├── bootstrap/
│   ├── README.md
│   ├── MASTER_PLAN.md
│   ├── ARCHITECTURE_DECISIONS.md   (this document)
│   ├── ROADMAP.md                  (authoritative — AD-0005)
│   ├── ENGINEERING_GUIDE.md
│   ├── REPOSITORY_GUIDE.md
│   ├── QUALITY_GATES.md
│   ├── RELEASE_PROCESS.md
│   └── WORKFLOW.md
├── handbook/                       (00–21; source of truth — AD-0009)
├── specifications/
│   ├── vision/
│   ├── discovery/
│   ├── domains/
│   ├── capabilities/
│   ├── runtime/
│   ├── architecture-requirements/  (renamed — AD-0007)
│   ├── security/
│   ├── observability/
│   ├── ui/
│   ├── roadmap/
│   ├── backlog/
│   └── releases/
├── architecture/
│   ├── c4/                         (Context/Container/Component/Code only — AD-0010)
│   ├── event-storming/             (remains here — AD-0011)
│   ├── deployment/
│   ├── runtime/
│   ├── network/
│   ├── integrations/
│   ├── state-machines/
│   └── sequences/                  (diagrams/ removed — AD-0008)
├── playbooks/
│   ├── architecture-review/
│   ├── security-review/
│   ├── performance-review/
│   ├── observability-review/
│   ├── production-readiness/
│   ├── release-review/
│   └── incident-review/
├── templates/                      (specification is base; others extend — AD-0012)
│   ├── adr/
│   ├── specification/
│   ├── epic/
│   ├── feature/
│   ├── story/
│   ├── task/
│   ├── runtime/
│   ├── plugin/
│   ├── provider/
│   ├── evaluation/
│   ├── api/
│   └── architecture/
├── examples/                       (no executable code — AD-0014)
│   ├── agents/
│   ├── workflows/
│   ├── providers/
│   ├── plugins/
│   ├── supervisors/
│   └── evaluations/
├── reference/
│   ├── langgraph/
│   ├── agno/
│   ├── openai-agents-sdk/
│   ├── google-adk/
│   ├── crewai/
│   ├── autogen/
│   ├── azure-ai-foundry/
│   ├── copilot-studio/
│   ├── dify/
│   └── flowise/
├── adrs/
├── docs/                           (derived from handbook — AD-0009)
├── assets/
├── scripts/                        (maintenance utilities only — AD-0015)
├── .gitignore                      (new — AD-0020)
├── README.md
├── LICENSE
├── CHANGELOG.md
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── SECURITY.md
└── ROADMAP.md                      (navigation only — AD-0005)
```

Directory count moves from 96 to **95** (removal of `architecture/diagrams/`; the
AD-0007 rename is net-zero). One new top-level file (`.gitignore`) and one new
bootstrap file (`ARCHITECTURE_DECISIONS.md`) are added.

---

## 4. Ownership & Boundary Rulings (summary)

- **Roadmap:** the bootstrap [`ROADMAP.md`](ROADMAP.md) owns all phase content; the
  root roadmap only navigates to it. (AD-0005)
- **Documentation:** the Handbook is authored; Docs is generated/curated from it.
  (AD-0009)
- **Architecture views:** C4 holds the four canonical C4 views only; every other view
  has a dedicated directory; no catch-all exists. (AD-0010, AD-0008)
- **Event Storming:** an Architecture activity that may inform, but does not belong to,
  the Domain Model. (AD-0011)
- **Templates:** Specification is the base template; specialized templates extend it.
  (AD-0012)
- **Examples:** artifacts and models only — never executable application code.
  (AD-0014)
- **Scripts:** repository maintenance only — never platform implementation. (AD-0015)

---

## 5. Open Inputs

Accepted by the Board as permissible open dependencies until the metadata is available:

- **Repository URL (AD-0017):** the canonical remote URL is required to replace the
  `example.com` placeholder in [`CHANGELOG.md`](../CHANGELOG.md). The repository
  currently has no configured remote. This dependency may remain open.

---

## 6. Postponed Items

Recorded for continuity; explicitly **not** part of Foundation:

- **AD-0004 — Line-wrapping standard** → Engineering phase.
- **AD-0019 — NOTICE / copyright file** → later phase.

---

## 7. Implementation Implications (deferred — not applied by this document)

The following work items realize the approved decisions. They are listed so the
subsequent, separately approved implementation step is unambiguous. None are performed
now.

1. **Rewrite all READMEs to the eight-section contract** (AD-0001), including the
   `References` section. Reference READMEs fold their "why studied" content into
   `Overview`/`Purpose` while still satisfying the master-plan requirement to explain
   why the technology is studied.
2. **Convert every plain-text path to a relative Markdown link** (AD-0002), repository
   wide.
3. **Align headings to the canonical vocabulary** (AD-0003).
4. **Restructure roadmaps** (AD-0005): move authoritative phase content into the
   bootstrap [`ROADMAP.md`](ROADMAP.md); reduce the root roadmap to navigation.
5. **Rename** `specifications/architecture/` → `specifications/architecture-requirements/`
   and update all inbound references (AD-0007).
6. **Remove** `architecture/diagrams/`; repoint references in
   [`assets/README.md`](../assets/README.md) and
   [`architecture/README.md`](../architecture/README.md) (AD-0008).
7. **State the Docs/Handbook producer–consumer relationship** in the `docs` and
   `handbook` READMEs (AD-0009).
8. **Constrain C4 scope** in the `c4` README to the four canonical views (AD-0010).
9. **State the examples policy** (AD-0014) in the example READMEs.
10. **Note the template base/extension relationship** in the template READMEs, to be
    fully documented later (AD-0012).
11. **Correct the typo** in [`adrs/README.md`](../adrs/README.md) (AD-0016); **link
    `MASTER_PLAN.md`** in the root README (AD-0018).
12. **Replace placeholder URLs** once the repository URL is provided (AD-0017).
13. **Add `.gitignore`** (AD-0020).
14. **Register this document** in the bootstrap [`README.md`](README.md) `Contents` and
    cross-link it from the root README — performed under the AD-0001/AD-0002 rewrite so
    the new file is not left unreferenced.

---

## 8. Immutability & Amendment Process

Upon ratification, this document and every Architecture Decision it contains are
**immutable**.

- **A decision is never edited.** Its text, once ratified, is permanent.
- **Change occurs only by supersession.** If a decision must change, a new Architecture
  Decision is authored with the next available identifier (AD-0022, AD-0023, …). The
  new AD states what it supersedes; the superseded AD's `Superseded By` field is set to
  point to it. No other field of the superseded AD is altered.
- **History is always preserved.** Superseded decisions remain in this register,
  visibly marked, so the full decision history is always available.
- **Identifiers are permanent.** AD identifiers are never reused and never renumbered.

A superseding Architecture Decision requires explicit Architecture Board ratification.
Where an ADR document is warranted in [`../adrs/`](../adrs/), it is authored from
[`../templates/adr/`](../templates/adr/) and linked from the superseding AD.
