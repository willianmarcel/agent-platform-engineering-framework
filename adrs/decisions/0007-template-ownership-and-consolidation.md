# ADR-0007 — Template ownership and consolidation

- **Status:** Accepted — see [ADR Lifecycle](../ADR_LIFECYCLE.md)
- **Date:** 2026-07-17
- **Category:** C1 Structural & Documentation
- **Authority:** Architecture Board
- **Supersedes:** —
- **Superseded By:** —

## Decision
Every template type has exactly one owning home (one-template-one-home). The base specification
template lives at [`templates/specification/`](../../templates/specification/specification-template.md);
specialized specification templates are owned by the Specification Library and extend the base; the
ADR template is owned by the ADR framework ([`adrs/ADR_TEMPLATE.md`](../ADR_TEMPLATE.md)); and the
work-item templates (epic, feature, story, task) are owned by the top-level `templates/` module. The
full ownership map and base-and-extension inheritance are documented in
[`templates/TEMPLATE_OWNERSHIP.md`](../../templates/TEMPLATE_OWNERSHIP.md).

## Context
Templates existed in three places with overlapping responsibilities: the top-level `templates/`
subdirectories were contract-README stubs with no forms; the Specification Library had already
delivered working specification forms (`specifications/templates/` and per-area templates); and EC-1
placed the canonical ADR form in the ADR framework. AD-0012 named `templates/specification/` the base
but left the base form unauthored and deferred the inheritance documentation. EC-2 Objective 1
directed resolving template ownership and consolidation.

## Options Considered
- **One-template-one-home with a documented ownership map (chosen).** Author the base form; make the
  Library the owner of specification extensions; make the ADR framework the owner of the ADR form;
  keep work-item templates top-level; resolve top-level stubs as pointers or extension points.
- **Populate all twelve top-level stubs with forms.** Rejected: duplicates the Library's delivered
  forms and the ADR framework's form, re-creating the drift the objective exists to remove.
- **Move every template into the top-level `templates/`.** Rejected: separates specification
  templates from the framework that governs them and the ADR template from its framework.

## Rationale
Consolidation means removing duplication and establishing single ownership, not filling every stub.
Owning each template where its governing framework lives keeps templates consistent with the rules
that shape them and eliminates competing copies.

## Consequences
The base template is now concrete (completing AD-0012). No template type has two homes. Top-level
`runtime/`, `api/`, `architecture/`, and `adr/` stubs are registry pointers to their owners;
`provider/`, `plugin/`, and `evaluation/` are recognized extension points; work-item forms are
delivered. Frozen subdirectory READMEs are unchanged (Module Entry Pattern); the ownership map lives
in the top-level entry document.

## Affected Areas
[`templates/`](../../templates/), [`specifications/templates/`](../../specifications/templates/), and
[`adrs/ADR_TEMPLATE.md`](../ADR_TEMPLATE.md).

## Migration Required
Partial — done in EC-2: base form authored; work-item forms authored; ownership map documented. No
frozen README modified; no existing form moved or duplicated.

## Traceability
Origin: EC-2 Objective 1 (Board-approved). Completes AD-0012 in the Foundation
[Architecture Decisions](../../bootstrap/ARCHITECTURE_DECISIONS.md). Implemented by
[TEMPLATE_OWNERSHIP.md](../../templates/TEMPLATE_OWNERSHIP.md).
