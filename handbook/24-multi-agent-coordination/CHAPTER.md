# Chapter 24 — Multi-Agent Coordination

## 1. Introduction

Some problems exceed what a single agent should handle: they span distinct skills, require separation
of concerns, or benefit from division of labor and independent review. A **multi-agent system**
decomposes such a problem across several agents that coordinate to solve it together.

Multi-agent coordination is powerful and, if undisciplined, unpredictable. More agents mean more
interactions, more places for context to be lost, more ways for control to loop or stall, and more
cost. **Multi-agent coordination** is the discipline of deciding when to use multiple agents, how to
divide responsibility among them, how they hand work to one another, and how the whole reaches a
result and stops. This chapter defines the coordination topologies and the contracts between agents,
building on the general orchestration and runtime concepts the platform already owns.

## 2. Objectives

- Establish criteria for **when** a multi-agent design is warranted over a single agent.
- Define **agent roles** and the **coordination topologies** (single, supervised, networked).
- Define the **handoff** and the **agent-to-agent contract** by which agents exchange work.
- Make **termination** and **convergence** explicit so multi-agent systems reliably finish.
- Connect coordination to the Control Plane's orchestration and the Runtime Platform's execution.

## 3. Concepts

This chapter **owns** the following concepts.

**Multi-agent system.** A design in which several agents, each with a bounded responsibility,
coordinate to accomplish a task no one of them owns alone.

**Agent role.** The bounded responsibility, granted tools, and context an agent holds within a
coordination — its specialization and its limits.

**Coordination topology.** The shape of control and communication among agents. Canonical topologies:
**single** (one agent, no coordination), **supervised** (a coordinating agent delegates to and
integrates specialized agents), and **networked** (peers hand work directly to one another under a
protocol).

**Supervisor pattern.** A supervised topology in which one agent owns the goal, decomposes it,
delegates subtasks to specialized agents, and integrates their results — the coordinator of record.

**Handoff.** The transfer of a unit of work from one agent to another, carrying the context, the
task, and the authority required, and returning a bounded result.

**Agent-to-agent contract.** The declared interface of a handoff: what is passed, what is expected
back, what authority transfers, and what happens on failure — the coordination analogue of a tool
contract.

**Convergence and termination.** The conditions under which a coordination reaches a result and
stops, and the guarantees (a bound on steps, a decision on disagreement) that prevent loops and
stalls.

Concepts referenced but **owned elsewhere**: **orchestration**, configuration, and administration
(Control Plane); the **runtime lifecycle**, concurrency, and failure handling (Runtime Platform);
the **tool contract** and permissioning (Tool & Function Architecture); **context assembly** across
a handoff (Context & Prompt Engineering); the **authoring experience** for composing agents (Builder
Platform).

## 4. Principles

1. **Prefer one agent.** Introduce multiple agents only when a single agent genuinely cannot meet the
   need; coordination is a cost paid for a reason.
2. **Bound every role.** Each agent has a clear responsibility, a least-privilege toolset, and a
   defined context; no agent is a catch-all.
3. **Handoffs are contracts.** Work transfers through declared agent-to-agent contracts, not implicit
   shared mutable state.
4. **Coordination must terminate.** Every multi-agent design has an explicit step bound, a convergence
   condition, and a decision rule for disagreement.
5. **Authority travels explicitly.** A handoff transfers only the authority the receiving agent needs,
   and returns it; delegation does not silently escalate privilege.
6. **Observability spans the coordination.** The path of a task across agents is traceable end to end,
   not a set of disconnected calls.

## 5. Architecture

Multi-agent coordination is built on the platform's existing orchestration and runtime, adding the
agent-to-agent boundary:

- **Roles** — the catalog of agent roles, each with its responsibility, granted tools, and context
  scope.
- **Coordinator** — in a supervised topology, the agent (or orchestration policy owned by the Control
  Plane) that decomposes the goal, selects roles, issues handoffs, and integrates results.
- **Handoff channel** — the mediated transfer of work between agents that enforces the agent-to-agent
  contract, moves the required context and authority, and records the exchange.
- **Convergence control** — the mechanism enforcing the step bound, detecting completion or stall, and
  applying the disagreement decision rule.
