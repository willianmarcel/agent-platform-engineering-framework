# Proposal — Agentic Core (P1)

## Overview
This directory holds **proposed chapter-quality content** for the four agent-native engineering
disciplines that the [AR-001 review](../../AR-001_ARCHITECTURE_REVIEW.md) found near-absent from the
Handbook. It is a staging area: the content is authored to Handbook standard but is **not yet
integrated** into the frozen Handbook numbering, index, or Knowledge Graph.

## Purpose
To close the framework's agentic-maturity gap with real content, while deferring the one part that
requires a Board decision — where each discipline lives in the Handbook and how concepts are
registered — to an explicit, gated integration step.

## Why these four
A term scan of the 22 Handbook chapters found: `context engineering` 0, `tool use / function calling`
0, `multi-agent` 0, `prompt injection / guardrail / hallucination` 0; `prompt` 18 lines, `memory` 15
lines. Evaluation (119) and retrieval/RAG (32) are already covered. These four disciplines are the
engineering concerns that make agentic systems distinct, and they are the highest-leverage additions.

## Contents
- [`01-context-and-prompt-engineering.md`](01-context-and-prompt-engineering.md) — the agent's real
  source artifact: context assembly, prompt lifecycle, context-window management.
- [`02-tool-and-function-architecture.md`](02-tool-and-function-architecture.md) — tool contracts,
  permissioning, side-effect governance, execution safety.
- [`03-multi-agent-orchestration.md`](03-multi-agent-orchestration.md) — agent roles, coordination
  topologies, handoffs, agent-to-agent contracts, convergence.
- [`04-memory-and-conversational-state.md`](04-memory-and-conversational-state.md) — working vs
  long-term memory, scope, retention, retrieval into context.
- [`06-agentic-security.md`](06-agentic-security.md) — the agent-specific threat surface: prompt
  injection (direct/indirect), guardrails, autonomy levels, human-in-the-loop, least authority.
- [`05-related-upgrades.md`](05-related-upgrades.md) — one remaining recommended upgrade
  (Evaluation-Driven Development as a peer of SDD) plus the rationale for the now-delivered
  agentic-security chapter.

## Out of Scope
- Modifying the frozen Handbook (chapters, `TABLE_OF_CONTENTS.md`, `HANDBOOK_INDEX.md`,
  `KNOWLEDGE_GRAPH.md`) — integration is a separate, Board-approved step.
- Naming any vendor, product, model, or technology (strict neutrality is preserved throughout).

## Relationships
- [AR-001 review](../../AR-001_ARCHITECTURE_REVIEW.md) — the evidence and rationale.
- [Handbook](../../../handbook/HANDBOOK_SUMMARY.md) — the body these chapters are proposed to join.

## References
- Each chapter references its owning and neighboring Handbook chapters for concepts owned elsewhere.

## Conventions
- Authored to the canonical twelve-section chapter template.
- **Concept ownership:** each chapter owns only genuinely-new agentic concepts (verified absent from
  the Handbook) and references existing owners; it defines nothing already owned.
- **Integration plan:** on Board approval, each becomes a numbered Handbook chapter with its concepts
  registered in the Knowledge Graph — the numbering/placement decision is deferred to that step.
