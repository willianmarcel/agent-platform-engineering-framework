# Context & Prompt Engineering

> **Proposed chapter (P1 — Agentic Core).** Authored to Handbook standard; not yet integrated into
> the frozen Handbook numbering or Knowledge Graph. Owns the context/prompt-engineering concepts
> defined below; references other chapters for concepts they own.

## 1. Introduction

In a conventional system, the source code is the primary artifact engineers author, version, and
review. In an agent platform, a second primary artifact sits beside it: the **context** supplied to
the model on every call — the instructions, retrieved knowledge, tool descriptions, history, and
current input that together determine the agent's behavior. Context is not configuration and not
documentation; it is the executable specification of what the agent does at that moment.

**Context Engineering.** The discipline of deciding what information enters the model's context on
each call, how it is assembled, ordered, and bounded, and how that assembly is versioned, tested, and
evolved. It treats the context as a first-class engineering artifact with a lifecycle, not as ad-hoc
text.

Because model behavior is highly sensitive to context, this discipline is where much of an agent's
quality, cost, and reliability is decided. A platform that leaves context assembly implicit — strings
concatenated at call sites — cannot reason about, review, or improve its agents' behavior. This
chapter defines context and prompts as governed artifacts and the engineering practice around them.

## 2. Objectives

- Establish the **context** and the **prompt** as first-class, versioned engineering artifacts.
- Define the **context assembly** process and the roles of its layers.
- Make the **context window** an explicit engineering constraint with a managed budget.
- Provide principles, patterns, and anti-patterns for authoring and evolving context.
- Connect context engineering to specification, evaluation, and the runtime.

## 3. Concepts

This chapter **owns** the following concepts.

**Prompt.** A structured instruction supplied to the model. A prompt is authored, versioned, and
reviewed like code — never an inline literal assembled at a call site without governance.

**Prompt layering.** The separation of a prompt into distinct layers by authority and lifetime:
**system** (platform-owned behavior and constraints), **developer** (the builder's task-specific
instructions), and **input** (the end user's or upstream system's request). Layers have different
owners, change at different rates, and carry different trust.

**Context.** The complete set of information provided to the model on a single call: the prompt
layers, retrieved knowledge, tool and capability descriptions, prior interaction history, and the
current input. The context — not any single prompt — is what determines the response.

**Context assembly.** The deterministic process that composes the context for a call from its
sources, applying selection, ordering, formatting, and truncation rules.

**Context window.** The bounded capacity, measured in tokens, available for a single call's context.
It is a hard engineering constraint that assembly must respect.

**Context budget.** The deliberate allocation of the context window across its competing consumers
(instructions, retrieved knowledge, history, tools, headroom for the response), expressed as a policy
rather than left to chance.

**Prompt lifecycle.** The managed progression of a prompt or assembly rule from draft, through
review and evaluation, to active, superseded, or retired — with versions retained for traceability.

Concepts referenced but **owned elsewhere**: the model **provider abstraction** (Provider Platform);
**retrieval** and knowledge sourcing (Data Platform); **evaluation** of behavioral quality
(Evaluation); the **runtime** that executes calls (Runtime Platform); the **authoring experience**
for builders (Builder Platform); and **Specification-Driven Development** (Development Methodology).

## 4. Principles

1. **Context is an artifact, not a string.** It is authored, named, versioned, reviewed, and traced —
   subject to the same discipline as any specification.
2. **Assembly is deterministic and inspectable.** Given the same sources, assembly produces the same
   context; what entered the context and why is recoverable for any call.
3. **Layer by authority and trust.** System, developer, and input layers are kept distinct; lower-trust
   layers never silently override higher-trust instructions.
4. **The window is a budget, not an afterthought.** Every assembly has an explicit budget and a defined
   behavior when sources exceed it.
5. **Least context.** Include what the task requires and no more; unnecessary context adds cost,
   latency, and distraction, and dilutes the signal the model needs.
6. **Change is evaluated, not assumed.** A change to a prompt or assembly rule is validated against
   evaluation before it becomes active, because small context changes can shift behavior materially.

## 5. Architecture

Context engineering sits between the platform's knowledge and tools and the model call. A reference
arrangement separates four responsibilities:

- **Sources** — the prompt library (layered, versioned prompts), the retrieval interface to knowledge,
  the tool/capability registry, and the interaction history store.
- **Assembler** — the deterministic component that selects from sources, orders and formats them,
  enforces the context budget, and truncates or summarizes under pressure according to policy.
- **Budget policy** — the declared allocation of the window across consumers, with a defined
  overflow strategy (drop, summarize, or reject) per consumer.
