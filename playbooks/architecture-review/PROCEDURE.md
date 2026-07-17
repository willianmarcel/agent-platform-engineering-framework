# Procedure — Architecture Review

A repeatable procedure for reviewing an architecture proposal or model against the framework's
principles, constraints, and decisions. It operationalizes the governance authority of the
[Architecture Charter](../../governance/ARCHITECTURE_CHARTER.md) and the decision review criteria of
[ADR Governance](../../adrs/ADR_GOVERNANCE.md). It is technology-neutral and describes method, not
tooling.

## Trigger
Run this review when: a new architecture proposal is raised; an architecturally significant change is
proposed (per the [ADR significance threshold](../../adrs/ADR_FRAMEWORK.md)); or a milestone requires
an architecture sign-off.

## Inputs
- The proposal or model under review, with its context.
- The governing Handbook chapters (especially [Chapter 06](../../handbook/06-reference-architecture/CHAPTER.md)
  and the [Platform Capability Model](../../handbook/PLATFORM_CAPABILITY_MODEL.md)).
- Any related specifications and existing [ADRs](../../adrs/).

## Steps
1. **Frame.** Confirm the proposal's scope, the problem it addresses, and the decision(s) it implies.
2. **Check altitude.** Verify the proposal is at architectural altitude — the *what/why*, not
   implementation *how*; no technology or vendor prescribed.
3. **Check consistency.** Verify alignment with the Reference Architecture, the Platform Capability
   Model, concept ownership, and every Accepted ADR. Flag any contradiction.
4. **Check decisions.** Identify architecturally significant choices; confirm each is recorded (or
   proposed) as an [ADR](../../adrs/) with sound context, options, and consequences.
5. **Check cross-cutting impact.** Assess effects on security, observability, and user experience;
   route to the [security review](../security-review/PROCEDURE.md) when security-relevant.
6. **Assess trade-offs.** Weigh the options and their consequences; confirm the chosen option is
   justified.
7. **Decide.** Record the outcome and rationale.

## Decision criteria
Approve when the proposal is at correct altitude, consistent with the framework and all Accepted
ADRs, has its significant decisions recorded, and its trade-offs are justified. Otherwise request
changes or escalate per the [Escalation Policy](../../governance/ARCHITECTURE_ESCALATION.md).

## Outputs
- A decision: **approved**, **changes requested**, or **escalated**, with rationale.
- Any new or updated [ADRs](../../adrs/) the review requires.
- A record suitable for the milestone's architecture review.

## Gates enforced
Quality Gates [G-6 Traceability, G-7 Decision integrity, G-8 Consistency](../../bootstrap/QUALITY_GATES.md);
the review dimensions of the [Review Framework](../../execution/REVIEW_FRAMEWORK.md).

## Relationships
- Authority: [Architecture Charter](../../governance/ARCHITECTURE_CHARTER.md),
  [Architecture Board](../../governance/ARCHITECTURE_BOARD.md).
- Feeds the [Release Review](../release-review/PROCEDURE.md) and the
  [Release Process](../../bootstrap/RELEASE_PROCESS.md).