- **Coordination trace** — the end-to-end record linking each agent's contribution to the overall
  task, feeding observability and evaluation.

The coordinator relies on the Control Plane for orchestration policy and on the Runtime Platform for
concurrent execution, lifecycle, and failure handling; this chapter adds only the agent-to-agent
contract and the coordination guarantees on top. No specific framework or technology is prescribed.

## 6. Patterns

- **Single-agent-first.** Start with one agent and decompose only when a bounded, named reason
  demands it.
- **Supervisor–specialist.** A coordinator owns the goal and delegates to specialists with narrow
  roles, integrating their bounded results.
- **Sequential handoff.** Agents pass work along a defined pipeline, each transforming and forwarding
  under a contract.
- **Bounded delegation.** A handoff carries a step and scope limit so a delegated subtask cannot
  expand without return.
- **Adjudicated disagreement.** When agents conflict, a defined rule (a deciding role, a vote, an
  escalation) resolves it rather than looping.
- **Shared context by reference.** Agents share context through governed references, not by mutating a
  common blob, preserving each role's bounded view.

## 7. Anti-patterns

- **Multi-agent by default.** Splitting a task across agents when one would do, paying coordination
  cost for no benefit.
- **Unbounded coordination.** No step limit or convergence condition, so agents loop, ping-pong, or
  stall.
- **Implicit shared state.** Agents coordinating through a mutable common blob, so responsibility and
  context ownership blur.
- **Authority creep.** A handoff that grants the receiving agent more privilege than its subtask
  needs, widening blast radius with each delegation.
- **Lossy handoff.** Transferring work without the context or the return contract, so the receiving
  agent guesses and the result cannot be integrated.
- **Untraceable coordination.** A web of agent calls with no end-to-end trace, making failures
  undiagnosable.

## 8. Best Practices

- Justify every multi-agent design against a single-agent baseline.
- Give each agent a bounded role, least-privilege tools, and a defined context scope.
- Transfer work through declared agent-to-agent contracts with explicit authority and return.
- Enforce a step bound, a convergence condition, and a disagreement decision rule.
- Trace tasks end to end across agents.
- Share context by governed reference, not shared mutable state.

## 9. Examples

*Illustrative and technology-neutral; no runnable code.*

- **A supervised research task.** A coordinator decomposes a question into sub-questions, hands each
  to a specialist agent with a read-only toolset and a bounded context, then integrates the returned
  findings — with a step bound so the coordination cannot expand indefinitely.
- **A sequential pipeline.** A drafting agent hands its output to a reviewing agent under a contract
  that specifies what is passed and what critique is expected back; a third agent finalizes only after
  the review returns.
- **An adjudicated conflict.** Two specialist agents return incompatible recommendations; a defined
  deciding role resolves the conflict per the disagreement rule, and the resolution is recorded in the
  coordination trace.

## 10. Checklist

- [ ] The multi-agent design is justified against a single-agent baseline.
- [ ] Each agent has a bounded role, least-privilege tools, and a defined context scope.
- [ ] Work transfers through declared agent-to-agent contracts with explicit authority and return.
- [ ] The coordination has a step bound, a convergence condition, and a disagreement decision rule.
- [ ] Authority does not escalate silently across handoffs.
- [ ] The task is traceable end to end across all agents.
- [ ] Agents share context by reference, not mutable shared state.

## 11. References

- Control Plane — orchestration, configuration, and administration, which multi-agent coordination
  builds upon.
- Runtime Platform — the lifecycle, concurrency, and failure handling that execute coordinated agents.
- Tool & Function Architecture — the tool contracts and grants each agent role holds.
- Context & Prompt Engineering — the context assembled and transferred across handoffs.
- Builder Platform — the authoring experience for composing multi-agent designs.

## 12. Summary

Multiple agents are a deliberate response to problems a single agent cannot bound — not a default.
Coordination is designed as roles with bounded responsibility, handoffs governed by agent-to-agent
contracts, and explicit guarantees of convergence and termination, all built on the orchestration and
runtime the platform already owns. Disciplined this way, a multi-agent system divides labor without
losing control; undisciplined, it multiplies cost, loses context, and loops. The test of a good
multi-agent design is that it terminates, stays traceable, and earns the coordination it pays for.
