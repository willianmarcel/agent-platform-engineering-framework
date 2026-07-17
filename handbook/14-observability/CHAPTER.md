# Chapter 14 — Observability

## Introduction

This chapter defines observability as a cross-cutting capability of an AI Agent Platform:
the capability to understand the platform's internal state from the signals it emits. Its
prerequisites are
[Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md) and
[Chapter 07 — Runtime Platform](../07-runtime-platform/CHAPTER.md), whose running work is a
principal subject of observation.

Observability here is an architectural capability — what must be emitted, correlated, and
understood, and to what standard — not any monitoring tool, dashboard, or technology. It
describes the signals a platform must produce and the visibility they enable, so the
guidance holds whatever technology realizes it. No product is named and no implementation
is prescribed.

## Objectives

After reading this chapter, a reader will be able to:

- Explain observability as an architectural capability and how it differs from monitoring.
- Distinguish the platform signals — logs, metrics, and traces — and their correlation.
- Reason about operational visibility, health, diagnostics, and service-level objectives.
- Keep observability designed in rather than added after the fact.

## Concepts

This chapter **owns** the concepts below; other chapters reference them without redefining
them.

**Observability.** The capability to understand the platform's internal state and behavior
from the signals it emits, without changing it to ask a new question. Observability is a
property the platform must be designed to have; it is what makes operation, diagnosis, and
improvement possible.

**Platform Signals.** The observable outputs the platform emits about itself — the raw
material of observability. Logs, metrics, and traces are the principal kinds of platform
signal.

**Telemetry.** The disciplined emission and collection of platform signals. Telemetry is
how signals are produced and gathered so they can be understood; it is the instrumentation
side of observability.

**Logs.** The records of discrete events the platform emits, describing what happened and
when. Logs are the narrative signal, valuable for detail and context.

**Metrics.** The quantitative measurements the platform emits over time, describing how much
and how often. Metrics are the aggregate signal, valuable for trends and thresholds.

**Traces.** The signals that follow a unit of work across the platform's parts, describing
its path and timing. Traces are the connective signal, valuable for understanding flow
across boundaries.

**Correlation.** The linking of signals — logs, metrics, and traces — so that they can be
understood together as one account of an event or unit of work. Correlation is what turns
separate signals into understanding.

**Operational Visibility.** The resulting ability of operators to see what the platform is
doing and how well, derived from correlated signals. Operational visibility is
observability realized for the people who run the platform.

**Health.** The observable condition of the platform and its parts — whether they are
functioning as intended. Health is a summary judgment built from signals, used to know at a
glance whether intervention is needed.

**Monitoring.** The ongoing observation of signals and health against expectations, so that
deviations are noticed. Monitoring is the active use of observability over time; it is a
practice the platform's observability enables, not a tool.

**Diagnostics.** The use of correlated signals to determine the cause of a problem.
Diagnostics is observability applied to explanation — moving from *what* is wrong to *why*.

**SLO.** A service-level objective: an explicit target for a signal that defines acceptable
operation, against which health and monitoring are judged. SLOs make "good enough" explicit
and measurable.

## Principles

- **Observable by design.** Build the platform to emit the signals needed to understand it,
  rather than adding visibility after the fact.
- **Correlate signals.** Emit logs, metrics, and traces so they can be linked into one
  account.
- **Make objectives explicit.** Define service-level objectives so health and monitoring are
  judged against a stated standard.
- **Observe without disturbing.** Understand the platform from its signals without having to
  change it to ask.
- **Uphold the platform's architectural principles.** Like every platform capability,
  observability is secure, observable, governable, explainable, and composable by design;
  provider-, cloud-, and runtime-agnostic; and vendor-neutral — as expressed in the
  [Platform Capability Model](../PLATFORM_CAPABILITY_MODEL.md) and owned by
  [Chapter 03](../03-engineering-principles/CHAPTER.md).

## Architecture

This section describes the structure of *observability*, a cross-cutting capability within
the [Platform Capability Model](../PLATFORM_CAPABILITY_MODEL.md) and the reference
architecture owned by [Chapter 06](../06-reference-architecture/CHAPTER.md).

Observability is organized from signal to understanding:

