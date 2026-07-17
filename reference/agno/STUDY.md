# Reference Study — Agno

A structured, analytical study of Agno (lightweight multi-agent framework) for the APEF. This study analyzes an external
technology to draw architectural lessons; it is **not** an endorsement, a recommendation, or
implementation guidance, and it names Agno only because analyzing it is the purpose of this
reference area. The APEF itself remains technology- and vendor-neutral.

See the directory [`README.md`](README.md) for this study's scope contract.

## Overview

Agno emphasizes high-performance, low-overhead construction of agents and multi-agent teams.

## Why the APEF studies it

The APEF studies Agno because performance characteristics and a lean authoring model are relevant to the builder and runtime concerns.

## Model summary

Agents are constructed as lightweight objects with attached tools, memory, and knowledge; the framework prioritizes minimal runtime overhead and fast instantiation, composing agents into teams for collaborative work.

## Strengths

- Low runtime overhead and fast instantiation.
- Ergonomic, minimal authoring surface.
- Composition of agents into teams with shared tools and memory.

## Trade-offs and limitations

- Leaner on enterprise governance and operational concerns.
- Performance focus can trade against broader platform features.
- Team coordination semantics are relatively implicit.

## Takeaways for the APEF

These are architectural lessons mapped to the capability that owns the concern; they inform the
APEF's own thinking without prescribing any technology.

- A lean authoring surface informs the builder plane's developer experience — [Chapter 08](../../handbook/08-builder-platform/CHAPTER.md).
- Low-overhead instantiation is a lesson for runtime performance as a quality attribute — [Chapter 07](../../handbook/07-runtime-platform/CHAPTER.md).
- Attached memory and knowledge illustrate the runtime/data-plane split (coordination vs persistence) — [Chapter 12](../../handbook/12-data-platform/CHAPTER.md).

## Relationships

- [Reference Index](../REFERENCE_INDEX.md) — all studies and their takeaways.
- [Platform Capability Model](../../handbook/PLATFORM_CAPABILITY_MODEL.md) — the capabilities these
  takeaways inform.

## Conventions

- Analysis only: no source code, no marketing claims, no APEF specifications or architecture.
- Takeaways are lessons for the APEF, never prescriptions to adopt Agno.
