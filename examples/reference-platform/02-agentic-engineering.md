# Reference Platform — Agentic Engineering

*Applies APEF steps 5–6 (the agentic core, Ch 22–26) to the Support Operations Assistant Platform.
Non-executable and technology-neutral.*

This is where an agent platform is won or lost. Each section applies one agentic discipline to this
scenario.

## Context & prompt engineering (Ch 22)

The assistant's context on each call is assembled, not concatenated, from four layers with a declared
budget:

| Layer | Source | Trust | Budget share |
|-------|--------|-------|--------------|
| System | Platform-owned assistant instructions and safety rules | Highest | Fixed, small |
| Policy | The tenant's answerable/actionable rules (from the control plane) | High | Fixed, small |
| Knowledge | Retrieved, ranked, tenant-scoped passages with citations | Untrusted data | Capped share |
| History | Compacted prior turns of this session | Medium | Bounded |
| Input | The support agent's current question | Untrusted data | Remainder |

- **Trust layering:** knowledge and input are framed as *data*, never as instructions. Retrieved
  passages cannot change the assistant's behavior — they are material to answer *from*.
- **Budget behavior:** if retrieved knowledge exceeds its share, the lowest-ranked passages are
  dropped, not the policy or system layers.
- **Prompt lifecycle:** the system prompt is a versioned, owned artifact; a change to it is gated by
  evaluation (see [`03-evaluation-and-decisions.md`](03-evaluation-and-decisions.md)).

## Tool & function architecture (Ch 23)

The assistant acts only through declared, classified tools, granted by least privilege:

| Tool | Side-effect class | Safeguard |
|------|-------------------|-----------|
| `search_knowledge` | Read-only | Freely invoked; logged; tenant-scoped |
| `lookup_case` | Read-only | Freely invoked; logged; tenant-scoped |
| `draft_response` | Reversible | Produces a draft for the human; never sends |
| `escalate_case` | Reversible | Creates an escalation; logged; undoable |
| `send_to_customer` | **Not granted** | Out of the assistant's toolset entirely — sending is a human action |

The customer-facing send is *not a tool the agent holds*; the human sends. `draft_response` returns a
draft framed as data, never as an instruction the assistant then "acts on." Every invocation is logged
with inputs, tenant, and outcome.

## Multi-agent coordination (Ch 24)

A single agent suffices for most questions; multi-agent coordination is used **only** where it earns
its cost:

- **Default:** one assistant agent with the toolset above.
- **When a question needs specialized knowledge** (e.g., billing vs. technical), a **supervisor**
  decomposes it and delegates to a specialist agent with a narrowed, read-only grant, then integrates
  the result. The handoff carries the question and tenant scope under a contract and returns a bounded
  finding; a step bound prevents loops.
- Authority does not escalate across the handoff — the specialist holds *less* than the supervisor,
  never more.

## Memory & conversational state (Ch 25)

- **Working memory:** the current session's turns, compacted as it grows so continuity is preserved
  within the context budget.
- **Long-term memory:** per-tenant and per-support-agent preferences (e.g., preferred tone), curated
  as structured facts — never raw transcripts. Case content is **not** remembered; it is read live
  from the systems of record.
- **Scope:** memory is strictly tenant- and user-scoped; one tenant's memory can never enter another's
  context. Retention rules expire session working memory and honor removal requests.

## Agentic security (Ch 26)

The platform reads untrusted knowledge and case data and can act, so it is designed defensively:

- **Untrusted content:** retrieved passages and case data are screened and framed as data; an input
  guardrail detects instruction-like payloads (indirect injection) before the assistant acts.
- **Autonomy level:** the assistant is *act-with-approval* for anything reversible and customer-visible
  (drafts await human send) and *suggest-only* for anything outside its grant. Irreversible customer
  actions are structurally impossible (no such tool).
- **Blast-radius minimization:** least-authority identity, read-only default tools, tenant-scoped
  memory — a successful injection yields, at most, a bad *draft* a human reviews, never an action.
- **Output guardrail:** drafts are screened for leaked internal data or disallowed content before being
  shown to the support agent.

## What steps 5–6 produced

A concrete agentic design: a layered, budgeted, trust-separated context; a least-privilege, side-effect
-classified toolset in which the dangerous action simply does not exist for the agent; bounded
multi-agent coordination used only where justified; tenant-scoped curated memory; and a defense-in
-depth security posture where the worst outcome of compromise is a reviewed draft. Every choice traces
to its owning chapter and to a decision in [`03-evaluation-and-decisions.md`](03-evaluation-and-decisions.md).
