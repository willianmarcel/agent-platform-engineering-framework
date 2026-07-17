# P1 — Agentic Core (planning brief)

## Purpose

The independent architecture review (`docs/AR-001_ARCHITECTURE_REVIEW.md`) found the framework strong on form but thin on the engineering disciplines that are native to agent platforms. A term scan across the 22 Handbook chapters is the evidence base for this brief: "context engineering" returned 0 hits, "tool use / function calling" 0, "multi-agent" 0, and "prompt injection / guardrail / hallucination" 0; "prompt" appeared in only 18 lines and "memory" in 15. By contrast, evaluation (119 lines) and retrieval (32 lines) are already covered.

This is a *planning* brief. It proposes elevating four agent-native disciplines to first-class treatment and names a proposed owning home for each. It deliberately does not define the concepts or draft the chapters; those remain downstream work to be scoped and reviewed on their own terms.

## The four disciplines

### 1. Context & Prompt Engineering

This is the agent's real "source code," yet the scan shows near-absence: "context engineering" at 0 hits and "prompt" confined to 18 lines. It would own context assembly, the prompt lifecycle (authoring, versioning, promotion, rollback), and context-window management as a governed budget rather than an implementation afterthought. Proposed home: a new Handbook chapter, given that no existing chapter carries this concern today.

### 2. Tool / Function Architecture

Tool use is how an agent acts on the world, but the scan returns 0 hits for "tool use / function calling." This discipline would own tool contracts, permissioning, side-effect governance, and execution safety — the boundary where an agent's decisions become real-world actions. Proposed home: a new Handbook chapter, since this responsibility currently has no owner and spans design, security, and operations.

### 3. Multi-Agent Orchestration

"Multi-agent" returns 0 hits, leaving coordination patterns unaddressed. This discipline would own supervisor and handoff patterns, agent-to-agent protocols, and the delegation and escalation contracts that let multiple agents cooperate without ambiguity. Proposed home: a new Handbook chapter, as orchestration is a distinct architectural layer above any single agent.

### 4. Memory & Conversational State

The scan finds "memory" in only 15 lines, so the framework treats durable state as incidental. This discipline would own short- and long-term memory, retrieval into working context, and cross-turn continuity — connecting to the retrieval material that already exists rather than duplicating it. Proposed home: a new Handbook chapter that references and depends on the existing retrieval coverage.

## Two related upgrades

Beyond the four disciplines, the review points to two adjacent upgrades worth sequencing alongside P1:

- **Evaluation-Driven Development as a peer of Specification-Driven Development.** Evaluation is already the best-covered area (119 lines), which makes it a natural candidate to elevate from a supporting practice to a first-class development model, with behavioral-regression gates that block changes on measured behavior rather than on structure alone.

- **Agentic security.** The scan returned 0 hits for "prompt injection / guardrail / hallucination." A dedicated security thread would address prompt injection, guardrails, explicit autonomy levels, and human-in-the-loop checkpoints — the failure modes specific to autonomous agents rather than generic application security.

## Scope note

Every item above is a proposal for where a discipline should live and what it should own. Naming an owning home is not the same as writing it; each chapter or deepening remains subject to its own scoping and review. This brief adds nothing to the Handbook itself and changes no existing artifact.
