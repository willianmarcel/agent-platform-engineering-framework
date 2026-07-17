# Agentic Security

> **Proposed chapter (P1 — Agentic Core).** Authored to Handbook standard; not yet integrated into
> the frozen Handbook numbering or Knowledge Graph. **Extends, and does not duplicate, the Security
> chapter**, which owns threat model, identity, and isolation. This chapter owns the *agent-specific*
> threat and control concepts defined below.

## 1. Introduction

Classical application security assumes the program's instructions are trusted and its inputs are
data. An agent platform breaks that assumption: the agent's instructions and its data arrive in the
**same channel** — the context — and the agent acts on both through tools. A document it retrieves, a
web page it reads, a tool result it receives, or a message from another agent can carry text that the
model treats as instruction. The attacker no longer needs to breach the system; they only need their
content to enter the agent's context.

**Agentic security** is the discipline of defending a system whose control flow is influenced by
untrusted natural-language content and whose actions have real effect. It addresses threats that
classical security does not fully cover — indirect prompt injection, tool abuse, memory
exfiltration, and unsafe autonomy — and it treats the agent's autonomy itself as something to be
bounded. This chapter defines those threats and the controls against them, building on the Security
chapter's identity, isolation, and threat-model foundations.

## 2. Objectives

- Define the **agentic threat surface** and how it differs from classical application security.
- Establish **prompt injection** (direct and indirect) as the central threat and its defenses.
- Define **guardrails** on inputs and outputs, and **autonomy levels** as a safety control.
- Make the **human-in-the-loop boundary** and **reversibility** first-class safety mechanisms.
- Connect agentic security to the tool, context, memory, and evaluation disciplines.

## 3. Concepts

This chapter **owns** the following concepts.

**Agentic threat surface.** The set of ways an adversary can influence an agent's behavior or exfiltrate
value through the agent — spanning its context sources, its tools, its memory, and its coordination —
because the agent acts on untrusted natural-language content.

**Prompt injection.** An attack in which untrusted content entering the context is interpreted by the
model as instruction. **Direct** injection comes through the user input; **indirect** injection is
carried by content the agent retrieves or a tool returns — the more dangerous form, because the user
may be the victim rather than the attacker.

**Jailbreak.** Input crafted to make the agent bypass its own constraints or safety instructions.

**Guardrail.** A control that inspects and constrains what enters or leaves the agent — an **input
guardrail** screens context and tool results before the model acts on them; an **output guardrail**
screens the agent's responses and proposed actions before they take effect.

**Autonomy level.** The declared degree of independent action an agent is permitted, from
suggest-only, through act-with-approval, to act-autonomously-within-bounds — an explicit architectural
decision, not an implicit default.

**Human-in-the-loop safety boundary.** The line at which a consequential action requires human
authorization before it executes, determined by the action's consequence and the agent's autonomy
level.

**Least-authority agent.** The application of least privilege to an agent's identity, tools, context
scope, and memory scope, so a compromised or misled agent has minimal reach.

Concepts referenced but **owned elsewhere**: the **threat model, identity, and isolation** (Security);
**tool contracts, side-effect classes, and permissioning** (Tool & Function Architecture); **context
assembly and trust layers** (Context & Prompt Engineering); **memory scope** (Memory & Conversational
State); **evaluation** as the measure of control effectiveness (Evaluation).

## 4. Principles

1. **All model-facing content is untrusted.** Retrieved documents, tool results, and inter-agent
   messages are data to be screened, never instructions to be obeyed.
2. **Instructions and data are separated by trust.** Higher-trust system instructions are structurally
   distinguished from lower-trust content; lower trust never overrides higher.
3. **Autonomy is bounded by consequence.** The greater an action's consequence, the lower the autonomy
   permitted without a human; irreversible actions default to human authorization.
4. **Least authority everywhere.** An agent's identity, tools, context, and memory are all
   least-privilege, so compromise has minimal blast radius.
5. **Defense in depth.** Injection defense, guardrails, least authority, human-in-the-loop, and
   reversibility layer; no single control is trusted alone.
6. **Controls are measured, not assumed.** Guardrails and autonomy bounds are evaluated against
   adversarial cases, because their effectiveness cannot be assumed.

## 5. Architecture

Agentic security places controls at every point where untrusted content or consequential action
crosses a boundary:

- **Input guardrail** — screens retrieved knowledge, tool results, and inter-agent messages before
  they enter the model's working context, framing them as data and detecting injection.
- **Trust-layered context** — keeps system instructions structurally separated from lower-trust
  content (from Context & Prompt Engineering), so injected text cannot masquerade as policy.
- **Output guardrail** — screens the agent's responses and *proposed actions* before they take effect,
  blocking unsafe output and disallowed actions.
- **Autonomy policy** — declares, per agent and action class, the permitted autonomy level and where
  the human-in-the-loop boundary sits.