- **Context record** — the captured, inspectable record of what was assembled for a call, linked to
  the response and to the prompt/rule versions used, feeding observability and evaluation.

The assembler depends on the provider abstraction only for the window size and tokenization boundary;
it prescribes no model or vendor. Retrieval is delegated to the Data Platform; execution to the
Runtime Platform. This keeps context assembly a distinct, testable stage rather than logic scattered
across call sites.

## 6. Patterns

- **Prompt library.** Central, versioned prompts referenced by identity, not copied inline — one
  owner per prompt, reused across agents.
- **Layered assembly.** Compose system, developer, retrieved-knowledge, history, and input as named
  segments with explicit order and boundaries.
- **Budgeted retrieval.** Allocate a fixed share of the window to retrieved knowledge; rank and
  trim to fit rather than injecting everything found.
- **History compaction.** Summarize or window prior interactions to a bounded size, preserving the
  decisions that matter while staying within budget.
- **Context capture.** Persist the assembled context (or a faithful digest) with each call for
  debugging, evaluation, and audit.
- **Progressive disclosure of tools.** Present only the tools relevant to the current step rather
  than the entire registry, reducing distraction and cost.

## 7. Anti-patterns

- **String-concatenation prompts.** Assembling context from inline literals at call sites, with no
  version, owner, or review — behavior cannot be reasoned about or reproduced.
- **Unbounded context.** Injecting all available history or retrieved documents until the window
  overflows unpredictably, causing silent truncation of whatever happens to be last.
- **Trust inversion.** Letting user input override system-layer constraints because the layers were
  concatenated without separation (also a security failure — see agentic security).
- **Copy-paste prompt drift.** The same prompt duplicated across agents, edited independently, with
  no single owner — the context analogue of duplicated code.
- **Untested prompt changes.** Editing a prompt directly in the active path without evaluation, then
  discovering the behavioral regression in production.
- **Context bloat.** Padding context with "just in case" material that raises cost and latency and
  degrades the model's focus.

## 8. Best Practices

- Keep prompts in a versioned library with one owner each; reference them by identity.
- Declare an explicit context budget per assembly and a defined overflow behavior per consumer.
- Separate the trust layers structurally; never let a lower layer silently override a higher one.
- Capture the assembled context for every call and link it to the response and the versions used.
- Gate prompt and assembly changes behind evaluation, as a peer to code review.
- Prefer least context; measure the cost and latency of what you include.
- Treat retrieval results as untrusted input to be bounded and framed, not as authoritative
  instructions.

## 9. Examples

*Illustrative and technology-neutral; no runnable code.*

- **A support agent's assembly** allocates its window as: system layer (fixed), developer task
  instructions (fixed), retrieved knowledge (ranked, capped at a set share), recent history
  (compacted to a bound), and the current message — with headroom reserved for the response. When
  retrieved knowledge exceeds its share, the lowest-ranked items are dropped, not the history.
- **A prompt promotion** moves a revised system prompt from draft to active only after it passes the
  agent's evaluation suite; the prior version is retained and the change is traceable to its
  evaluation result.
- **A context record** for a call shows exactly which prompt versions, which retrieved items, and how
  much history were present — turning a "why did the agent do that?" question into an inspection.

## 10. Checklist

- [ ] Every prompt is versioned, owned, and referenced by identity (no inline literals).
- [ ] Context assembly is a distinct, deterministic, inspectable stage.
- [ ] Trust layers (system / developer / input) are structurally separated.
- [ ] Each assembly has an explicit context budget and a defined overflow behavior.
- [ ] Assembled context is captured and linked to the response and versions used.
- [ ] Prompt/assembly changes are gated behind evaluation.
- [ ] The least-context principle is applied; included material earns its cost.
- [ ] No vendor, model, or technology is named in the context-engineering design.

## 11. References

- Development Methodology — Specification-Driven Development, which prompts and assemblies extend to
  behavior.
- Provider Platform — the model abstraction that supplies the window and tokenization boundary.
- Data Platform — retrieval and knowledge sourcing consumed by assembly.
- Evaluation — the behavioral-quality gate that context changes must pass.
- Runtime Platform — the execution of model calls the assembled context feeds.
- Builder Platform — the authoring experience through which builders supply the developer layer.

## 12. Summary

Context is the agent's executable specification, and prompts are its authored source. Context
engineering makes both first-class: versioned artifacts, a deterministic and inspectable assembly
stage, explicit trust layers, and a managed context budget, with every change validated by
evaluation. A platform that engineers its context deliberately can reason about, review, and improve
its agents' behavior; one that assembles context ad hoc cannot. This discipline is the foundation on
which tool use, orchestration, and memory build.