1. **Telemetry** emits **platform signals** — **logs**, **metrics**, and **traces**.
2. **Correlation** links them into one account.
3. **Operational visibility**, **health**, and **diagnostics** derive understanding, judged
   against **SLOs** through **monitoring**.

Observability applies across every plane rather than being a plane itself: it observes the
[runtime's](../07-runtime-platform/CHAPTER.md) execution, the other planes' behavior, and
the platform as a whole. Its durable record — audit data — is persisted by the
[data plane](../12-data-platform/CHAPTER.md), which observability uses without owning, and
its findings inform [security](../15-security/CHAPTER.md) and
[evaluation](../16-evaluation/CHAPTER.md).

## Patterns

- **Instrument for questions.** *Context:* designing any capability. Emit the signals needed
  to answer the questions operators will ask, before they must ask them.
- **Correlate across boundaries.** *Context:* work that crosses planes. Trace and correlate
  signals so a unit of work can be understood end to end.
- **Objective-driven monitoring.** *Context:* judging operation. Monitor signals against
  explicit SLOs rather than against intuition.

## Anti-patterns

- **Observability as afterthought.** *Why it fails:* adding visibility after the fact leaves
  blind spots exactly where they matter. *Instead:* observable by design.
- **Uncorrelated signals.** *Why it fails:* logs, metrics, and traces that cannot be linked
  yield data without understanding. *Instead:* correlate signals.
- **Objectiveless monitoring.** *Why it fails:* watching signals with no stated target
  cannot say whether operation is acceptable. *Instead:* make objectives explicit.
- **Tool-shaped thinking.** *Why it fails:* treating observability as a tool rather than a
  designed capability ties it to a technology. *Instead:* design the capability, whatever
  realizes it.

## Best Practices

- Design each capability to emit the logs, metrics, and traces needed to understand it.
- Correlate signals so units of work are understandable across planes.
- Define SLOs and monitor against them.
- Persist durable records through the [data plane](../12-data-platform/CHAPTER.md) rather
  than reinventing storage.
- Feed observability findings to [security](../15-security/CHAPTER.md) and
  [evaluation](../16-evaluation/CHAPTER.md).

## Examples

The following are illustrative, non-executable aids.

**Platform signals and what they reveal:**

| Signal | What it reveals |
|--------|-----------------|
| Logs | What happened, in narrative detail |
| Metrics | How much and how often, over time |
| Traces | The path and timing of work across the platform |
| Correlation | The three above, understood together |

**From signal to objective (illustrative):** signals are emitted and correlated, operational
visibility and health are derived, and both are judged against SLOs — so that acceptable
operation is defined in advance and deviations are noticed as they arise.

## Checklist

A reader is ready to proceed to
[Chapter 15 — Security](../15-security/CHAPTER.md) when they can confirm:

- [ ] I can explain observability as a capability and distinguish it from monitoring.
- [ ] I can distinguish logs, metrics, and traces, and why correlation matters.
- [ ] I can reason about operational visibility, health, diagnostics, and SLOs.
- [ ] I can keep observability designed in rather than added later.

## References

- [Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md) — the frame
  that places observability as a cross-cutting capability.
- [Chapter 07 — Runtime Platform](../07-runtime-platform/CHAPTER.md) — a principal subject of
  observation.
- [Chapter 12 — Data Platform](../12-data-platform/CHAPTER.md) — persists the durable audit
  record observability produces.
- [Chapter 15 — Security](../15-security/CHAPTER.md) and
  [Chapter 16 — Evaluation](../16-evaluation/CHAPTER.md) — consume observability's findings.
- [Platform Capability Model](../PLATFORM_CAPABILITY_MODEL.md) — the canonical model this
  capability belongs to.
- [Glossary](../21-glossary/) — canonical terms used in this chapter.

## Summary

Observability is the capability to understand the platform from the signals it emits.
Telemetry produces platform signals — logs, metrics, and traces — which correlation links
into one account, yielding operational visibility, health, and diagnostics, judged against
explicit SLOs through monitoring. It is a cross-cutting capability designed into every
plane, not a tool bolted on, and it observes without disturbing. The next chapter,
[Chapter 15 — Security](../15-security/CHAPTER.md), defines the principles that make the
platform trustworthy.
