# Chapter 20 — Roadmap

## Introduction

This chapter defines how an AI Agent Platform, and the framework that guides it, evolve over
the long term. Its prerequisites are
[Chapter 01 — Platform Vision](../01-platform-vision/CHAPTER.md) and
[Chapter 02 — Product Thinking](../02-product-thinking/CHAPTER.md), whose vision and product
philosophy this evolution serves.

This chapter defines an evolution philosophy — enduring strategy for how the platform grows —
not a plan, a backlog, or a release schedule. It states the principles by which capabilities,
architecture, and versions change over time, so the guidance remains valid regardless of any
particular plan. No product is named and no implementation is prescribed.

## Objectives

After reading this chapter, a reader will be able to:

- Explain evolution strategy as a philosophy, distinct from a project plan or backlog.
- Reason about capability, product, and architectural evolution.
- Apply backward compatibility, versioning strategy, and a technical-debt strategy.
- Frame innovation and long-term evolution as deliberate, sustained practices.

## Concepts

This chapter **owns** the concepts below; other chapters reference them without redefining
them.

**Evolution Strategy.** The overarching approach to how the platform changes over its life —
what is prioritized, what is preserved, and how change is sequenced in principle. Evolution
strategy is this chapter's subject: it governs the *how* of change, not a specific *what* or
*when*.

**Long-term Evolution.** The perspective that treats the platform as something that must
remain valuable and coherent over many years, and shapes decisions accordingly. Long-term
evolution is the horizon evolution strategy is set against.

**Capability Evolution.** The principled growth of the platform's capabilities over time —
how a capability matures, changes, or is retired — as the durable unit by which the platform
advances. Capability evolution applies, at the roadmap horizon, the product evolution owned by
[Chapter 02](../02-product-thinking/CHAPTER.md); the platform grows by evolving capabilities,
not by accumulating features.

**Product Evolution Roadmap.** The forward view of how the product's value is intended to
grow, expressed as sequenced capability evolution rather than a schedule. The product
evolution roadmap turns the product philosophy into a direction, while remaining a philosophy
of sequencing rather than a dated plan.

**Architectural Evolution.** The principled change of the platform's architecture over time,
so the structure can adapt without losing coherence. Architectural evolution governs how the
reference architecture owned by [Chapter 06](../06-reference-architecture/CHAPTER.md) is
allowed to change; it does not redefine that architecture.

**Backward Compatibility.** The commitment to preserve what those who depend on the platform
already rely on, so that evolution does not betray them. Backward compatibility is the
constraint that makes evolution trustworthy, and it is expressed concretely at interfaces
through the API versioning owned by [Chapter 13](../13-api-platform/CHAPTER.md).

**Versioning Strategy.** The principled approach to how the platform expresses change through
versions — what a version communicates and what it promises. Versioning strategy is the
platform-wide philosophy of versioning, distinct from the API versioning mechanism owned by
[Chapter 13](../13-api-platform/CHAPTER.md).

**Release Philosophy.** The principles that govern how and why the platform releases change —
its cadence, its risk posture, and what a release means. Release philosophy is the *why* of
releasing; the operational *how* is owned by the release management in
[Chapter 19](../19-devops/CHAPTER.md).

**Technical Debt Strategy.** The deliberate approach to incurring, tracking, and repaying
technical debt, so that short-term compromise does not silently erode the platform. A
technical-debt strategy keeps evolvability (owned by
[Chapter 03](../03-engineering-principles/CHAPTER.md)) sustainable over time.

**Innovation Management.** The deliberate practice of pursuing new value while protecting the
platform's coherence and commitments. Innovation management is how evolution admits the new
without destabilizing the whole.

## Principles

- **Evolve by strategy, not by plan.** Govern change through an enduring evolution strategy,
  leaving specific plans, backlogs, and schedules outside the Handbook.
- **Evolve capabilities, not features.** Advance the platform by maturing capabilities toward
  enduring value.
- **Preserve what is depended upon.** Hold backward compatibility so evolution does not
  betray those who rely on the platform.
- **Version with meaning.** Express change through a versioning strategy that communicates
  what each version promises.
- **Repay debt deliberately.** Manage technical debt so evolvability is sustained rather than
  eroded.
- **Uphold the platform's architectural principles.** Like every platform capability,
  evolution is secure, observable, governable, explainable, and composable by design;
  provider-, cloud-, and runtime-agnostic; and vendor-neutral — as expressed in the
  [Platform Capability Model](../PLATFORM_CAPABILITY_MODEL.md) and owned by
  [Chapter 03](../03-engineering-principles/CHAPTER.md).

## Architecture

This section describes the structure of the *evolution philosophy*, within the
[Platform Capability Model](../PLATFORM_CAPABILITY_MODEL.md) and the reference architecture
owned by [Chapter 06](../06-reference-architecture/CHAPTER.md).

Evolution is organized from horizon to commitment:

