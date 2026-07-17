# Chapter 19 — DevOps

## Introduction

This chapter defines DevOps for an AI Agent Platform: the engineering operations by which
the platform is built, delivered, and operated. Its prerequisites are
[Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md) and
[Chapter 14 — Observability](../14-observability/CHAPTER.md).

DevOps describes **engineering operations** — how the platform's software is integrated,
released, deployed, and kept operable — and never the platform runtime that executes business
workloads, which is owned by [Chapter 07 — Runtime Platform](../07-runtime-platform/CHAPTER.md).
This chapter defines an operational discipline — practices, pipelines, and readiness — not any
tool, pipeline product, or technology. No product is named and no implementation is
prescribed.

## Objectives

After reading this chapter, a reader will be able to:

- Explain DevOps as engineering operations, distinct from the platform runtime.
- Distinguish continuous integration, delivery, and deployment.
- Reason about deployment pipelines, release management, and the infrastructure lifecycle.
- Apply operational readiness and automation to keep the platform operable.

## Concepts

This chapter **owns** the concepts below; other chapters reference them without redefining
them.

**DevOps.** The engineering operations discipline that unifies building, delivering, and
operating the platform's software as one continuous practice. DevOps is this chapter's
subject: it concerns how the platform is made operable, not how it executes work.

**Engineering Operations.** The whole of the activity that turns engineered software into a
running, maintained platform — integration, delivery, deployment, and ongoing operation.
Engineering operations is the umbrella DevOps organizes; it is distinct from the runtime's
execution of workloads.

**Platform Operations.** The engineering operations concerned specifically with running the
platform itself — keeping it deployed, healthy, and maintainable over time. Platform
operations draws on [observability](../14-observability/CHAPTER.md) for its visibility and on
the [control plane](../11-control-plane/CHAPTER.md) for governance, without executing
workloads.

**Continuous Integration.** The practice of integrating software changes frequently and
verifying them automatically, so that integration problems are found early and small.
Continuous integration keeps the software continuously in a known-good state.

**Continuous Delivery.** The practice of keeping software always in a releasable state
through automation, so that a release is a decision rather than an effort. Continuous
delivery makes releasing routine and low-risk.

**Continuous Deployment.** The practice of automatically deploying releasable changes, so
that delivery reaches the platform without a manual gate. Continuous deployment is
continuous delivery carried through to deployment.

**Deployment Pipelines.** The defined, automated paths a change follows from integration to
deployment, with the verifications and approvals it must pass. Deployment pipelines make the
path from change to running platform explicit and repeatable.

**Release Management.** The practice of coordinating what is released, when, and how, so that
change reaches the platform deliberately and safely. Release management is the operational
counterpart to the release philosophy owned by
[Chapter 20 — Roadmap](../20-roadmap/CHAPTER.md).

**GitOps.** The operational practice of managing infrastructure and deployment declaratively,
through version-controlled sources of truth from which the running state is derived. GitOps
is described here as a neutral operational practice, not as any specific tool.

**Infrastructure Lifecycle.** The stages the platform's infrastructure passes through — from
provisioning, through change, to decommissioning — managed deliberately and declaratively.
The infrastructure lifecycle keeps the platform's foundation reproducible and governable.

**Operational Automation.** The practice of automating operational activity so that
operations are repeatable, reliable, and free of avoidable manual effort. Operational
automation is what makes engineering operations scale.

**Operational Readiness.** The state in which a capability is ready to be operated in
production — observable, governable, recoverable, and understood. Operational readiness is the
bar a capability must meet before it is entrusted to operations, complementing the
production-readiness practice in the framework's playbooks.

## Principles

- **Operate, do not execute.** DevOps builds, delivers, and operates the platform's software;
  it never executes the business workloads the runtime owns.
- **Integrate and deliver continuously.** Keep software continuously integrated and
  releasable so change is small, frequent, and low-risk.
- **Automate the path to production.** Make the path from change to running platform an
  explicit, automated pipeline.
- **Manage infrastructure declaratively.** Derive the running state from version-controlled
  sources of truth.
- **Require operational readiness.** Entrust a capability to operations only when it is
  observable, governable, and recoverable.
- **Uphold the platform's architectural principles.** Like every platform capability, DevOps
  is secure, observable, governable, explainable, and composable by design; provider-,
  cloud-, and runtime-agnostic; and vendor-neutral — as expressed in the
  [Platform Capability Model](../PLATFORM_CAPABILITY_MODEL.md) and owned by
  [Chapter 03](../03-engineering-principles/CHAPTER.md).

## Architecture

