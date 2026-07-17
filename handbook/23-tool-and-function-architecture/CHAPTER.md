# Chapter 23 — Tool & Function Architecture

## 1. Introduction

An agent that can only produce text is an advisor; an agent that can **act** is a system with
consequences. Agents act through **tools** — the functions, capabilities, and integrations they may
invoke to retrieve information or change the world. Tool use is where an agent platform crosses from
generating language to taking actions that cost money, mutate data, send messages, and touch other
systems.

**Tool architecture** is the discipline of defining what an agent may do, under what authority, with
what safeguards, and with what guarantees when an action fails or must be undone. It is the point in
an agent platform where correctness and safety matter most, because a mistaken action is not a
mis-phrased sentence — it is a real effect. This chapter defines tools as governed contracts,
permissioned and bounded, with side effects treated as first-class engineering concerns.

## 2. Objectives

- Define the **tool** and the **tool contract** as governed, versioned artifacts.
- Establish **permissioning** so an agent can invoke only what it is authorized to.
- Make **side effects** explicit and governed, including reversibility and human approval.
- Define safe **execution** and **result handling** for tool calls.
- Connect tool architecture to the runtime, the control plane, and security.

## 3. Concepts

This chapter **owns** the following concepts.

**Tool.** A discrete capability an agent may invoke to observe or change state — a function,
integration, or platform capability exposed to the agent under governance. A tool is not arbitrary
code the agent writes; it is a declared, bounded action the platform offers.

**Tool contract.** The declared interface of a tool: its purpose, inputs and their constraints, its
outputs, its side effects, its authority requirements, and its failure modes. The contract is what
the agent reasons over and what the platform enforces.

**Tool registry.** The governed catalog of available tools, versioned and owned, from which an agent
is granted a scoped subset.

**Tool permissioning.** The authorization model that determines which tools an agent (acting for a
principal) may invoke, and under what conditions — the least-privilege boundary around action.

**Side-effect class.** The classification of a tool by the consequence of invoking it: **read-only**
(no state change), **reversible** (state change that can be undone), and **irreversible /
high-consequence** (state change that cannot be undone, moves value, or is externally visible). The
class determines the safeguards required.

**Human-in-the-loop approval.** A required checkpoint where a person authorizes an action before a
tool of a given side-effect class executes.

**Action reversibility.** The property, and the platform mechanism, by which a tool's effect can be
compensated or rolled back; where reversibility is impossible, the action is gated instead.

Concepts referenced but **owned elsewhere**: the **plugin/extension contract** and lifecycle (Plugin
Platform); the **provider abstraction** (Provider Platform); **orchestration** and administration
(Control Plane); **API contracts and the edge** (API Platform); **identity, authorization, and
isolation** (Security); the **runtime** that executes calls (Runtime Platform).

## 4. Principles

1. **Tools are contracts, not free code.** An agent invokes declared, bounded tools; it does not
   execute arbitrary unreviewed actions.
2. **Least privilege for action.** An agent is granted the smallest set of tools its task requires,
   scoped to the principal it acts for.
3. **Side effects are first-class.** Every tool declares its side-effect class; the platform applies
   safeguards by class, not by trust in the agent.
4. **Consequence gates behavior.** The higher the consequence, the stronger the control — approval,
   confirmation, or prohibition for irreversible actions.
5. **Prefer reversibility.** Design actions to be undoable where possible; where not, gate them
   explicitly rather than hoping they succeed.
6. **Fail safe and observable.** A failed or ambiguous tool call defaults to no effect, and every
   invocation is recorded with its inputs, authority, and outcome.

## 5. Architecture

Tool use is mediated, never direct. A reference arrangement places a governed boundary between the
agent's intent and the tool's effect:

- **Tool registry** — the versioned catalog of tool contracts, each with an owner and a side-effect
  class.
- **Grant** — the scoped subset of tools an agent holds for a task, derived from the principal's
  authorization (least privilege).
- **Invocation mediator** — the component that receives a proposed tool call, validates it against the
  contract, checks the grant and authority, applies the side-effect-class safeguards (including
  human-in-the-loop for high-consequence classes), executes via the runtime, and returns a framed
  result.
- **Effect log** — the record of every invocation: tool and version, inputs, deciding authority,
  approval if required, outcome, and compensation if reversed — feeding observability, evaluation,
  and audit.

