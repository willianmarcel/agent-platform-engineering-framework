# Related Upgrades (P1)

> **Proposed follow-on work (P1 — Agentic Core).** Two upgrades that the four agentic-core chapters
> depend on or point to. Recorded here as scoped recommendations, not full chapters; each merits its
> own Board-approved milestone.

## A. Elevate Evaluation-Driven Development to a peer of Specification-Driven Development

**Why.** APEF's methodology spine is Specification-Driven Development (SDD): intent is specified
before it is built. But agentic behavior is **non-deterministic and model-dependent** — the same
input can yield different outputs, and behavior shifts when the underlying model or the context
changes. SDD alone cannot gate this: a specification says what *should* happen; it does not verify
what a probabilistic system *does* happen. Evaluation is already the framework's strongest agentic
area (the deepest coverage in the Handbook), but it is positioned as a downstream check rather than a
driver.

**Proposal.** Recognize **Evaluation-Driven Development (EDD)** as a peer of SDD in the Development
Methodology: for agentic capabilities, an **evaluation suite is authored alongside the
specification**, and **behavioral-regression gates** — evaluation runs that must pass before a change
to a prompt, context assembly, tool set, or coordination becomes active — join the quality gates.
This makes non-determinism a first-class engineering reality: changes are validated against measured
behavior, not assumed correct. The Context, Tool, Coordination, and Memory chapters each already
require "change is gated behind evaluation"; EDD-as-peer makes that requirement a methodology, not a
per-chapter footnote.

**Scope note.** This deepens the Development Methodology and Evaluation chapters and the Quality
Gates; it introduces no new concept ownership conflict (evaluation remains owned by the Evaluation
chapter; methodology by Development Methodology).

## B. A dedicated Agentic Security chapter

**Why.** The four agentic-core chapters repeatedly reach a security boundary that the current Security
chapter does not yet cover at the agentic level. A term scan found **zero** Handbook coverage of
`prompt injection`, `jailbreak`, `guardrail`, or `hallucination`. Yet:

- **Context & Prompt Engineering** warns of *trust inversion* — lower-trust input overriding
  higher-trust instructions.
- **Tool & Function Architecture** warns of *result-as-instruction* — a compromised or malformed tool
  result steering the agent — and governs irreversible action.
- **Multi-Agent Coordination** warns of *authority creep* across handoffs.
- **Memory** warns of *scope leakage* of private remembered information.

These are facets of an agent-specific threat surface — **indirect prompt injection, tool abuse,
memory exfiltration, and unsafe autonomy** — that classical application security does not fully
address.

**Proposal.** A dedicated agentic-security discipline (extending, not duplicating, the Security
chapter, which owns threat model, identity, isolation) covering: prompt-injection defense (treating
all retrieved and tool-returned content as untrusted), guardrails on inputs and outputs, **autonomy
levels** and the human-in-the-loop boundary for consequential action, and reversibility as a safety
control. Autonomy and human-in-the-loop are architectural decisions, not features, and belong in the
methodology.

**Scope note.** This extends the Security chapter's cross-cutting concern to agentic threats;
concept ownership stays with Security for identity/isolation, with this discipline owning the
agent-specific threat and control concepts.

## Sequencing

Both are recommended for the milestone that integrates the four agentic-core chapters, or immediately
after. EDD-as-peer is a methodology change (broad, low-risk, high-leverage); the agentic-security
chapter is additive content on an established cross-cutting concern. Neither is a prerequisite for
reviewing the four chapters, but both are prerequisites for calling the framework *mature* on agentic
engineering.

## References

- The four agentic-core chapters in this proposal.
- [AR-001 review](../../AR-001_ARCHITECTURE_REVIEW.md) — the maturity gap and evidence.
