# Chapter 15 — Security

## Introduction

This chapter defines the security principles of an AI Agent Platform: the enduring
commitments that make the platform trustworthy. Its prerequisite is
[Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md). Security is a
cross-cutting concern that every plane must uphold; this chapter owns its **principles**,
while their operational application — the governance of identity and authorization — is
owned by [Chapter 11 — Control Plane](../11-control-plane/CHAPTER.md). Security defines the
principles that govern identity and authorization; the control plane applies them.

This chapter defines principles and an architectural stance — not any security product,
algorithm, or configuration. It states what must hold for the platform to be trustworthy,
so the guidance remains valid as threats and technologies evolve. No product is named and
no implementation is prescribed.

## Objectives

After reading this chapter, a reader will be able to:

- Explain security as a set of enduring principles and a cross-cutting concern.
- Apply zero trust, secure by design, and defense in depth.
- Reason about threat modeling, the platform trust model, and security architecture.
- Situate secrets management, cryptography principles, privacy, and compliance.

## Concepts

This chapter **owns** the concepts below; other chapters reference them without redefining
them.

**Security Principles.** The enduring commitments that make the platform trustworthy,
independent of any threat of the moment or technology of the day. Security principles are
the foundation this chapter provides; every plane applies them, and the control plane
operationalizes those concerning identity and authorization.

**Secure by Design.** The principle that security is built into the platform from the first
decision, not added afterward. Secure by design makes safety the default state rather than a
later correction, mirroring quality by design (owned by
[Chapter 03](../03-engineering-principles/CHAPTER.md)) in the security domain.

**Zero Trust.** The principle that no actor, request, or component is trusted implicitly by
virtue of its location or origin; trust is established explicitly and continually. Zero
trust replaces assumed perimeters with verified, least-privilege interactions.

**Defense in Depth.** The principle of layering independent safeguards so that the failure
of any one does not compromise the platform. Defense in depth assumes that any single
control may fail and ensures others remain.

**Threat Modeling.** The disciplined identification of what could go wrong — the assets,
threats, and weaknesses relevant to the platform — so that security effort is directed where
it matters. Threat modeling is how security reasoning is made deliberate rather than
reactive.

**Platform Trust Model.** The explicit account of who and what the platform trusts, to what
degree, and on what basis. The trust model is the platform's stated position on trust, from
which zero-trust and authorization decisions follow; the operational governance of the
identities it concerns is owned by
[Chapter 11](../11-control-plane/CHAPTER.md).

**Security Architecture.** The architectural expression of the security principles — how
boundaries, controls, and trust are arranged structurally to uphold them. Security
architecture applies the architectural boundaries owned by
[Chapter 06](../06-reference-architecture/CHAPTER.md) to the purpose of security.

**Secrets Management.** The principles governing how sensitive credentials and keys are
handled so they are never exposed or misused. Secrets management is stated here as
principle; its persistence is a concern of the
[data plane](../12-data-platform/CHAPTER.md) and its operation of the
[control plane](../11-control-plane/CHAPTER.md).

**Cryptography Principles.** The enduring principles governing the use of cryptography —
protecting data in transit and at rest, and establishing integrity and authenticity —
independent of any specific algorithm or library. This chapter owns the principles, not the
mechanisms.

**Privacy.** The principle that personal and sensitive information is collected, used, and
retained only as it should be, and protected throughout. Privacy is a security principle
here; the ownership and lifecycle of the data it concerns are owned by
[Chapter 12](../12-data-platform/CHAPTER.md).

**Compliance.** The principle that the platform can demonstrably meet the external
obligations that apply to it. Compliance is stated as a principle and a capability the
platform must support; the specific regimes are outside this technology-neutral Handbook.

## Principles

- **Secure by design.** Build security in from the first decision; never bolt it on.
- **Trust nothing implicitly.** Establish trust explicitly and continually, following the
  platform trust model.
- **Layer defenses.** Assume any single control may fail, and ensure independent safeguards
  remain.
- **Model threats deliberately.** Direct security effort by reasoning about what could go
  wrong, not by reacting to what already has.
- **Define principles; delegate operation.** Own the security principles here and let the
  control plane apply those governing identity and authorization.
- **Uphold the platform's architectural principles.** Like every platform capability,
  security is secure, observable, governable, explainable, and composable by design;
  provider-, cloud-, and runtime-agnostic; and vendor-neutral — as expressed in the
  [Platform Capability Model](../PLATFORM_CAPABILITY_MODEL.md) and owned by
  [Chapter 03](../03-engineering-principles/CHAPTER.md).

## Architecture