- **Least-authority envelope** — the agent's scoped identity, tool grant, context scope, and memory
  scope (from Security, Tool, and Memory disciplines), bounding reach.
- **Security trace** — records screened content, guardrail decisions, approvals, and actions for
  detection, evaluation, and audit.

These controls extend the Security chapter's identity and isolation; they do not replace them. The
tool mediator enforces the autonomy boundary at the point of action; the context assembler enforces
trust layering at the point of reasoning.

## 6. Patterns

- **Untrusted-content framing.** Wrap all retrieved and tool-returned content as clearly-delimited
  data, never merged into the instruction layers.
- **Injection screening.** Inspect incoming content for instruction-like payloads before the agent
  acts on it, especially for indirect sources.
- **Action allowlist by autonomy level.** Permit only the action classes the agent's autonomy level
  allows; route the rest to human authorization or deny.
- **Confirm irreversible actions.** Require human authorization at the safety boundary for
  irreversible or high-consequence actions, showing the exact effect (shared with Tool architecture).
- **Output filtering.** Screen responses for leaked secrets, disallowed content, or unsafe proposed
  actions before they leave the agent.
- **Blast-radius minimization.** Grant least authority across identity, tools, context, and memory so
  a successful injection achieves little.

## 7. Anti-patterns

- **Trusting retrieved or tool content.** Treating a document's or tool's text as instruction — the
  root of indirect injection.
- **Concatenated trust.** Merging user input and retrieved content into the system instructions with
  no separation, so injection overrides policy.
- **Unbounded autonomy.** Letting an agent take consequential, irreversible actions with no autonomy
  level and no human boundary.
- **Over-privileged agents.** Broad identity, full tool access, and unscoped memory, maximizing the
  damage of any compromise.
- **Guardrails as afterthought.** Adding input/output screening late, untested against adversarial
  cases, and assuming it works.
- **Silent action.** Consequential actions taken without a security trace, leaving compromise
  undetectable.

## 8. Best Practices

- Treat every retrieved document, tool result, and inter-agent message as untrusted data; frame and
  screen it before the agent acts.
- Keep system instructions structurally separated from lower-trust content.
- Declare an autonomy level per agent and action class; place irreversible actions behind the
  human-in-the-loop boundary.
- Apply least authority to identity, tools, context, and memory alike.
- Screen outputs and proposed actions with output guardrails.
- Evaluate guardrails and autonomy bounds against adversarial and red-team cases; record a security
  trace.

## 9. Examples

*Illustrative and technology-neutral; no runnable code.*

- **Indirect injection defense.** An agent summarizing a retrieved document encounters embedded text
  instructing it to send data to a third party. Because retrieved content is framed as untrusted data
  and screened by the input guardrail, the instruction is treated as content to summarize, not a
  command — and the "send" action is outside the agent's tool grant regardless.
- **Autonomy boundary.** A support agent may answer freely and draft changes autonomously, but issuing
  a refund crosses the human-in-the-loop boundary: the platform pauses, shows the amount and
  recipient, and executes only on approval.
- **Blast-radius minimization.** An agent compromised by a jailbreak holds only a read-only toolset and
  a session-scoped memory, so the attack yields no irreversible action and no access to another user's
  data.

## 10. Checklist

- [ ] All retrieved content, tool results, and inter-agent messages are treated as untrusted and
  screened before the agent acts.
- [ ] System instructions are structurally separated from lower-trust content.
- [ ] Each agent has a declared autonomy level; irreversible actions sit behind the human-in-the-loop
  boundary.
- [ ] Least authority is applied to identity, tools, context, and memory.
- [ ] Input and output guardrails are in place and evaluated against adversarial cases.
- [ ] A security trace records screened content, guardrail decisions, approvals, and actions.
- [ ] No consequential action executes without its autonomy and boundary checks.

## 11. References

- Security — threat model, identity, isolation (the foundation this chapter extends).
- Tool & Function Architecture — side-effect classes, permissioning, and the action boundary.
- Context & Prompt Engineering — trust layering and untrusted-content framing.
- Memory & Conversational State — memory scope and exfiltration boundaries.
- Evaluation — adversarial evaluation of guardrails and autonomy bounds.

## 12. Summary

An agent acts on untrusted natural language through tools that have real effect, so its instructions
and its data share a channel and its autonomy is itself a risk. Agentic security treats all
model-facing content as untrusted, separates instructions from data by trust, bounds autonomy by
consequence with a human-in-the-loop boundary for irreversible action, applies least authority across
identity, tools, context, and memory, and layers input/output guardrails — all measured against
adversarial cases, not assumed. It extends the platform's identity and isolation to the agent-specific
threat surface. Without this discipline, a retrieved document can hijack an agent; with it, the agent
is powerful, bounded, and safe.
