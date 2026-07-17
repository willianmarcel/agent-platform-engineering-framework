# Chapter 09 — Provider Platform

## Introduction

This chapter defines the provider plane of an AI Agent Platform: the capability through
which the platform obtains intelligence from external model and service providers. Its
prerequisites are
[Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md) and
[Chapter 07 — Runtime Platform](../07-runtime-platform/CHAPTER.md), whose executing work
consumes what providers supply.

The central subject of this chapter is **provider abstraction** as a long-term
architectural principle: the platform depends on the *capabilities* providers offer, not on
any particular provider. Accordingly, this chapter names no vendor and no product; it
describes an architectural capability — responsibilities, boundaries, and relationships —
that must remain valid as the provider landscape changes. Providers supply intelligence;
they do not create solutions, execute them, extend the platform, govern it, or persist its
data.

## Objectives

After reading this chapter, a reader will be able to:

- Explain provider abstraction and why it is an enduring architectural principle.
- Describe a model catalog and how provider capabilities are represented.
- Reason about multi-provider strategy, routing, and model selection.
- Apply capability, cost, and latency awareness while preserving provider independence and
  vendor neutrality.

## Concepts

This chapter **owns** the concepts below; other chapters reference them without redefining
them.

**LLM Providers.** External suppliers of language-model and related generative
intelligence that the platform consumes as a capability. This chapter treats providers as
an abstract role defined by what they supply, never as specific named products.

**Provider Abstraction.** The architectural boundary that separates the platform from any
particular provider, expressed as a stable, provider-neutral contract for the capabilities
the platform depends on. Provider abstraction is the plane's defining principle: it lets
providers change beneath a constant contract, so the platform is never coupled to one
supplier.

**Model Catalog.** The platform's organized inventory of the models available through its
providers, described by their capabilities rather than by their origin. The catalog is how
the platform reasons about what intelligence it can draw on, independent of who supplies it.

**Provider Capabilities.** The abstract abilities a provider offers — the kinds of work its
models can perform and the properties they exhibit — expressed in provider-neutral terms.
Provider capabilities are distinct from product capabilities (owned by
[Chapter 02](../02-product-thinking/CHAPTER.md)) and from plugin capabilities (owned by
[Chapter 10](../10-plugin-platform/CHAPTER.md)); they describe supplied intelligence.

**Capability Matching.** The act of selecting intelligence by matching the capabilities a
task requires against the provider capabilities available in the catalog. Capability
matching keeps selection grounded in what a task needs, not in a fixed provider choice.

**Multi-Provider Strategy.** The deliberate use of more than one provider so the platform is
resilient to any single provider's limits, changes, or unavailability. Multi-provider
strategy is how provider independence is realized in practice.

**Routing Policies.** The provider-neutral rules that decide, for a given unit of work,
which provider and model should serve it. Routing policies express intent — such as
preferring capability fit, cost, or latency — and are distinct from the governance policies
owned by [Chapter 11](../11-control-plane/CHAPTER.md).

**Model Selection.** The outcome of applying routing policies and capability matching to
choose a specific model for a specific need. Model selection is a decision the plane makes
on the platform's behalf, insulated behind the provider abstraction.

**Cost Awareness.** The plane's account of the relative cost of using different providers
and models, so that selection can weigh cost as a first-class factor. Cost awareness is a
property the plane maintains, not a specific price of any product.

**Latency Awareness.** The plane's account of the responsiveness of different providers and
models, so that selection can weigh latency alongside capability and cost. Like cost
awareness, it is an abstract, provider-neutral property.

**Provider Independence.** The property that the platform can operate without dependence on
any single provider, changing or combining providers without redesign. Provider
independence is the goal that provider abstraction and multi-provider strategy exist to
secure.

**Vendor Neutrality.** The principle that the platform's design, contracts, and language
favor no vendor, so guidance and solutions remain valid across the ecosystem. Vendor
neutrality is a design commitment, upheld throughout this Handbook.

## Principles

- **Depend on capabilities, not providers.** Bind the platform to a provider-neutral
  contract for the capabilities it needs, never to a specific supplier.
- **Assume plurality.** Design for more than one provider so no single supplier is a point
  of failure or lock-in.
- **Select by fit.** Choose models by matching required capabilities against available ones,
  weighing cost and latency, through explicit routing policies.
- **Preserve independence and neutrality.** Keep the platform able to change providers
  without redesign, and keep its language and design free of vendor bias.
