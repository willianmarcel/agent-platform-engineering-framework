# Example — Illustrative Tool Plugin (conceptual)

A conceptual, **non-executable**, **technology-neutral** example demonstrating APEF concepts. It
defines no real product and names no vendor, product, framework, SDK, or implementation detail;
it illustrates methodology only.

**Contributed capability.** A *lookup tool* that contributes a discrete action an agent can invoke. *(illustrative; abstract)*

**Plugin contract.** States what the plugin provides (the lookup action), what it requires (an input query), and the guarantees it upholds ([Chapter 10](../../handbook/10-plugin-platform/CHAPTER.md)).

**Integration.** Reaches its external system through an open, standardized protocol treated architecturally — no product or SDK is named.

**Lifecycle.** Registration → validation → activation → use → deactivation, governed by the platform; the extension is isolated.

**Acceptance criteria.** The plugin contributes its capability within its contract and lifecycle without compromising the core — measurable in a real Plugin Specification.

## Concepts demonstrated

This example demonstrates plugin architecture, extensions/tools, plugin contract, plugin lifecycle, protocol-oriented integration (all 10).

## Relationships

- [Plugin Examples](PLUGIN_EXAMPLES.md) — the area entry document.
- [Examples Index](../EXAMPLES_INDEX.md) — all example areas.
- [Platform Capability Model](../../handbook/PLATFORM_CAPABILITY_MODEL.md) — the capabilities this
  example draws on.

## Conventions

- Illustrative only; every value is a placeholder for a real, measurable one in an actual
  specification.
- Names no technology; demonstrates APEF concepts exclusively.
