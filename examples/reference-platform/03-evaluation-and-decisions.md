# Reference Platform — Evaluation & Decisions

*Applies APEF steps 7–8 (measured quality → recorded decisions, Ch 16/27 and the ADR framework) to the
Support Operations Assistant Platform. Non-executable and technology-neutral.*

## Evaluation plan (steps 7, via EDD — Ch 16/27)

Because the assistant's behavior is non-deterministic, correctness is defined as **behavioral
acceptance criteria over a representative case set**, and every behavior-shaping change passes a
**behavioral regression gate** against a baseline before it ships.

### Behavioral acceptance criteria (illustrative)

| Dimension | Criterion (over the case set, with thresholds) |
|-----------|------------------------------------------------|
| Groundedness | Answers are supported by retrieved knowledge and cite it; unsupported claims below a set rate. |
| Policy compliance | The assistant answers/acts only within the tenant's policy; zero policy violations on the policy case set. |
| Safety (adversarial) | On the injection case set, no injected instruction changes behavior and no ungranted action is attempted — a **blocking** criterion. |
| Escalation correctness | Cases that policy or low confidence require to escalate are escalated; measured against a labeled set. |
| Draft quality | Drafts meet a rubric (tone, completeness) at or above baseline. |

### The gate

- A change to the system prompt, the context assembly, the toolset, the memory policy, the
  coordination, or the underlying model **runs the case set and must hold or improve the baseline**,
  with the safety criterion always passing, before it becomes active.
- The current result is the **baseline**; on acceptance the baseline is updated.
- The suite is **re-run when the model changes**, since behavior can drift with no platform change.

This is the [Evaluation dimension gate](../../execution/QUALITY_GATES.md) applied to a real platform.

## Significant decisions (step 8, as worked ADRs)

Recorded in the form of the [ADR framework](../../adrs/ADR_FRAMEWORK.md). These are *illustrative*
records for this instance, not framework ADRs.

### RD-01 — The assistant never sends to the customer
- **Decision:** Sending a customer-facing message is a human action; the assistant holds no send tool
  and can only draft.
- **Context:** Customer-visible messages are irreversible and high-consequence; the platform's promise
  is human control of anything customer-facing.
- **Rationale:** Removing the tool makes the unsafe action *structurally impossible* rather than merely
  guarded — the strongest control (Ch 23/26).
- **Consequences:** The human is always in the loop for sending; throughput depends on human review,
  accepted deliberately.

### RD-02 — Retrieved knowledge and case data are untrusted
- **Decision:** All retrieved and read content is framed as data and screened for injection before the
  assistant acts on it.
- **Context:** The assistant reads tenant knowledge and case records it does not control (Ch 26).
- **Rationale:** Indirect prompt injection is the central agentic threat; treating this content as
  instruction would let a poisoned document steer the assistant.
- **Consequences:** An input guardrail and trust-layered context are required; retrieved content can
  never change behavior, only inform answers.

### RD-03 — Single agent by default; supervisor only when specialization is needed
- **Decision:** Use one assistant agent by default; introduce a supervisor–specialist coordination only
  for questions needing specialized knowledge.
- **Context:** Multi-agent coordination adds cost, latency, and failure modes (Ch 24).
- **Rationale:** Coordination must earn its cost; most questions do not need it.
- **Consequences:** A justified, bounded coordination path exists but is the exception, with a step
  bound and non-escalating authority.

### RD-04 — Case content is read live, never remembered
- **Decision:** The platform holds a read model of cases and reads them live; it does not store case
  content in agent memory.
- **Context:** Cases are owned by the systems of record; case data is sensitive and changes (Ch 12/25).
- **Rationale:** Avoids stale and leaked case data; keeps the systems of record authoritative.
- **Consequences:** Every case reference is a live, tenant-scoped read; memory holds only curated
  preferences.

## What steps 7–8 produced

A measurable definition of "good" for a probabilistic system, gated on evidence with a blocking safety
criterion, and the platform's load-bearing decisions recorded with their rationale and consequences —
the same shape the framework prescribes, filled in.

## The whole instance, in one line

Vision and non-goals → four bounded contexts → the reference planes made specific → a layered context,
a least-privilege toolset without the dangerous tool, bounded coordination, scoped memory, and
defense-in-depth security → behavioral gates with a blocking safety criterion → recorded decisions.
That is what engineering a platform *with* APEF produces — [start the path here](../../GETTING_STARTED.md).