This section describes the structure of the platform's *security*, a cross-cutting concern
within the [Platform Capability Model](../PLATFORM_CAPABILITY_MODEL.md) and the reference
architecture owned by [Chapter 06](../06-reference-architecture/CHAPTER.md).

Security is organized from principle to application:

1. **Security principles** — **secure by design**, **zero trust**, **defense in depth** —
   establish the stance.
2. **Threat modeling** and the **platform trust model** direct where and how it is applied.
3. **Security architecture** arranges boundaries and controls; **secrets management**,
   **cryptography principles**, **privacy**, and **compliance** address specific concerns.

Security applies across every plane rather than being a plane itself. It governs, in
principle, the identity and authorization that the
[control plane](../11-control-plane/CHAPTER.md) operates; it relies on
[observability](../14-observability/CHAPTER.md) to detect and diagnose; and it constrains how
the [data plane](../12-data-platform/CHAPTER.md) handles sensitive information.

## Patterns

- **Threat-model first.** *Context:* designing any capability. Reason about assets, threats,
  and weaknesses before building, so security is directed by understanding.
- **Least-privilege trust.** *Context:* any interaction. Grant only the trust and access
  required, verified continually, following the trust model.
- **Layered controls.** *Context:* protecting anything valuable. Place independent
  safeguards so no single failure is catastrophic.

## Anti-patterns

- **Bolted-on security.** *Why it fails:* security added after design leaves gaps that are
  costly and unreliable to close. *Instead:* secure by design.
- **Implicit trust.** *Why it fails:* trusting by location or origin invites compromise once
  a boundary is crossed. *Instead:* trust nothing implicitly.
- **Single line of defense.** *Why it fails:* one control's failure compromises everything.
  *Instead:* layer defenses.
- **Redefining operation.** *Why it fails:* restating identity and authorization operation
  here duplicates the control plane and will diverge. *Instead:* define principles and
  delegate operation.

## Best Practices

- Threat-model before building, and let the model direct security effort.
- Apply zero trust and least privilege, following the platform trust model.
- Layer independent safeguards for defense in depth.
- State secrets, cryptography, and privacy as principles, delegating their operation and
  persistence to the [control plane](../11-control-plane/CHAPTER.md) and
  [data plane](../12-data-platform/CHAPTER.md).
- Use [observability](../14-observability/CHAPTER.md) to detect and diagnose security
  concerns.

## Examples

The following are illustrative, non-executable aids.

**Security principles and what they establish:**

| Principle | What it establishes |
|-----------|---------------------|
| Secure by design | Safety as the default from the first decision |
| Zero trust | Explicit, continual trust rather than assumed perimeters |
| Defense in depth | Independent safeguards that survive one another's failure |
| Threat modeling | Effort directed by reasoning about what could go wrong |

**Principle versus operation (illustrative):** this chapter states that a principal must be
trusted only as far as verified and authorized; the [control plane](../11-control-plane/CHAPTER.md)
is what actually manages that principal's identity and permissions. Security defines the
rule; the control plane applies it.

## Checklist

A reader is ready to proceed to
[Chapter 16 — Evaluation](../16-evaluation/CHAPTER.md) when they can confirm:

- [ ] I can explain security as enduring principles and a cross-cutting concern.
- [ ] I can apply zero trust, secure by design, and defense in depth.
- [ ] I can reason about threat modeling, the trust model, and security architecture.
- [ ] I understand the split between security principles here and their operation in
  Chapter 11.

## References

- [Chapter 03 — Engineering Principles](../03-engineering-principles/CHAPTER.md) — owns
  quality by design, which secure by design mirrors.
- [Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md) — owns the
  architectural boundaries security architecture applies.
- [Chapter 11 — Control Plane](../11-control-plane/CHAPTER.md) — operates the identity and
  authorization these principles govern.
- [Chapter 12 — Data Platform](../12-data-platform/CHAPTER.md) — owns the data ownership and
  lifecycle privacy concerns.
- [Chapter 14 — Observability](../14-observability/CHAPTER.md) — detects and diagnoses
  security concerns.
- [Platform Capability Model](../PLATFORM_CAPABILITY_MODEL.md) — the canonical model this
  capability belongs to.
- [Glossary](../21-glossary/) — canonical terms used in this chapter.

## Summary

Security is the set of enduring principles that make the platform trustworthy — secure by
design, zero trust, and defense in depth — directed by threat modeling and an explicit
platform trust model, and arranged through security architecture. Secrets management,
cryptography principles, privacy, and compliance are stated here as principles, with their
operation and persistence delegated to the control and data planes. Security defines the
principles that govern identity and authorization; the control plane applies them. The next
chapter, [Chapter 16 — Evaluation](../16-evaluation/CHAPTER.md), defines how the quality of
the platform's AI is measured.
