# Reference Study — Flowise

A structured, analytical study of Flowise (visual LLM workflow builder) for the APEF. This study analyzes an external
technology to draw architectural lessons; it is **not** an endorsement, a recommendation, or
implementation guidance, and it names Flowise only because analyzing it is the purpose of this
reference area. The APEF itself remains technology- and vendor-neutral.

See the directory [`README.md`](README.md) for this study's scope contract.

## Overview

Flowise provides visual, node-based construction of LLM workflows.

## Why the APEF studies it

The APEF studies Flowise because its visual composition model is a useful reference for builder-platform interaction design.

## Model summary

Workflows are assembled by connecting nodes on a canvas, each node representing a step or component, making flow construction accessible without programming.

## Strengths

- Accessible, node-based visual composition.
- Fast assembly of flows without code.
- Clear visual representation of a flow.

## Trade-offs and limitations

- Visual node graphs scale poorly to large, complex flows.
- The node model can constrain expressiveness.
- Governance and operations are secondary.

## Takeaways for the APEF

These are architectural lessons mapped to the capability that owns the concern; they inform the
APEF's own thinking without prescribing any technology.

- Node-based visual composition informs the builder plane's visual composition and reusable components — [Chapter 08](../../handbook/08-builder-platform/CHAPTER.md).
- The accessibility of visual authoring informs experience and interaction design — [Chapter 17](../../handbook/17-ui-ux/CHAPTER.md).
- The scaling limits of pure visual graphs are a cautionary lesson for the builder plane — [Chapter 08](../../handbook/08-builder-platform/CHAPTER.md).

## Relationships

- [Reference Index](../REFERENCE_INDEX.md) — all studies and their takeaways.
- [Platform Capability Model](../../handbook/PLATFORM_CAPABILITY_MODEL.md) — the capabilities these
  takeaways inform.

## Conventions

- Analysis only: no source code, no marketing claims, no APEF specifications or architecture.
- Takeaways are lessons for the APEF, never prescriptions to adopt Flowise.
