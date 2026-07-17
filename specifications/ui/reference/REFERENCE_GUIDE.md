# Experience — Reference Guide

Guidance for using the Experience specification library. Part of the
[Specification Framework](../../SPECIFICATION_FRAMEWORK.md).

## Purpose
Specify specify the experience: interaction, navigation, accessibility, journeys, and human interaction, as philosophy rather than interface.

## When to use
Use this library when a Experience concern needs normative intent before the work it governs
proceeds — one specification per single owning concern.

## When not to use
Do not use it for concerns owned by another library (see the
[Library Index](../../SPECIFICATION_LIBRARY_INDEX.md)); reference those libraries instead of
duplicating them. Never use it to prescribe implementation, technology, or a specific framework.

## Relationship with other libraries
Derives from the observability library and constrains
the backlog library; all links are
bidirectional per [Traceability](../../SPECIFICATION_TRACEABILITY.md).

## Common mistakes
- Redefining a concept owned by [Chapter 17](../../../handbook/17-ui-ux/CHAPTER.md)
  instead of referencing it.
- Prescribing implementation or naming a technology.
- Omitting traceability or leaving acceptance criteria unmeasurable.

## Best practices
- Keep the specification at intent level; one owner; bidirectional traceability.
- Author from the [templates](../templates/) and pass every applicable gate.

## Review guidance
Apply the Product, Documentation review dimensions (see [Specification Review](../../SPECIFICATION_REVIEW.md)).

## Completion guidance
Satisfy the applicable [completion gates](../../SPECIFICATION_COMPLETION.md); completion is
attributed to the approval authority.
