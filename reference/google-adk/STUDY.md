# Reference Study — Google ADK

A structured, analytical study of Google ADK (enterprise agent development kit) for the APEF. This study analyzes an external
technology to draw architectural lessons; it is **not** an endorsement, a recommendation, or
implementation guidance, and it names Google ADK only because analyzing it is the purpose of this
reference area. The APEF itself remains technology- and vendor-neutral.

See the directory [`README.md`](README.md) for this study's scope contract.

## Overview

Google's Agent Development Kit provides an opinionated, enterprise-oriented approach to building, evaluating, and deploying agents.

## Why the APEF studies it

The APEF studies Google ADK because its enterprise and deployment posture informs the control-plane, evaluation, and DevOps concerns.

## Model summary

The kit offers structured agent construction, multi-agent composition, built-in evaluation, and a path to deployment and operation, with an opinionated project structure and lifecycle.

## Strengths

- Integrated build-evaluate-deploy lifecycle.
- Enterprise deployment and operational posture.
- Built-in evaluation as part of the workflow.

## Trade-offs and limitations

- Opinionated structure reduces flexibility.
- Lifecycle is oriented to its own ecosystem.
- Breadth can add adoption weight.

## Takeaways for the APEF

These are architectural lessons mapped to the capability that owns the concern; they inform the
APEF's own thinking without prescribing any technology.

- Its build-evaluate-deploy lifecycle informs engineering operations and delivery — [Chapter 19](../../handbook/19-devops/CHAPTER.md).
- Built-in evaluation reinforces evaluation as a first-class, continuous capability — [Chapter 16](../../handbook/16-evaluation/CHAPTER.md).
- Enterprise governance and lifecycle inform the control plane — [Chapter 11](../../handbook/11-control-plane/CHAPTER.md).

## Relationships

- [Reference Index](../REFERENCE_INDEX.md) — all studies and their takeaways.
- [Platform Capability Model](../../handbook/PLATFORM_CAPABILITY_MODEL.md) — the capabilities these
  takeaways inform.

## Conventions

- Analysis only: no source code, no marketing claims, no APEF specifications or architecture.
- Takeaways are lessons for the APEF, never prescriptions to adopt Google ADK.