1. **Long-term evolution** sets the horizon; **evolution strategy** governs how change is
   prioritized and sequenced.
2. **Capability evolution**, the **product evolution roadmap**, and **architectural
   evolution** express change across the product and the architecture.
3. **Backward compatibility**, **versioning strategy**, **release philosophy**, **technical
   debt strategy**, and **innovation management** are the commitments that keep evolution
   trustworthy and sustainable.

Evolution serves the [vision](../01-platform-vision/CHAPTER.md) and
[product philosophy](../02-product-thinking/CHAPTER.md), is realized operationally through the
release management owned by [Chapter 19](../19-devops/CHAPTER.md), and is expressed at
interfaces through the API versioning owned by [Chapter 13](../13-api-platform/CHAPTER.md).

## Patterns

- **Strategy over schedule.** *Context:* directing evolution. Govern change with an enduring
  strategy rather than a fixed plan, so direction survives changing circumstances.
- **Compatible evolution.** *Context:* changing anything depended upon. Preserve backward
  compatibility, and version deliberately where change is unavoidable.
- **Deliberate debt.** *Context:* short-term compromise. Incur technical debt knowingly and
  track it so it is repaid rather than forgotten.

## Anti-patterns

- **Roadmap as schedule.** *Why it fails:* a dated plan masquerading as strategy dates
  quickly and constrains without guiding. *Instead:* evolve by strategy, not by plan.
- **Feature accumulation.** *Why it fails:* growing by features rather than capabilities
  yields sprawl, not value. *Instead:* evolve capabilities, not features.
- **Silent breakage.** *Why it fails:* evolving without backward compatibility betrays
  dependents. *Instead:* preserve what is depended upon.
- **Debt denial.** *Why it fails:* unacknowledged technical debt compounds until evolvability
  is lost. *Instead:* repay debt deliberately.

## Best Practices

- Govern evolution through an enduring strategy, keeping specific plans and backlogs outside
  the Handbook.
- Advance by capability evolution aligned to the [vision](../01-platform-vision/CHAPTER.md)
  and [product philosophy](../02-product-thinking/CHAPTER.md).
- Preserve backward compatibility and version with meaning, delegating the mechanism to
  [Chapter 13](../13-api-platform/CHAPTER.md).
- Maintain a technical-debt strategy to sustain evolvability.
- Coordinate release philosophy here with release management in
  [Chapter 19](../19-devops/CHAPTER.md).

## Examples

The following are illustrative, non-executable aids.

**Dimensions of evolution:**

| Dimension | What it governs |
|-----------|-----------------|
| Capability evolution | How capabilities mature, change, or retire |
| Architectural evolution | How the architecture adapts while staying coherent |
| Versioning strategy | What each version communicates and promises |
| Technical debt strategy | How debt is incurred, tracked, and repaid |

**Strategy versus plan (illustrative):** this chapter states *how* the platform should evolve —
by capability, compatibly, with meaningful versions; it does not state *what* will ship *when*,
which is a plan and lies outside the Handbook.

## Checklist

A reader is ready to proceed to
[Chapter 21 — Glossary](../21-glossary/CHAPTER.md) when they can confirm:

- [ ] I can explain evolution strategy as a philosophy, not a plan or backlog.
- [ ] I can reason about capability, product, and architectural evolution.
- [ ] I can apply backward compatibility, versioning strategy, and technical-debt strategy.
- [ ] I can frame innovation and long-term evolution deliberately.

## References

- [Chapter 01 — Platform Vision](../01-platform-vision/CHAPTER.md) and
  [Chapter 02 — Product Thinking](../02-product-thinking/CHAPTER.md) — own the vision and
  product philosophy evolution serves.
- [Chapter 03 — Engineering Principles](../03-engineering-principles/CHAPTER.md) — owns
  evolvability, which the technical-debt strategy sustains.
- [Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md) — owns the
  architecture that architectural evolution changes.
- [Chapter 13 — API Platform](../13-api-platform/CHAPTER.md) — owns the API versioning that
  expresses compatibility at interfaces.
- [Chapter 19 — DevOps](../19-devops/CHAPTER.md) — owns the release management that realizes
  release philosophy.
- [Platform Capability Model](../PLATFORM_CAPABILITY_MODEL.md) — the canonical model this
  capability belongs to.
- [Glossary](../21-glossary/CHAPTER.md) — canonical terms used in this chapter.

## Summary

This chapter defines how the platform and framework evolve: an evolution strategy, set against
a long-term horizon, that advances the platform by capability, product, and architectural
evolution, and keeps that evolution trustworthy through backward compatibility, a versioning
strategy, a release philosophy, a technical-debt strategy, and innovation management. It is a
philosophy of evolution, not a plan, backlog, or schedule. The final chapter,
[Chapter 21 — Glossary](../21-glossary/CHAPTER.md), consolidates the canonical vocabulary the
whole Handbook shares.
