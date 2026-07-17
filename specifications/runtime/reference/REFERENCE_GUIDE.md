# Runtime — Reference Guide

Guidance for using the Runtime specification library. Part of the
[Specification Framework](../../SPECIFICATION_FRAMEWORK.md).

## Purpose
Specify specify runtime intent: responsibilities, constraints, execution models, operational behaviour, and lifecycle, within runtime boundaries.

## When to use
Use this library when a Runtime concern needs normative intent before the work it governs
proceeds — one specification per single owning concern.

## When not to use
Do not use it for concerns owned by another library (see the
[Library Index](../../SPECIFICATION_LIBRARY_INDEX.md)); reference those libraries instead of
duplicating them. Never use it to prescribe implementation, technology, or a specific framework.

## Relationship with other libraries
Derives from the architecture-requirements library and constrains
the security library; all links are
bidirectional per [Traceability](../../SPECIFICATION_TRACEABILITY.md).

## Common mistakes
- Redefining a concept owned by [Chapter 07](../../../handbook/07-runtime-platform/CHAPTER.md)
  instead of referencing it.
- Prescribing implementation or naming a technology.
- Omitting traceability or leaving acceptance criteria unmeasurable.

## Best practices
- Keep the specification at intent level; one owner; bidirectional traceability.
- Author from the [templates](../templates/) and pass every applicable gate.

## Review guidance
Apply the Runtime, Architecture review dimensions (see [Specification Review](../../SPECIFICATION_REVIEW.md)).

## Completion guidance
Satisfy the applicable [completion gates](../../SPECIFICATION_COMPLETION.md); completion is
attributed to the approval authority.
