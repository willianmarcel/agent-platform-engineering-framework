# Quality Gates

Quality Gates define the objective criteria every contribution must satisfy before it is accepted
into APEF. Gates make quality repeatable and reviewable rather than a matter of opinion: a change
either meets a gate or it does not. This document owns the **framework-authoring** gates — the
conditions for accepting a change to the framework's own documentation and structure.

It is distinct from, and complementary to, two other gate sets it aligns with: the
[Execution Quality Gates](../execution/QUALITY_GATES.md), which gate work *produced by* the Execution
Framework, and the [Specification Completion gates](../specifications/SPECIFICATION_COMPLETION.md),
which gate a specification's readiness. Where those apply, they apply in addition to these.

## The gates

A contribution is accepted only when all applicable gates below pass.

### G-1 · Structural conformance
The change respects the repository topology and the [Repository Guide](REPOSITORY_GUIDE.md):
every artifact is in its correct home, every new directory carries an eight-section README
(AD-0001), and the Module Entry Pattern is preserved (frozen READMEs unmodified; authoritative
content in entry documents).

### G-2 · Documentation completeness
No placeholders remain — no `TODO`, `TBD`, `Coming Soon`, or empty section. Every document is
useful and self-contained on merge. Chapters conform to the twelve-section template; other
artifacts conform to their template.

### G-3 · Concept single-ownership
No concept is defined in more than one place. New terminology is introduced in exactly one owning
chapter and referenced elsewhere. The change introduces no duplicate definition and no orphaned
concept.

### G-4 · Link integrity
Every internal link resolves. Cross-references point to the owning artifact rather than restating
it. No dangling relative path is introduced.

### G-5 · Neutrality
Handbook, specifications, execution, examples, and governance content name no vendor, product, or
SDK, and prescribe no technology. Reference material may analyze external technologies for
educational purposes only, and only within `reference/`.

### G-6 · Traceability
Every deliverable traces to its origin: to its governing Handbook chapter, to its specification
where applicable, and — for architecturally significant choices — to an ADR. Bidirectional
traceability is preserved.

### G-7 · Decision integrity
Any architecturally significant decision embodied by the change is recorded as an ADR in
[`../adrs/`](../adrs/) following the ADR framework. Frozen decisions are not rewritten; they are
superseded through the defined lifecycle.

### G-8 · Consistency
The change is internally consistent with the Handbook, Execution Framework, Specification Library,
and Governance Package. It introduces no contradiction in voice, structure, terminology, or
architectural altitude.

## How gates are checked

Gates are verifiable by inspection and, where practical, by mechanical checks against the
repository (for placeholders, link resolution, single-ownership, and neutrality markers). A gate
is binary; a partial pass is a fail. The review dimensions in the
[Review Framework](../execution/REVIEW_FRAMEWORK.md) map onto these gates, so a review that clears
all dimensions also clears the corresponding gates.

Because APEF prescribes no executable automation, these gates define *what* must hold; any tooling
that assists in checking them is an implementation choice left to the adopting team and is out of
the framework's scope.

## Relationships

- Enforces the standards in [`ENGINEERING_GUIDE.md`](ENGINEERING_GUIDE.md).
- Is a precondition of the [`RELEASE_PROCESS.md`](RELEASE_PROCESS.md) — a release may be cut only
  when every gate passes across its scope.
- [`WORKFLOW.md`](WORKFLOW.md) specifies at which point in the contribution flow each gate is
  applied.
- Complements the [Execution Quality Gates](../execution/QUALITY_GATES.md) and the
  [Specification Completion gates](../specifications/SPECIFICATION_COMPLETION.md).