The mediator depends on the Control Plane for authority, on Security for identity and isolation, and
on the Runtime Platform for execution; it prescribes no specific integration technology. Tools that
wrap external systems are defined against the API Platform's contracts and may be delivered through
the Plugin Platform's extension model.

## 6. Patterns

- **Contract-first tools.** Define the tool contract (purpose, inputs, side effects, authority,
  failures) before implementation; the agent reasons over the contract.
- **Scoped grants.** Issue an agent only the tools its task needs, bound to the acting principal.
- **Side-effect tiering.** Route read-only tools freely, reversible tools with logging, and
  irreversible/high-consequence tools through approval or prohibition.
- **Confirm-before-act.** For high-consequence tools, require an explicit human approval step that
  states exactly what will happen.
- **Idempotent actions.** Design mutating tools to be safely retriable, so recovery does not
  double-apply effects.
- **Compensating actions.** Pair a reversible tool with the action that undoes it, enabling rollback.
- **Result framing.** Return tool outputs as bounded, typed, clearly-attributed results — never as
  trusted instructions to the agent.

## 7. Anti-patterns

- **Unbounded tool access.** Granting an agent the entire registry regardless of task, maximizing
  blast radius.
- **Undeclared side effects.** A tool whose contract hides that it mutates or transmits state, so no
  safeguard is applied.
- **Irreversible-by-default.** Exposing high-consequence actions with no approval, confirmation, or
  compensation.
- **Result-as-instruction.** Treating a tool's returned content as commands the agent must follow,
  turning a compromised or malformed result into control (also an injection vector — see agentic
  security).
- **Retry without idempotency.** Re-invoking a failed mutating tool and applying the effect twice.
- **Silent failure.** A tool call that fails without a recorded, safe outcome, leaving state and the
  agent's understanding inconsistent.

## 8. Best Practices

- Keep tools in a versioned, owned registry; declare a side-effect class for each.
- Grant tools by least privilege, scoped to the acting principal and the task.
- Require human-in-the-loop approval for irreversible or high-consequence actions, with the effect
  stated plainly.
- Make mutating tools idempotent and, where possible, provide compensating actions.
- Log every invocation with inputs, authority, approval, and outcome.
- Frame tool results as untrusted, bounded data — never as instructions.
- Default to no effect on failure or ambiguity.

## 9. Examples

*Illustrative and technology-neutral; no runnable code.*

- **A tiered toolset.** An agent holds a read-only search tool (invoked freely and logged), a
  reversible "draft a record" tool (invoked with logging and undoable), and an irreversible "send an
  external message" tool (routed through human approval that shows the recipient and content before
  sending).
- **A confirm-before-act flow.** When the agent proposes the irreversible action, the platform pauses
  and presents the exact effect to a person; only on approval does the mediator execute, recording who
  approved.
- **A compensated action.** A "reserve capacity" tool is paired with a "release reservation"
  compensation; if the surrounding task fails, the platform reverses the reservation and logs it.

## 10. Checklist

- [ ] Every tool has a versioned, owned contract declaring inputs, outputs, side effects, and authority.
- [ ] Each tool is assigned a side-effect class (read-only / reversible / irreversible).
- [ ] Agents receive least-privilege, principal-scoped tool grants.
- [ ] Irreversible / high-consequence tools require human-in-the-loop approval.
- [ ] Mutating tools are idempotent; reversible tools have compensating actions where feasible.
- [ ] Every invocation is logged with inputs, authority, approval, and outcome.
- [ ] Tool results are framed as untrusted data, never as instructions.
- [ ] Failure and ambiguity default to no effect.

## 11. References

- Plugin Platform — the extension contract and lifecycle through which many tools are delivered.
- Control Plane — the authority, configuration, and administration tool grants derive from.
- Security — identity, authorization, and isolation that bound tool execution.
- API Platform — the contracts external-system tools are defined against.
- Runtime Platform — the execution of tool calls and their failure handling.
- Provider Platform — the model abstraction that proposes tool calls from context.

## 12. Summary

Tools are where agents act, and action has consequences, so tool architecture governs *what* an agent
may do rather than trusting *how* it decides. Tools are declared contracts, granted by least
privilege, classified by side effect, and mediated so that read-only actions flow freely while
irreversible ones are gated by human approval or made reversible. Every invocation is logged and
fails safe. Engineered this way, an acting agent is powerful without being dangerous; engineered
carelessly, it is a system that takes real, unreviewed actions on the world.
