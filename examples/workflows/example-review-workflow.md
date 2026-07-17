# Example — Illustrative Review Workflow (conceptual)

A conceptual, **non-executable**, **technology-neutral** example demonstrating APEF concepts. It
defines no real product and names no vendor, product, framework, SDK, or implementation detail;
it illustrates methodology only.

**Intent.** Compose a multi-step review that classifies a request, drafts a response, obtains human review, and finalizes it. *(illustrative)*

**Composition.** Step 1 classify → Step 2 draft → Step 3 human review → Step 4 finalize; composed at design time in the builder plane ([Chapter 08](../../handbook/08-builder-platform/CHAPTER.md)).

**Human-in-the-loop.** Step 3 keeps a person a deciding participant ([Chapter 17](../../handbook/17-ui-ux/CHAPTER.md)).

**Execution.** The workflow definition is handed to the runtime for execution ([Chapter 07](../../handbook/07-runtime-platform/CHAPTER.md)); the builder does not run it.

**Acceptance criteria.** The workflow produces a reviewed, finalized outcome with human oversight at the review step — measurable in a real Workflow Specification.

## Concepts demonstrated

This example demonstrates workflow composition (08), design-time vs run-time boundary (08/07), human-in-the-loop (17).

## Relationships

- [Workflow Examples](WORKFLOW_EXAMPLES.md) — the area entry document.
- [Examples Index](../EXAMPLES_INDEX.md) — all example areas.
- [Platform Capability Model](../../handbook/PLATFORM_CAPABILITY_MODEL.md) — the capabilities this
  example draws on.

## Conventions

- Illustrative only; every value is a placeholder for a real, measurable one in an actual
  specification.
- Names no technology; demonstrates APEF concepts exclusively.
