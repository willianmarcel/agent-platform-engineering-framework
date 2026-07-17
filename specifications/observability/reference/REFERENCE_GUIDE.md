# Observability — Reference Guide

Guidance for using the Observability specification library. Part of the
[Specification Framework](../../SPECIFICATION_FRAMEWORK.md).

## Purpose
Specify specify what must be observable and to what standard: metrics, logs, traces, health, monitoring, visibility, and observability acceptance.

## When to use
Use this library when a Observability concern needs normative intent before the work it governs
proceeds — one specification per single owning concern.

## When not to use
Do not use it for concerns owned by another library (see the
[Library Index](../../SPECIFICATION_LIBRARY_INDEX.md)); reference those libraries instead of
duplicating them. Never use it to prescribe implementation, technology, or a specific framework.

## Relationship with other libraries
Derives from the security library and constrains
the ui library; all links are
bidirectional per [Traceability](../../SPECIFICATION_TRACEABILITY.md).

## Common mistakes
- Redefining a concept owned by [Chapter 14](../../../handbook/14-observability/CHAPTER.md)
  instead of referencing it.
- Prescribing implementation or naming a technology.
- Omitting traceability or leaving acceptance criteria unmeasurable.

## Best practices
- Keep the specification at intent level; one owner; bidirectional traceability.
- Author from the [templates](../templates/) and pass every applicable gate.

## Review guidance
Apply the Observability, Operations review dimensions (see [Specification Review](../../SPECIFICATION_REVIEW.md)).

## Completion guidance
Satisfy the applicable [completion gates](../../SPECIFICATION_COMPLETION.md); completion is
attributed to the approval authority.
