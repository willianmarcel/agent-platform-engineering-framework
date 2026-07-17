# Specification Reference Guide

Guidance on the decisions of specification management: when to create, split, merge, supersede,
or archive a specification. Part of the
[Specification Framework](../SPECIFICATION_FRAMEWORK.md).

## When to create a specification
Create one when a distinct engineering concern needs normative intent before implementation —
one specification per single owning concern (see the [Taxonomy](../SPECIFICATION_TAXONOMY.md)).

## When to split a specification
Split when a specification has come to cover more than one owning concern, or when parts have
different owners or lifecycles. Each resulting specification must have a single owner and trace
to the original.

## When to merge specifications
Merge only when specifications share one owner and one concern and their separation adds no
clarity. The merged specification supersedes the originals, which are archived.

## When to supersede a specification
Supersede when an approved specification's intent changes materially. A new version is authored
and approved; the predecessor becomes [Superseded](../SPECIFICATION_LIFECYCLE.md) and is
retained for history.

## When to archive a specification
Archive when a specification is retired from active use. Archived records are immutable and kept
for traceability.

## Discipline
Every such decision preserves single ownership, bidirectional traceability, and immutable
history, per [Governance](../SPECIFICATION_GOVERNANCE.md).
