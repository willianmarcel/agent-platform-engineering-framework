# EC-1 — Next Milestone Proposal

The Architecture Team's proposal for the milestone following EC-1, for the Architecture Board's
consideration. It is grounded in the [Engineering Assessment](ENGINEERING_ASSESSMENT.md) gap list
and the state left by EC-1. EC-1 resolved the two High-priority gaps (G1, G2); the remaining path to
full Engineering Completeness is the Assessment's Medium and Low findings.

## Where EC-1 leaves the framework

- **Conceptually Complete** (Handbook, PCM) — unchanged.
- **Methodologically Complete** (Execution + Specification frameworks) — unchanged.
- **Engineering methodology** (bootstrap guides) — now complete (G1).
- **Decision governance** (ADR framework) — now established, migration gated on approval (G2).

Remaining from the Assessment: instance-content areas are ready-but-empty by design, and two
editorial reconciliations (OD-2 title/TOC, OD-4 principles home) are open.

## Proposed milestone: EC-2 — Decision Log Activation & Reference Instances

A milestone in two coordinated parts, sized to be completable and Board-reviewable.

### Part A — Activate the decision log (depends on OD-9 approval)
Author the six seed ADRs the [Migration Plan](../adrs/ADR_MIGRATION_PLAN.md) defines
(ADR-0001..ADR-0006), populate the [Index](../adrs/ADR_INDEX.md), and reconcile OD-2 (author
ADR-0003 and resolve the title-vs-TOC note under Board direction). This turns the established-but-empty
ADR log into a populated, exemplary one and demonstrates the framework on real decisions.

### Part B — Seed the ready-structure instance areas
Provide a small number of **exemplar** instances that demonstrate the ready-structure areas without
over-populating them: one worked ADR-driven architecture instance, one completed playbook procedure
(e.g., architecture-review), and one specialized template instance. Each demonstrates the pattern so
adopters have a concrete model, while the areas remain designed for growth through use.

## Explicitly out of scope for EC-2

- Resolving **OD-4** (mandated-principles home) — remains a Release 1.1 item unless the Board pulls
  it forward.
- Any executable automation, technology, or vendor content (permanently out of scope).
- Bulk-populating instance areas — the framework's value is the pattern, not exhaustive instances.

## Alternative considered

**"Publish v1.0 now, defer EC-2."** The framework is already publication-ready per the
[Publication Readiness](PUBLICATION_READINESS.md) assessment, and EC-1 strengthened it further. The
Board could choose to lift OD-6, commit, and tag v1.0 immediately, treating EC-2 as post-1.0
evolution. This is a legitimate path; the Team defers the sequencing decision to the Board.

## Recommendation

Approve EC-1; rule on OD-7–OD-9; then either (a) proceed to **EC-2 Part A** to activate the decision
log as the natural next increment, or (b) authorize v1.0 publication and fold EC-2 into Phase 5
evolution. The Team recommends **(a) then publication**, so v1.0 ships with a populated, exemplary
decision log rather than an empty one.
