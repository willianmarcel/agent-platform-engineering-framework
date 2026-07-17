# EC-2 — Playbooks Report (Objective 2)

Records which playbooks were produced and why, ratified as
[ADR-0008](../../adrs/decisions/0008-necessary-operational-playbooks.md). The directive was to produce
*only the playbooks that remain architecturally necessary after the Engineering Assessment*.

## Selection principle

The review *model* is already delivered in the Execution and Specification frameworks. A playbook is
architecturally necessary only where it (a) operationalizes a framework-level gate the framework
itself defines and references, and (b) can be executed without a running platform. Playbooks that
assess a running platform's live behavior are adopter-operational Phase-5 content.

## Produced — the three necessary procedures

| Playbook | Operationalizes | Procedure |
|----------|-----------------|-----------|
| Architecture Review | Charter authority + ADR review criteria | [PROCEDURE](../../playbooks/architecture-review/PROCEDURE.md) |
| Security Review (blocking) | Chapter 15 security principles + blocking security dimension | [PROCEDURE](../../playbooks/security-review/PROCEDURE.md) |
| Release Review | The Release Process + all eight Quality Gates | [PROCEDURE](../../playbooks/release-review/PROCEDURE.md) |

Each defines trigger, inputs, steps, decision criteria, outputs, and the gates it enforces; the three
interlink (architecture → security → release).

## Deferred — platform-operation reviews (Phase 5)

`production-readiness`, `performance-review`, `observability-review`, and `incident-review` remain
ready-structure (contract README only). They assess a running platform against live targets and
incidents — they require an operating platform to execute and are therefore adopter-instance content
for Phase 5, not framework-level gates. This keeps the framework operationally complete without
over-producing procedures it cannot yet exercise.

## Conformance

Framework- and technology-neutral (verified); no placeholders; all links resolve; procedures added as
entry documents beside frozen READMEs (Module Entry Pattern / ADR-0004); consistent with the Release
Process, the Quality Gates, and the security chapter.

## Result

Objective 2 is complete: the three architecturally necessary review procedures are operational; the
four platform-operation reviews are explicitly and defensibly deferred.
