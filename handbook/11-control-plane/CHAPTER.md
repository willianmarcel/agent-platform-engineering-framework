# Chapter 11 — Control Plane

## Introduction

This chapter defines the control plane of an AI Agent Platform: the capability through
which the platform is *governed and operated*. Its prerequisite is
[Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md), which placed
the control plane as one plane within the whole.

The control plane **manages the platform**; it **never executes business workloads**. That
boundary is its defining principle: it decides what is permitted, configured, and
allocated, while the running of work belongs to the
[runtime plane](../07-runtime-platform/CHAPTER.md). This chapter describes an architectural
capability — responsibilities, boundaries, and relationships — not any administration tool,
identity system, or technology. This chapter owns the *governance and operation* of identity
and authorization on the platform; the **security model and its principles** — threat
modeling, isolation, least privilege, and secrets — are owned by
[Chapter 15 — Security](../15-security/), which this plane applies rather than defines.

## Objectives

After reading this chapter, a reader will be able to:

- Explain what the control plane governs and why it never executes workloads.
- Distinguish platform governance, configuration, and operational governance.
- Reason about multi-tenancy, quotas, and feature flags as governance mechanisms.
- Understand how the control plane governs identity and authorization while deferring the
  security model to its owner.

## Concepts

This chapter **owns** the concepts below; other chapters reference them without redefining
them.

**Platform Governance.** The capability to decide and enforce what the platform and its
tenants may do — the rules, permissions, and limits under which everything else operates.
Platform governance is the control plane's purpose: it sets the conditions the other planes
run within.

**Operational Governance.** The subset of governance concerned with running the platform
well over time — administration, allocation, and the controls by which operators keep the
platform healthy and compliant. Where platform governance sets the rules, operational
governance is the ongoing practice of applying them.

**Configuration.** The capability to determine the platform's behavior through declared
settings rather than through change to what is built. Configuration is how governance is
expressed as adjustable, auditable state.

**Platform Configuration.** The platform-wide configuration that establishes how the
platform itself behaves, as distinct from the configuration of any single solution.
Platform configuration is the control plane's authoritative account of the platform's
operating settings.

**Policies.** The declared rules that govern what is permitted across the platform. Control-
plane policies are governance rules; they are distinct from the provider routing policies
owned by [Chapter 09](../09-provider-platform/CHAPTER.md), which decide provider selection,
not permission.

**Multi-Tenancy.** The capability to serve multiple tenants from one platform while keeping
each tenant's configuration, data ownership, and limits separate and governed. Multi-tenancy
is the governance structure that makes shared operation safe and fair.

**Identity.** In this plane, the governance of who and what the platform recognizes as
principals — the establishment and management of tenants, users, and services as identities
the platform can reason about. This is the operational governance of identity; the security
principles that identity must satisfy are owned by
[Chapter 15 — Security](../15-security/).

**Authorization.** In this plane, the governance of what a recognized principal is permitted
to do — the assignment and enforcement of permissions according to policy. This is the
governance of authorization; its underlying security model, including least privilege and
isolation, is owned by [Chapter 15 — Security](../15-security/).

**Quotas.** The declared limits on how much of a resource a tenant or principal may consume.
Quotas are a governance mechanism for fairness, cost control, and protection against
overuse.

**Feature Flags.** The governance mechanism by which capabilities are turned on or off, or
scoped to particular tenants, without changing what is built. Feature flags let governance
control exposure and rollout as configuration.

**Administration.** The capability by which operators manage the platform — creating tenants,
setting configuration and policy, and overseeing the platform's operation. Administration is
the human-facing surface of operational governance.

## Principles

- **Govern, do not execute.** The control plane decides what is permitted, configured, and
  allocated; it never runs business workloads, which belong to the runtime.
- **Express governance as configuration and policy.** Make governance adjustable and
  auditable through declared settings and rules rather than through change to what is built.
- **Isolate tenants.** Keep each tenant's configuration, limits, and data ownership separate
  and enforced.
- **Apply the security model, do not define it.** Govern identity and authorization
  operationally, applying the principles owned by
  [Chapter 15 — Security](../15-security/).
- **Uphold the platform's architectural principles.** Like every core-platform plane, the
  control plane is provider-, framework-, cloud-, and runtime-agnostic; vendor-neutral;
  protocol-oriented; and extensible, composable, observable, and governable by design —
  instantiating the architectural principles owned by
  [Chapter 03](../03-engineering-principles/CHAPTER.md).

## Architecture

This section describes the structure of the *control plane*, within the reference
architecture owned by [Chapter 06](../06-reference-architecture/CHAPTER.md).

