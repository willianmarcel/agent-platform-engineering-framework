# ADR Template

This is the canonical form every Architecture Decision Record is authored from. Copy it into
[`decisions/`](decisions/) as `NNNN-short-title.md`, replace the guidance in each field, and delete
this preamble. Fields are mandatory unless marked *(optional)*. The field set mirrors the eight
fields of the Foundation register (AD format) so that ADRs and the Foundation Architecture
Decisions read as one continuous decision log.

The relative links in the form below are written **relative to `decisions/`**, where the finished
record lives — so they resolve correctly from a completed ADR, not from this template's own
location.

---

# ADR-NNNN — <Short imperative title>

- **Status:** <Proposed | Accepted | Rejected | Superseded | Deprecated> — see [ADR Lifecycle](../ADR_LIFECYCLE.md)
- **Date:** <YYYY-MM-DD of the current status>
- **Category:** <one category from [decision-categories/](../decision-categories/)>
- **Authority:** <the body that ratified this decision, e.g. Architecture Board>
- **Supersedes:** <ADR-XXXX / AD-XXXX, or "—">
- **Superseded By:** <ADR-YYYY, or "—">

## Decision
State the decision in one or two sentences, in the present tense, as a rule the framework now
follows. This is the single most important field; it must be unambiguous.

## Context
The situation and forces that made a decision necessary: the problem, the constraints, and the
relevant background. State facts, not the choice.

## Options Considered
The alternatives that were genuinely weighed, each with its salient trade-off. Include the chosen
option and at least the strongest rejected one. *(Optional only for decisions with a single viable
path, in which case state that no alternative was viable and why.)*

## Rationale
Why the decision was chosen over the alternatives — the reasoning that connects the context and
options to the decision.

## Consequences
What becomes true because of this decision: benefits, costs, new constraints, and follow-on work.
State negative consequences honestly.

## Affected Areas
The directories, chapters, specifications, or other decisions this decision touches, as relative
links. Where it changes repository structure, name the affected modules.

## Migration Required
Whether existing artifacts must change to conform (Yes / No / Partial) and, if so, what must be
done. A decision that requires migration is not complete until the migration is planned.

## Traceability
Links to the origin of the decision (governing Handbook chapter, specification, milestone approval)
and to any decision it supersedes or is superseded by. Every ADR traces both to why it exists and
to what it affects.

## References *(optional)*
External or cross-repository sources relevant to the decision.