- **Uphold the platform's architectural principles.** Like every core-platform plane, the
  provider plane is provider-, framework-, cloud-, and runtime-agnostic; vendor-neutral;
  protocol-oriented; and extensible, composable, observable, and governable by design —
  instantiating the architectural principles owned by
  [Chapter 03](../03-engineering-principles/CHAPTER.md).

## Architecture

This section describes the structure of the *provider plane*, within the reference
architecture owned by [Chapter 06](../06-reference-architecture/CHAPTER.md).

The provider plane is organized around insulated selection and use of intelligence:

1. Providers are represented behind a single **provider abstraction**.
2. Their models are described in a **model catalog** by their **provider capabilities**.
3. For a unit of work, **capability matching** and **routing policies** — informed by
   **cost awareness** and **latency awareness** — drive **model selection**.
4. A **multi-provider strategy** sustains **provider independence** and **vendor
   neutrality**.

The plane supplies intelligence to the [runtime plane](../07-runtime-platform/CHAPTER.md),
which executes the work; it is governed by the
[control plane](../11-control-plane/CHAPTER.md), which owns the governance policies that
constrain routing; and it never creates, extends, or persists.

## Patterns

- **Abstraction-first integration.** *Context:* adopting any provider. Integrate it behind
  the provider abstraction so nothing above the abstraction depends on it.
- **Policy-driven routing.** *Context:* choosing intelligence for work. Let routing policies
  and capability matching select the model, rather than hard-wiring a choice.
- **Graceful plurality.** *Context:* resilience. Maintain multiple providers so work can be
  served despite any one provider's change or unavailability.

## Anti-patterns

- **Provider lock-in.** *Why it fails:* coupling the platform to one provider's specifics
  forfeits independence and ages with that provider. *Instead:* depend on capabilities, not
  providers.
- **Vendor language in the design.** *Why it fails:* naming and modeling around one vendor
  embeds bias and dates the design. *Instead:* preserve vendor neutrality.
- **Hard-wired selection.** *Why it fails:* fixing a model choice in place ignores capability
  fit, cost, and latency and cannot adapt. *Instead:* select by fit through routing
  policies.
- **Single-provider assumption.** *Why it fails:* assuming one provider makes the platform
  fragile and captive. *Instead:* assume plurality.

## Best Practices

- Express every provider dependency as a provider-neutral capability contract.
- Describe models in the catalog by capability, and select by matching need to capability.
- Weigh cost and latency in routing policies, keeping those distinct from governance policy.
- Maintain a multi-provider strategy to secure provider independence.
- Keep all language, contracts, and examples vendor-neutral.

## Examples

The following are illustrative, non-executable aids.

**Selection factors (provider-neutral):**

| Factor | Question it answers |
|--------|---------------------|
| Capability matching | Can the model do what the task requires? |
| Cost awareness | What is the relative cost of this choice? |
| Latency awareness | How responsive is this choice? |

**Provider abstraction (illustrative):** work above the abstraction requests a *capability*;
the plane selects a suitable model behind the abstraction; the requesting work is unaware of
which provider served it, so providers may change without affecting anything above.

## Checklist

A reader is ready to proceed to
[Chapter 10 — Plugin Platform](../10-plugin-platform/CHAPTER.md) when they can confirm:

- [ ] I can explain provider abstraction and why it endures.
- [ ] I can describe a model catalog and provider capabilities in neutral terms.
- [ ] I can reason about routing, model selection, cost, and latency awareness.
- [ ] I can preserve provider independence and vendor neutrality.

## References

- [Chapter 02 — Product Thinking](../02-product-thinking/CHAPTER.md) — owns product
  capabilities, distinct from provider capabilities.
- [Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md) — the frame
  that places the provider plane.
- [Chapter 07 — Runtime Platform](../07-runtime-platform/CHAPTER.md) — consumes the
  intelligence the provider plane supplies.
- [Chapter 10 — Plugin Platform](../10-plugin-platform/CHAPTER.md) — owns plugin
  capabilities, distinct from provider capabilities.
- [Chapter 11 — Control Plane](../11-control-plane/CHAPTER.md) — owns the governance policies
  that constrain routing.
- [Glossary](../21-glossary/) — canonical terms used in this chapter.

## Summary

The provider plane obtains intelligence for the platform behind a stable provider
abstraction, so the platform depends on capabilities rather than on any supplier. It
maintains a model catalog described by provider capabilities, and selects intelligence
through capability matching and routing policies informed by cost and latency awareness — all
sustained by a multi-provider strategy that secures provider independence and vendor
neutrality. Providers supply intelligence and nothing more. The next chapter,
[Chapter 10 — Plugin Platform](../10-plugin-platform/CHAPTER.md), defines how the platform is
extended beyond the intelligence providers supply.
