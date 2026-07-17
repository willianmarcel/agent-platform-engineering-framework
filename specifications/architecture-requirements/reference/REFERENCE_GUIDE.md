# Architecture Requirements — Reference Guide

Guidance for using the Architecture Requirements specification library. Part of the
[Specification Framework](../../SPECIFICATION_FRAMEWORK.md).

## Purpose
Specify specify what the architecture must satisfy: drivers, constraints, quality-attribute scenarios, risks, trade-offs, and the forces behind decisions.

## When to use
Use this library when a Architecture Requirements concern needs normative intent before the work it governs
proceeds — one specification per single owning concern.

## When not to use
Do not use it for concerns owned by another library (see the
[Library Index](../../SPECIFICATION_LIBRARY_INDEX.md)); reference those libraries instead of
duplicating them. Never use it to prescribe implementation, technology, or a specific framework.

## Relationship with other libraries
Derives from the domains library and constrains
the runtime library; all links are
bidirectional per [Traceability](../../SPECIFICATION_TRACEABILITY.md).

## Common mistakes
- Redefining a concept owned by [Chapter 06](../../../handbook/06-reference-architecture/CHAPTER.md)
  instead of referencing it.
- Prescribing implementation or naming a technology.
- Omitting traceability or leaving acceptance criteria unmeasurable.

## Best practices
- Keep the specification at intent level; one owner; bidirectional traceability.
- Author from the [templates](../templates/) and pass every applicable gate.

## Review guidance
Apply the Architecture, Security review dimensions (see [Specification Review](../../SPECIFICATION_REVIEW.md)).

## Completion guidance
Satisfy the applicable [completion gates](../../SPECIFICATION_COMPLETION.md); completion is
attributed to the approval authority.
