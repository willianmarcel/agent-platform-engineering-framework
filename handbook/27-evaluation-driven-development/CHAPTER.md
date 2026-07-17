# Chapter 27 — Evaluation-Driven Development

## 1. Introduction

Specification-Driven Development (Chapter 04) is the framework's methodology spine: intent is
specified before it is built, and the specification is the contract the work must satisfy. That
contract works because conventional software is deterministic — given the same input, the same code
produces the same output, and a test can assert it.

Agentic behavior breaks that assumption. A model-backed agent is **non-deterministic** and
**model-dependent**: the same input can produce different outputs, and behavior shifts when the
underlying model, the context, the tools, or the prompts change. A specification can still state what
*should* happen, but it cannot, by itself, verify what a probabilistic system *does* happen. Asserting
one exact output is neither possible nor meaningful.

**Evaluation-Driven Development (EDD)** is the methodology that answers this. It makes evaluation a
peer of specification: for agentic behavior, the intended behavior is captured as an **evaluation
suite** authored alongside the specification, and a change is accepted only when it passes that
evaluation. Where SDD asks "is the built thing what we specified?", EDD asks "does the probabilistic
thing behave as we require, measured over cases, and did this change make it better or worse?" This
chapter defines EDD and how it composes with SDD to make non-determinism an engineered, gated
property rather than a hope.

## 2. Objectives

- Establish **Evaluation-Driven Development** as the peer of Specification-Driven Development for
  non-deterministic, model-dependent behavior.
- Define the **evaluation-first workflow**: behavior specified and evaluated together, before change.
- Define **behavioral acceptance criteria** and the **behavioral regression gate**.
- Position EDD relative to specification (Ch 04), evaluation mechanisms (Ch 16), and testing (Ch 18).
- Make EDD the standing methodology behind the agentic disciplines (Ch 22–26).

## 3. Concepts

This chapter **owns** the following concepts.

**Evaluation-Driven Development.** The methodology in which the intended behavior of a
non-deterministic capability is expressed as evaluation and authored alongside its specification, and
in which every change to that capability is validated against evaluation before it is accepted. It is
the peer of Specification-Driven Development for behavior that cannot be asserted deterministically.

**Evaluation-first workflow.** The practice of authoring the evaluation of intended behavior *together
with* the specification, before the behavior is built or changed — so acceptance is defined in
measurable terms from the outset, not retrofitted.

**Behavioral acceptance criteria.** The measurable, evaluation-expressed conditions a non-deterministic
capability must meet to be considered correct — stated over a population of cases and thresholds
rather than a single exact output.

**Behavioral regression gate.** A quality gate that blocks a change to a prompt, context assembly,
tool set, memory policy, coordination, or model until the capability's evaluation suite passes at or
above its established baseline — the guard against silent behavioral regression.

**Behavioral baseline.** The recorded evaluation result a capability currently achieves, against which
a proposed change is compared to determine improvement or regression.

Concepts referenced but **owned elsewhere**: **Specification-Driven Development** and the development
methodology (Development Methodology, Ch 04); the **evaluation** of AI systems — metrics, methods,
continuous evaluation (Evaluation, Ch 16); **testing** of deterministic behavior (Testing, Ch 18); the
**context, tool, coordination, and memory** changes EDD gates (Ch 22–25); the **quality gates** EDD
extends (Execution and framework-authoring gate sets).

## 4. Principles

1. **Specify and evaluate together.** For non-deterministic behavior, the evaluation is authored with
   the specification, not after it; acceptance is measurable from the start.
2. **Behavior is judged over cases, not instances.** Correctness is a distribution over a representative
   set, with thresholds — never a single asserted output.
3. **No change without evaluation.** A change to anything that shapes behavior passes the behavioral
   regression gate before it is accepted.
4. **Compare to a baseline.** Every change is measured against the current behavioral baseline;
   improvement and regression are explicit.
5. **Evaluation is a first-class artifact.** Evaluation suites are owned, versioned, and maintained
   like specifications and code, not disposable scripts.
6. **EDD complements, not replaces, SDD and testing.** Specifications still capture intent;
   deterministic parts are still tested; EDD governs the probabilistic behavior between them.

## 5. Architecture

EDD is a methodology layered onto the existing specification, evaluation, and quality-gate machinery;
it adds a discipline, not a new subsystem:

- **Paired artifacts** — a capability's specification (owned by SDD/Ch 04) and its evaluation suite
  (built on the mechanisms of Ch 16) are authored and versioned together.
- **Behavioral baseline** — the recorded evaluation result the capability currently achieves.
- **Behavioral regression gate** — a gate in the workflow that runs the evaluation suite on a proposed
  change and blocks acceptance unless it meets or exceeds the baseline and the acceptance criteria.
