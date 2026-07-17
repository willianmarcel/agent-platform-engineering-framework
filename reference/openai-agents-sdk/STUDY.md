# Reference Study — OpenAI Agents SDK

A structured, analytical study of OpenAI Agents SDK (provider-native agents SDK) for the APEF. This study analyzes an external
technology to draw architectural lessons; it is **not** an endorsement, a recommendation, or
implementation guidance, and it names OpenAI Agents SDK only because analyzing it is the purpose of this
reference area. The APEF itself remains technology- and vendor-neutral.

See the directory [`README.md`](README.md) for this study's scope contract.

## Overview

The OpenAI Agents SDK offers a first-party model of agents, tools, handoffs, guardrails, and sessions.

## Why the APEF studies it

The APEF studies OpenAI Agents SDK because it is a widely adopted, provider-native approach worth contrasting with a provider-agnostic framework.

## Model summary

Agents hold instructions and tools; work is passed between agents through handoffs; guardrails validate inputs and outputs; sessions carry conversational state. The model is deliberately small and integrated with one provider's capabilities.

## Strengths

- A small, coherent set of primitives (agents, tools, handoffs, guardrails).
- Guardrails as a first-class safety concern.
- Tight integration and low friction within one provider.

## Trade-offs and limitations

- Provider-native assumptions couple designs to one supplier.
- Multi-provider portability is not the design center.
- Integration convenience can obscure abstraction boundaries.

## Takeaways for the APEF

These are architectural lessons mapped to the capability that owns the concern; they inform the
APEF's own thinking without prescribing any technology.

- Tool use, handoffs, and guardrails inform runtime and builder patterns — [Chapter 07](../../handbook/07-runtime-platform/CHAPTER.md).
- Its provider-native assumptions show precisely what a provider abstraction must insulate — [Chapter 09](../../handbook/09-provider-platform/CHAPTER.md).
- Guardrails as first-class inform the security posture and human-in-the-loop stance — [Chapter 15](../../handbook/15-security/CHAPTER.md).

## Relationships

- [Reference Index](../REFERENCE_INDEX.md) — all studies and their takeaways.
- [Platform Capability Model](../../handbook/PLATFORM_CAPABILITY_MODEL.md) — the capabilities these
  takeaways inform.

## Conventions

- Analysis only: no source code, no marketing claims, no APEF specifications or architecture.
- Takeaways are lessons for the APEF, never prescriptions to adopt OpenAI Agents SDK.