This section describes the structure of *engineering operations*, within the
[Platform Capability Model](../PLATFORM_CAPABILITY_MODEL.md) and the reference architecture
owned by [Chapter 06](../06-reference-architecture/CHAPTER.md).

DevOps organizes engineering operations as a continuous flow:

1. **Continuous integration** keeps software known-good; **deployment pipelines** carry
   change forward.
2. **Continuous delivery** and **continuous deployment**, under **release management**, bring
   change to the platform.
3. **GitOps** and the **infrastructure lifecycle** manage the foundation declaratively;
   **operational automation** and **operational readiness** keep **platform operations**
   sustainable.

DevOps operates the platform whose runtime executes workloads: it draws on
[observability](../14-observability/CHAPTER.md) for operational visibility, on the
[control plane](../11-control-plane/CHAPTER.md) for governance, and on
[testing](../18-testing/CHAPTER.md) within its pipelines — while never performing the
runtime's execution.

## Patterns

- **Pipeline to production.** *Context:* delivering change. Move every change through an
  explicit, automated pipeline with defined verifications.
- **Declarative infrastructure.** *Context:* managing the foundation. Derive infrastructure
  and deployment from version-controlled sources of truth.
- **Readiness before operation.** *Context:* going to production. Require operational
  readiness before entrusting a capability to operations.

## Anti-patterns

- **DevOps as runtime.** *Why it fails:* treating engineering operations as the execution of
  workloads confuses two planes. *Instead:* operate, do not execute.
- **Manual release toil.** *Why it fails:* manual, infrequent releases are risky and slow.
  *Instead:* integrate and deliver continuously.
- **Imperative infrastructure.** *Why it fails:* hand-managed infrastructure is
  irreproducible and ungovernable. *Instead:* manage infrastructure declaratively.
- **Unready deployment.** *Why it fails:* operating a capability that is not observable or
  recoverable invites failure. *Instead:* require operational readiness.

## Best Practices

- Keep DevOps to engineering operations; delegate workload execution to the
  [runtime](../07-runtime-platform/CHAPTER.md).
- Integrate and deliver continuously, moving change through automated deployment pipelines.
- Manage infrastructure declaratively through its lifecycle.
- Require operational readiness, drawing on [observability](../14-observability/CHAPTER.md).
- Coordinate releases with the release philosophy owned by
  [Chapter 20](../20-roadmap/CHAPTER.md).

## Examples

The following are illustrative, non-executable aids.

**The continuous flow (illustrative):**

| Practice | What it ensures |
|----------|-----------------|
| Continuous integration | Software is continuously in a known-good state |
| Continuous delivery | Software is always releasable |
| Continuous deployment | Releasable change reaches the platform automatically |

**Operations versus execution (illustrative):** DevOps deploys and operates the platform
software that runs; the [runtime](../07-runtime-platform/CHAPTER.md) is what executes the
business workloads on it. DevOps keeps the platform operable; the runtime does the work.

## Checklist

A reader is ready to proceed to
[Chapter 20 — Roadmap](../20-roadmap/CHAPTER.md) when they can confirm:

- [ ] I can explain DevOps as engineering operations, distinct from the runtime.
- [ ] I can distinguish continuous integration, delivery, and deployment.
- [ ] I can reason about pipelines, release management, and the infrastructure lifecycle.
- [ ] I can apply operational readiness and automation.

## References

- [Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md) — the frame
  that places engineering operations.
- [Chapter 07 — Runtime Platform](../07-runtime-platform/CHAPTER.md) — executes workloads,
  distinct from engineering operations.
- [Chapter 11 — Control Plane](../11-control-plane/CHAPTER.md) — governs the platform DevOps
  operates.
- [Chapter 14 — Observability](../14-observability/CHAPTER.md) — supplies the visibility
  operations rely on.
- [Chapter 18 — Testing](../18-testing/CHAPTER.md) — runs within deployment pipelines.
- [Chapter 20 — Roadmap](../20-roadmap/CHAPTER.md) — owns the release philosophy release
  management serves.
- [Platform Capability Model](../PLATFORM_CAPABILITY_MODEL.md) — the canonical model this
  capability belongs to.
- [Glossary](../21-glossary/CHAPTER.md) — canonical terms used in this chapter.

## Summary

DevOps is the engineering-operations discipline that builds, delivers, and operates the
platform's software: continuous integration, delivery, and deployment move change through
automated deployment pipelines under release management, while GitOps and the infrastructure
lifecycle manage the foundation declaratively, and operational automation and readiness keep
platform operations sustainable. DevOps operates the platform; the runtime executes its
workloads, and the two never merge. The next chapter,
[Chapter 20 — Roadmap](../20-roadmap/CHAPTER.md), defines how the framework and the platform
evolve over the long term.