- **Promotion path** — a change to a prompt, context assembly, tool set, memory policy, or model moves
  from proposed to active only through the gate, updating the baseline on acceptance.

The evaluation *mechanisms* (datasets, judging methods, metrics, continuous evaluation) remain owned by
Chapter 16; EDD defines *when and why* they gate change and how they pair with specification. The gate
itself is registered in the quality-gate sets, alongside the framework's other gates. No technology is
prescribed.

## 6. Patterns

- **Spec-plus-eval.** Deliver every agentic capability as a specification and an evaluation suite
  together; neither is complete alone.
- **Gate the behavior-shaping change.** Route changes to prompts, context, tools, memory, coordination,
  and model version through the behavioral regression gate.
- **Baseline and compare.** Record the current evaluation result; accept a change only if it holds or
  improves the baseline.
- **Adversarial cases in the suite.** Include injection, edge, and failure cases (especially for tools
  and security) so the gate measures safety, not just happy-path quality.
- **Continuous re-evaluation.** Re-run evaluation when the underlying model changes, since behavior can
  shift with no change to the platform's own artifacts.

## 7. Anti-patterns

- **Assert-one-output.** Testing a probabilistic capability by asserting a single exact response —
  brittle and meaningless.
- **Evaluate-after.** Building behavior first and inventing evaluation later, so acceptance is
  retrofitted to whatever the system already does.
- **Ungated change.** Editing a prompt, tool, or model in the active path with no evaluation, then
  discovering the regression in production.
- **Disposable evals.** One-off evaluation scripts that are not owned, versioned, or maintained, so the
  gate rots.
- **Happy-path-only suites.** Evaluation that omits adversarial and failure cases, so the gate passes
  while the capability is unsafe.
- **Baseline blindness.** Accepting changes with no recorded baseline, so improvement and regression are
  invisible.

## 8. Best Practices

- Author the evaluation suite with the specification, before building or changing behavior.
- Express acceptance as behavioral criteria over a representative case set with thresholds.
- Put a behavioral regression gate in front of every behavior-shaping change; keep a recorded baseline.
- Include adversarial and failure cases, especially for tool use and agentic security.
- Own and version evaluation suites as first-class artifacts.
- Re-evaluate on model change; treat the model as a dependency whose behavior can drift.

## 9. Examples

*Illustrative and technology-neutral; no runnable code.*

- **A gated prompt change.** A revised system prompt is proposed. The behavioral regression gate runs
  the capability's evaluation suite; the change is accepted only because it holds the baseline on core
  cases and improves two, and the new result becomes the baseline.
- **A model upgrade.** The underlying model version changes with no edit to the platform's prompts or
  tools. Continuous re-evaluation runs; the suite reveals a regression on a class of cases, and the
  upgrade is held until the context assembly is adjusted and re-gated.
- **A safety case in the suite.** An indirect-injection case (from agentic security) is part of the
  evaluation; a tool change that would have let injected content trigger an action fails the gate and
  is blocked before reaching production.

## 10. Checklist

- [ ] Each agentic capability has a specification and a paired, versioned evaluation suite.
- [ ] Behavioral acceptance criteria are expressed over cases with thresholds, not single outputs.
- [ ] A behavioral regression gate fronts every change to prompts, context, tools, memory,
  coordination, or model.
- [ ] A behavioral baseline is recorded and updated on accepted change.
- [ ] Evaluation suites include adversarial and failure cases.
- [ ] Capabilities are re-evaluated when the underlying model changes.
- [ ] EDD is applied alongside SDD (intent) and testing (deterministic parts), not instead of them.

## 11. References

- Development Methodology (Ch 04) — Specification-Driven Development, of which EDD is the peer.
- Evaluation (Ch 16) — the evaluation mechanisms EDD gates change with.
- Testing (Ch 18) — the testing of deterministic behavior EDD complements.
- Context & Prompt Engineering, Tool & Function Architecture, Multi-Agent Coordination, Memory &
  Conversational State (Ch 22–25) — the behavior-shaping changes EDD gates.
- Agentic Security (Ch 26) — the adversarial cases the evaluation suite must include.

## 12. Summary

Non-determinism is the defining engineering reality of agentic systems, and specification alone cannot
gate it. Evaluation-Driven Development makes evaluation a peer of specification: intended behavior is
captured as a versioned evaluation suite authored with the spec, and every change that shapes behavior
— prompt, context, tool, memory, coordination, or model — passes a behavioral regression gate against a
recorded baseline before it is accepted. EDD does not replace Specification-Driven Development or
testing; it completes them for the probabilistic behavior between them, and it is the standing
methodology behind the agentic disciplines. With it, agentic behavior is measured, gated, and
improved on evidence; without it, behavior changes are acts of faith.
