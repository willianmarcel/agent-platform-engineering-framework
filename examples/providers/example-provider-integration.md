# Example — Illustrative Provider Integration (behind the abstraction) (conceptual)

A conceptual, **non-executable**, **technology-neutral** example demonstrating APEF concepts. It
defines no real product and names no vendor, product, framework, SDK, or implementation detail;
it illustrates methodology only.

**Required capability.** A *text generation capability* with a stated quality profile, requested by capability — the requesting work is unaware of which provider serves it. *(illustrative; no provider is named)*

**Model catalog.** Two abstract providers, each described only by the capabilities and quality profile they offer ([Chapter 09](../../handbook/09-provider-platform/CHAPTER.md)).

**Routing.** Selection by capability matching, weighing cost awareness and latency awareness through provider-neutral routing policies.

**Provider independence.** Either abstract provider can serve the capability; one can be replaced or added without changing anything above the abstraction.

**Acceptance criteria.** The capability is served to the stated quality profile regardless of which abstract provider is selected — measurable in a real Provider Specification.

## Concepts demonstrated

This example demonstrates provider abstraction, model catalog, routing, cost/latency awareness, provider independence, vendor neutrality (all 09).

## Relationships

- [Provider Examples](PROVIDER_EXAMPLES.md) — the area entry document.
- [Examples Index](../EXAMPLES_INDEX.md) — all example areas.
- [Platform Capability Model](../../handbook/PLATFORM_CAPABILITY_MODEL.md) — the capabilities this
  example draws on.

## Conventions

- Illustrative only; every value is a placeholder for a real, measurable one in an actual
  specification.
- Names no technology; demonstrates APEF concepts exclusively.
