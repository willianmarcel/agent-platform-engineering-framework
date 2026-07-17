# Release — Reference Guide

Guidance for using the Release specification library. Part of the
[Specification Framework](../../SPECIFICATION_FRAMEWORK.md).

## Purpose
Specify specify a release: scope, acceptance, readiness, compatibility, migration, rollback, validation, and governance.

## When to use
Use this library when a Release concern needs normative intent before the work it governs
proceeds — one specification per single owning concern.

## When not to use
Do not use it for concerns owned by another library (see the
[Library Index](../../SPECIFICATION_LIBRARY_INDEX.md)); reference those libraries instead of
duplicating them. Never use it to prescribe implementation, technology, or a specific framework.

## Relationship with other libraries
Derives from the roadmap library and constrains
none — it tails the chain; all links are
bidirectional per [Traceability](../../SPECIFICATION_TRACEABILITY.md).

## Common mistakes
- Redefining a concept owned by [Chapter 19](../../../handbook/19-devops/CHAPTER.md)
  instead of referencing it.
- Prescribing implementation or naming a technology.
- Omitting traceability or leaving acceptance criteria unmeasurable.

## Best practices
- Keep the specification at intent level; one owner; bidirectional traceability.
- Author from the [templates](../templates/) and pass every applicable gate.

## Review guidance
Apply the Operations, Testing review dimensions (see [Specification Review](../../SPECIFICATION_REVIEW.md)).

## Completion guidance
Satisfy the applicable [completion gates](../../SPECIFICATION_COMPLETION.md); completion is
attributed to the approval authority.
