# Reference Study — Azure AI Foundry

A structured, analytical study of Azure AI Foundry (enterprise AI platform) for the APEF. This study analyzes an external
technology to draw architectural lessons; it is **not** an endorsement, a recommendation, or
implementation guidance, and it names Azure AI Foundry only because analyzing it is the purpose of this
reference area. The APEF itself remains technology- and vendor-neutral.

See the directory [`README.md`](README.md) for this study's scope contract.

## Overview

Azure AI Foundry is a full enterprise platform for building, evaluating, and operating AI agents at scale.

## Why the APEF studies it

The APEF studies Azure AI Foundry because as a complete platform it is a rich source of control-plane, evaluation, observability, and provider patterns.

## Model summary

It combines a model catalog, agent construction and hosting, evaluation pipelines, observability, and governance into one managed platform spanning the build-to-operate lifecycle.

## Strengths

- Breadth across the full agent lifecycle.
- Enterprise governance, evaluation, and observability.
- A model catalog abstracting many models.

## Trade-offs and limitations

- Platform breadth implies coupling and lock-in.
- Opinionated integration across concerns.
- Adoption weight for smaller efforts.

## Takeaways for the APEF

These are architectural lessons mapped to the capability that owns the concern; they inform the
APEF's own thinking without prescribing any technology.

- A model catalog abstracting many models validates the provider-abstraction principle — [Chapter 09](../../handbook/09-provider-platform/CHAPTER.md).
- Its evaluation pipelines and observability inform those cross-cutting capabilities — [Chapter 16](../../handbook/16-evaluation/CHAPTER.md).
- Its governance and administration inform the control plane — [Chapter 11](../../handbook/11-control-plane/CHAPTER.md).

## Relationships

- [Reference Index](../REFERENCE_INDEX.md) — all studies and their takeaways.
- [Platform Capability Model](../../handbook/PLATFORM_CAPABILITY_MODEL.md) — the capabilities these
  takeaways inform.

## Conventions

- Analysis only: no source code, no marketing claims, no APEF specifications or architecture.
- Takeaways are lessons for the APEF, never prescriptions to adopt Azure AI Foundry.
