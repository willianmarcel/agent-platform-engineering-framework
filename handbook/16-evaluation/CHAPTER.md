# Chapter 16 — Evaluation

## Introduction

This chapter defines evaluation as a cross-cutting capability of an AI Agent Platform: the
capability to measure the quality of the platform's AI. Its prerequisites are
[Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md) and
[Chapter 07 — Runtime Platform](../07-runtime-platform/CHAPTER.md), whose running agents and
workflows are the subject of measurement.

Evaluation and testing are distinct disciplines and are kept separate throughout the
Handbook: **evaluation measures the quality of AI** — behavior that is model-dependent and
not fully determined in advance — while **testing verifies software correctness**, which is
owned by [Chapter 18 — Testing](../18-testing/). This chapter defines evaluation as an
architectural capability — what is measured, by whom, and how quality is judged over time —
not any evaluation tool, dataset, or technology. No product is named and no implementation
is prescribed.

## Objectives

After reading this chapter, a reader will be able to:

- Explain evaluation as the measurement of AI quality, distinct from software testing.
- Distinguish agent, prompt, and quality evaluation.
- Reason about human and automated evaluation, benchmarking, and success metrics.
- Apply continuous and reliability evaluation across the platform's life.

## Concepts

This chapter **owns** the concepts below; other chapters reference them without redefining
them.

**AI Evaluation.** The measurement of the quality of AI behavior — output that is
model-dependent and not fully determined in advance. AI evaluation is this chapter's
subject and its defining boundary against software testing: it judges *how good* AI behavior
is, not whether software is *correct*.

**Agent Evaluation.** The evaluation of an agent's behavior against what it is meant to
achieve. Agent evaluation applies AI evaluation to the unit of the agent, judging the
quality of what an agent does.

**Prompt Evaluation.** The evaluation of the instruction assets that shape AI behavior,
judging how well they elicit the intended results. Prompt evaluation measures the quality of
prompt assets (owned, as design-time artifacts, by
[Chapter 08](../08-builder-platform/CHAPTER.md)); it does not author them.

**Quality Evaluation.** The evaluation of AI output against defined dimensions of quality —
such as correctness of judgment, relevance, and safety of behavior — appropriate to the
task. Quality evaluation is how "good" is made specific for a given kind of work.

**Human Evaluation.** Evaluation performed by people, applying judgment that automation
cannot. Human evaluation is essential where quality is subjective, contextual, or novel.

**Automated Evaluation.** Evaluation performed by the platform without human judgment in the
loop, applying defined criteria at scale. Human and automated evaluation are complementary:
automation gives reach and repeatability; human evaluation gives judgment.

**Benchmarking.** The evaluation of AI behavior against a defined, stable reference so that
results can be compared across time, versions, or approaches. Benchmarking is how evaluation
yields comparable, durable measures.

**Success Metrics.** The defined measures by which the quality of AI is judged successful.
Success metrics operationalize evaluation; they measure the outcomes owned, at the vision
level, by [Chapter 01](../01-platform-vision/CHAPTER.md) and, as product value, by
[Chapter 02](../02-product-thinking/CHAPTER.md).

**Continuous Evaluation.** Evaluation performed continually over the platform's life, rather
than only at a point in time, so that quality is tracked and regressions are caught as
behavior and models change. Continuous evaluation is how quality is sustained, not merely
established.

**Reliability Evaluation.** The evaluation of how consistently AI behavior meets its quality
standard across varied inputs and conditions. Reliability evaluation judges dependability of
AI behavior, distinct from the architectural reliability owned by
[Chapter 06](../06-reference-architecture/CHAPTER.md).

**Evaluation Framework.** The organized approach that ties these together — what is measured,
by which method, against which references and metrics, and how often. The evaluation
framework makes evaluation systematic rather than ad hoc.

## Principles

- **Evaluate AI; test software.** Measure the quality of model-dependent behavior here, and
  leave the verification of software correctness to [Chapter 18](../18-testing/).
- **Combine human and automated judgment.** Use automation for reach and repeatability and
  human evaluation for judgment.
- **Make quality explicit.** Define success metrics and quality dimensions so "good" is
  specific and measurable.
- **Evaluate continuously.** Track quality over the platform's life and catch regressions as
  models and behavior change.
- **Uphold the platform's architectural principles.** Like every platform capability,
  evaluation is secure, observable, governable, explainable, and composable by design;
  provider-, cloud-, and runtime-agnostic; and vendor-neutral — as expressed in the
  [Platform Capability Model](../PLATFORM_CAPABILITY_MODEL.md) and owned by
  [Chapter 03](../03-engineering-principles/CHAPTER.md).

## Architecture

This section describes the structure of *evaluation*, a cross-cutting capability within the
[Platform Capability Model](../PLATFORM_CAPABILITY_MODEL.md) and the reference architecture
owned by [Chapter 06](../06-reference-architecture/CHAPTER.md).