The control plane is organized around governance and operation:

1. **Platform governance** sets the rules; **operational governance** and **administration**
   apply them over time.
2. Governance is expressed as **configuration** and **platform configuration**, **policies**,
   **quotas**, and **feature flags**.
3. **Multi-tenancy** structures shared operation; **identity** and **authorization** govern
   who may act and what they may do, applying the security model owned by
   [Chapter 15](../15-security/).

The control plane governs the other planes without doing their work: it constrains what the
[builder](../08-builder-platform/CHAPTER.md) may build, how the
[provider plane](../09-provider-platform/CHAPTER.md) routes, what
[plugins](../10-plugin-platform/CHAPTER.md) may do, and what the
[runtime](../07-runtime-platform/CHAPTER.md) may run — while the
[data plane](../12-data-platform/CHAPTER.md) persists configuration, policy, and audit data
on its behalf.

## Patterns

- **Governance as declared state.** *Context:* changing platform behavior. Express the change
  as configuration or policy, so it is adjustable and auditable rather than rebuilt.
- **Tenant-scoped everything.** *Context:* shared operation. Scope configuration, quotas, and
  permissions to tenants so isolation is the default.
- **Flagged exposure.** *Context:* introducing or restricting capability. Control exposure
  through feature flags rather than through change to what is built.

## Anti-patterns

- **Workload execution in the control plane.** *Why it fails:* running business work in the
  governance plane collapses the boundary and duplicates the runtime. *Instead:* govern, do
  not execute.
- **Hard-coded governance.** *Why it fails:* governance embedded in what is built cannot be
  adjusted or audited. *Instead:* express governance as configuration and policy.
- **Tenant leakage.** *Why it fails:* shared state or permissions across tenants breaks
  isolation and trust. *Instead:* isolate tenants.
- **Redefining security.** *Why it fails:* restating the security model here duplicates and
  will diverge from its owner. *Instead:* apply the security model, do not define it.

## Best Practices

- Keep the control plane strictly to governing and operating; delegate execution to the
  runtime.
- Express platform behavior as configuration, policy, quotas, and feature flags.
- Scope governance to tenants by default under multi-tenancy.
- Govern identity and authorization operationally, applying the principles owned by
  [Chapter 15](../15-security/).
- Delegate the persistence of configuration, policy, and audit data to the
  [data plane](../12-data-platform/CHAPTER.md).

## Examples

The following are illustrative, non-executable aids.

**Governance mechanisms and what they control:**

| Mechanism | What it governs |
|-----------|-----------------|
| Configuration / platform configuration | How the platform behaves, as declared state |
| Policies | What is permitted across the platform |
| Quotas | How much of a resource may be consumed |
| Feature flags | Which capabilities are exposed, and to whom |
| Multi-tenancy | Separation and fairness across tenants |

**Governance versus execution (illustrative):** the control plane decides that a tenant may
run a certain kind of work, within certain limits; the runtime is what actually runs it. The
control plane never performs the work itself.

## Checklist

A reader is ready to proceed to
[Chapter 12 — Data Platform](../12-data-platform/CHAPTER.md) when they can confirm:

- [ ] I can explain what the control plane governs and why it never executes workloads.
- [ ] I can distinguish platform, operational, and configuration governance.
- [ ] I can reason about multi-tenancy, quotas, and feature flags.
- [ ] I understand the split between governing identity and authorization here and the
  security model owned by Chapter 15.

## References

- [Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md) — the frame
  that places the control plane.
- [Chapter 07 — Runtime Platform](../07-runtime-platform/CHAPTER.md) — executes the workloads
  the control plane governs but never runs.
- [Chapter 09 — Provider Platform](../09-provider-platform/CHAPTER.md) — owns routing
  policies, distinct from governance policies.
- [Chapter 12 — Data Platform](../12-data-platform/CHAPTER.md) — persists configuration,
  policy, and audit data.
- [Chapter 15 — Security](../15-security/) — owns the security model that identity and
  authorization apply.
- [Glossary](../21-glossary/) — canonical terms used in this chapter.

## Summary

The control plane governs and operates the platform: it sets the rules through platform and
operational governance, expresses them as configuration, policies, quotas, and feature
flags, structures shared operation through multi-tenancy, and governs identity and
authorization — applying, not defining, the security model owned by Chapter 15. Its defining
boundary is that it manages the platform but never executes business workloads. The next
chapter, [Chapter 12 — Data Platform](../12-data-platform/CHAPTER.md), defines how the
platform's information is persisted.
