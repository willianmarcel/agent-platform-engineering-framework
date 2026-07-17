# Procedure — Security Review

A repeatable procedure for reviewing a design or change for security risk before it ships. It
operationalizes the security principles owned by
[Chapter 15 — Security](../../handbook/15-security/CHAPTER.md) and is a **blocking** review: a design
with an unresolved high security risk does not pass. It is technology-neutral and describes method,
not tooling.

## Trigger
Run this review when: a design handles identity, authorization, secrets, or sensitive data; a change
crosses a trust boundary or exposes a new interface; or an architecture review routes a
security-relevant proposal here.

## Inputs
- The design or change under review, with its data flows and trust boundaries.
- The security principles and their operational split from
  [Chapter 15](../../handbook/15-security/CHAPTER.md).
- Relevant security specifications ([`specifications/security/`](../../specifications/security/)) and
  [ADRs](../../adrs/).

## Steps
1. **Map assets and boundaries.** Identify what is protected, the trust boundaries, and the actors.
2. **Identify threats.** Enumerate threats against each boundary (spoofing, tampering, disclosure,
   denial, elevation), reasoned at architectural altitude.
3. **Assess controls.** For each significant threat, evaluate whether the design's controls are
   adequate — identity, authorization, data protection, isolation, and auditability.
4. **Rate residual risk.** Assign each unresolved threat a severity; a high residual risk is blocking.
5. **Confirm decisions.** Verify security-significant choices are recorded as
   [ADRs](../../adrs/) and traced to the security specifications.
6. **Decide.** Record the outcome, the residual-risk register, and required remediations.

## Decision criteria
Approve only when no unremediated **high** residual risk remains and controls are adequate for the
assessed threats. Otherwise block with required remediations, or escalate per the
[Escalation Policy](../../governance/ARCHITECTURE_ESCALATION.md).

## Outputs
- A decision: **approved**, **blocked (with remediations)**, or **escalated**.
- A residual-risk register with severities.
- Any new or updated security [ADRs](../../adrs/).

## Gates enforced
Quality Gate [G-8 Consistency](../../bootstrap/QUALITY_GATES.md) with the security principles; the
security dimension of the [Review Framework](../../execution/REVIEW_FRAMEWORK.md) (blocking).

## Relationships
- Owned concepts: [Chapter 15 — Security](../../handbook/15-security/CHAPTER.md).
- Invoked from the [Architecture Review](../architecture-review/PROCEDURE.md) and required by the
  [Release Review](../release-review/PROCEDURE.md).
