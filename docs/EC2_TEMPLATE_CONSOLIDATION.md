# EC-2 — Template Consolidation Report (Objective 1)

Records the resolution of template ownership and consolidation, ratified as
[ADR-0007](../adrs/decisions/0007-template-ownership-and-consolidation.md) and documented in
[`templates/TEMPLATE_OWNERSHIP.md`](../templates/TEMPLATE_OWNERSHIP.md).

## The problem

Templates existed in three overlapping places: the top-level [`templates/`](../templates/)
subdirectories were contract-README stubs with no forms; the Specification Library had already
delivered working specification forms ([`specifications/templates/`](../specifications/templates/)
and per-area templates); and EC-1 placed the canonical ADR form in the ADR framework. AD-0012 named
`templates/specification/` the base but left the base form unauthored and its inheritance
undocumented.

## The resolution

**One template, one home.** Each template type now has exactly one owning home:

| Type | Owner | Top-level role |
|------|-------|----------------|
| Base specification | [`templates/specification/specification-template.md`](../templates/specification/specification-template.md) *(authored now)* | Owner |
| Specification categories (capability, domain, product, runtime, api, architecture) | Specification Library | Registry pointers |
| Provider / plugin / evaluation | Base template, extended on demand | Recognized extension points |
| ADR | [`adrs/ADR_TEMPLATE.md`](../adrs/ADR_TEMPLATE.md) | Registry pointer |
| Epic / feature / story / task | [`templates/`](../templates/) *(forms authored now)* | Owner |

## What was produced

- **Base specification template form** — the nine-section canonical base (completes AD-0012).
- **Work-item forms** — [epic](../templates/epic/epic-template.md),
  [feature](../templates/feature/feature-template.md), [story](../templates/story/story-template.md),
  [task](../templates/task/task-template.md), which had no home elsewhere.
- **Ownership map** — [`TEMPLATE_OWNERSHIP.md`](../templates/TEMPLATE_OWNERSHIP.md): the full
  base-and-extension inheritance, the ownership table, the consolidation decisions, and the extension
  deltas for provider/plugin/evaluation.

## What was deliberately *not* done

- No specification form was duplicated into the top-level stubs (that would re-create the drift the
  objective removes); the stubs are resolved as pointers or extension points instead.
- No frozen subdirectory README was modified; the ownership map is the top-level entry document
  (Module Entry Pattern / ADR-0004).

## Conformance

Framework- and technology-neutral (verified); no placeholders; all links resolve; consistent with
AD-0012, the Specification Framework, and the ADR framework.

## Result

Objective 1 is complete: template ownership is unambiguous, duplication is removed, the base template
is concrete, and AD-0012's deferred inheritance is documented.
