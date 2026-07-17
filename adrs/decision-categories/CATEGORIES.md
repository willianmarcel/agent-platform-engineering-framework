# ADR Decision Categories

The canonical taxonomy for classifying Architecture Decision Records. Every ADR is assigned exactly
one category. The set is deliberately small and stable; it aligns with the framework's concern areas
(the Handbook foundations, planes, and cross-cutting concerns, plus the governance model) so that a
category tells a reader which part of the framework a decision shapes. Changing this taxonomy is
itself an architecturally significant decision, recorded as an ADR.

## The categories

### C1 · Structural & Documentation
Decisions about repository topology, module boundaries, directory naming, the README contract, the
documentation vocabulary, and cross-referencing. These shape how the framework is organized and
navigated.
*Examples of this concern in existing decisions: the README contract, cross-reference rules, the
architecture-requirements rename, removal of the generic diagrams directory, the Module Entry
Pattern.*

### C2 · Methodology & Process
Decisions about how work is done: Specification-Driven Development, the contribution workflow, the
quality gates, the review model, and the release process.
*Concern area: the Development Methodology and the Execution/Specification frameworks.*

### C3 · Platform Architecture
Decisions about the reference architecture, the platform planes, runtime shape, and the boundaries
between architectural layers of the platform the framework describes.
*Concern area: the Reference Architecture and the platform planes.*

### C4 · Capability Design
Decisions about the design of platform capabilities — builder, provider, plugin, control, data, and
API capabilities — and how they are modeled.
*Concern area: the capability chapters and the Platform Capability Model.*

### C5 · Cross-Cutting Concerns
Decisions about concerns that span the platform: security, observability, identity and
authorization, user and creator experience, and evaluation-versus-testing.
*Concern area: the cross-cutting chapters.*

### C6 · Governance & Lifecycle
Decisions about the governance model itself: ownership and authority, concept ownership rulings,
versioning and version control, the ADR and specification instruments, and standing conventions.
*Concern area: the Architecture Governance Package and the decision instruments.*

## Choosing a category

Assign the category that names the decision's **primary** concern. A decision that appears to span
categories usually has one dominant concern and secondary effects; classify by the dominant concern
and record the secondary effects in the ADR's Affected Areas and Traceability fields. If a decision
genuinely cannot be classified, that is a signal it is compound and should be split into separate
ADRs.

## Relationship to existing decisions

The Foundation Architecture Decisions (`AD-`) and the Board Outstanding Decisions (`OD-`) predate
this taxonomy but map onto it cleanly; the [Migration Plan](../ADR_MIGRATION_PLAN.md) and
[Traceability Matrix](../ADR_TRACEABILITY_MATRIX.md) record the category assigned to each existing
decision. This taxonomy governs classification going forward.