Evaluation is organized as a framework:

1. The **evaluation framework** defines what is evaluated — **agent**, **prompt**, and
   **quality** evaluation — and how.
2. **Human** and **automated** evaluation apply methods; **benchmarking** and **success
   metrics** make results comparable and explicit.
3. **Continuous** and **reliability** evaluation sustain and stress the measurement over
   time.

Evaluation applies across the platform rather than being a plane itself: it measures the AI
that the [runtime](../07-runtime-platform/CHAPTER.md) executes, draws on
[observability's](../14-observability/CHAPTER.md) signals, and persists its records through
the [data plane](../12-data-platform/CHAPTER.md). It is the AI counterpart to software
[testing](../18-testing/), and the two together give a complete account of
quality.

## Patterns

- **Framework-defined evaluation.** *Context:* measuring AI quality. Evaluate through a
  defined framework — subject, method, reference, metric, cadence — rather than ad hoc.
- **Human-plus-automated.** *Context:* judging quality. Combine automated evaluation for
  scale with human evaluation for judgment.
- **Continuous benchmarking.** *Context:* sustaining quality. Benchmark continually so
  regressions are caught as models and behavior evolve.

## Anti-patterns

- **Testing mistaken for evaluation.** *Why it fails:* treating model-dependent quality as a
  pass/fail software test misjudges it. *Instead:* evaluate AI; test software.
- **Automation-only judgment.** *Why it fails:* automated criteria miss subjective and novel
  quality. *Instead:* combine human and automated judgment.
- **Implicit quality.** *Why it fails:* evaluating against undefined "good" yields
  unrepeatable verdicts. *Instead:* make quality explicit through metrics.
- **Point-in-time evaluation.** *Why it fails:* evaluating once lets quality drift as models
  change. *Instead:* evaluate continuously.

## Best Practices

- Evaluate AI quality here and delegate software correctness to
  [Chapter 18](../18-testing/).
- Define an evaluation framework covering subject, method, reference, metric, and cadence.
- Combine human and automated evaluation, and benchmark against stable references.
- Define success metrics and quality dimensions explicitly.
- Evaluate continuously, drawing on [observability](../14-observability/CHAPTER.md) and
  persisting records through the [data plane](../12-data-platform/CHAPTER.md).

## Examples

The following are illustrative, non-executable aids.

**Evaluation and testing, distinguished:**

| Discipline | Judges | Owned by |
|------------|--------|----------|
| AI Evaluation | Quality of model-dependent behavior | This chapter |
| Software Testing | Correctness of deterministic software | [Chapter 18](../18-testing/) |

**Evaluation methods (illustrative):**

| Method | Strength |
|--------|----------|
| Human evaluation | Judgment for subjective, contextual, or novel quality |
| Automated evaluation | Reach and repeatability at scale |
| Benchmarking | Comparable results across time and versions |

## Checklist

A reader is ready to proceed to
[Chapter 17 — User Experience](../17-ui-ux/CHAPTER.md) when they can confirm:

- [ ] I can explain evaluation as measuring AI quality, distinct from testing.
- [ ] I can distinguish agent, prompt, and quality evaluation.
- [ ] I can combine human and automated evaluation and use benchmarking and success metrics.
- [ ] I can apply continuous and reliability evaluation.

## References

- [Chapter 01 — Platform Vision](../01-platform-vision/CHAPTER.md) and
  [Chapter 02 — Product Thinking](../02-product-thinking/CHAPTER.md) — own the outcomes that
  success metrics measure.
- [Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md) — owns
  architectural reliability, distinct from reliability evaluation.
- [Chapter 07 — Runtime Platform](../07-runtime-platform/CHAPTER.md) — executes the AI that
  is evaluated.
- [Chapter 08 — Builder Platform](../08-builder-platform/CHAPTER.md) — owns the prompt assets
  that prompt evaluation measures.
- [Chapter 14 — Observability](../14-observability/CHAPTER.md) — supplies signals evaluation
  draws on.
- [Chapter 18 — Testing](../18-testing/) — verifies software correctness, distinct from
  evaluation.
- [Platform Capability Model](../PLATFORM_CAPABILITY_MODEL.md) — the canonical model this
  capability belongs to.
- [Glossary](../21-glossary/) — canonical terms used in this chapter.

## Summary

Evaluation is the capability to measure the quality of the platform's AI — model-dependent
behavior that testing cannot judge. Through an evaluation framework it applies agent,
prompt, and quality evaluation, combining human and automated methods, made comparable by
benchmarking and explicit through success metrics, and sustained by continuous and
reliability evaluation. Evaluation measures AI quality; testing verifies software
correctness, and the two are kept distinct. The next chapter,
[Chapter 17 — User Experience](../17-ui-ux/CHAPTER.md), defines how people experience and
trust the platform.
