# APEF v1.0 — Release Candidate Package

The manifest of the Agent Platform Engineering Framework Release Candidate for v1.0. It
enumerates what the release comprises and its state. This package does not perform a commit,
tag, or publication; those await the Architecture Board's final decision (commits remain gated
by OD-6 until Publication Readiness is approved).

## Release identity

- **Name:** Agent Platform Engineering Framework (APEF)
- **Version:** v1.0 (Release Candidate)
- **Nature:** an engineering framework — methodology, knowledge, execution, specification, and
  governance — for building enterprise-grade AI Agent Platforms. Contains no application code,
  no executable automation, and no technology prescription.

## Contents

| Component | State | Entry point |
|-----------|-------|-------------|
| Foundation (repository structure) | Frozen (Foundation v1.0.0) | [Foundation Completion](../bootstrap/FOUNDATION_COMPLETE.md) |
| Governance (bootstrap + Architecture Package) | Ratified | [Master Plan](../bootstrap/MASTER_PLAN.md), [Charter](../governance/ARCHITECTURE_CHARTER.md) |
| Documentation Conventions | Normative (OD-3) | [Documentation Conventions](../governance/DOCUMENTATION_CONVENTIONS.md) |
| Handbook (22 chapters + model + diagrams) | Frozen (per completion records) | [Handbook Summary](../handbook/HANDBOOK_SUMMARY.md) |
| Platform Capability Model | Canonical | [PCM](../handbook/PLATFORM_CAPABILITY_MODEL.md) |
| Execution Framework | Delivered | [Execution Framework](../execution/EXECUTION_FRAMEWORK.md) |
| Specification Framework & Library | Delivered | [Specification Framework](../specifications/SPECIFICATION_FRAMEWORK.md) |
| Reference studies (10) | Approved | [Reference Index](../reference/REFERENCE_INDEX.md) |
| Worked examples (6) | Approved | [Examples Index](../examples/EXAMPLES_INDEX.md) |
| Publication artifacts | This package | [Framework Map](FRAMEWORK_MAP.md) |

## Statistics

- 438 documents; 214 directories.
- 22 chapters; 220 concepts (single-owned); 12 specification libraries; 10 studies; 6 example
  areas.
- 3,310 internal links, all resolving; 22/22 chapters template-conformant; 0 stray placeholders.

## Quality attestations

- Handbook consistency ✅ · Concept Ownership ✅ · Traceability ✅ · Architectural consistency ✅ ·
  Documentation standard ✅ · Technology / vendor / framework neutrality ✅ (with the single
  documented Chapter-00 analogy).

## Ready-structure (post-1.0 evolution)

By design, the following areas are delivered as ready structure with contract READMEs, to be
populated through use in Phase 5 (Evolution): `playbooks/` procedures, `adrs/` records,
`templates/` specialized forms beyond those delivered, `architecture/` diagram instances,
`assets/`, and `scripts/`. These are the framework's designed extensibility, not gaps in it.

## Outstanding

- **OD-4** — deferred to Release 1.1 (single authoritative home for the mandated architectural
  principles). Not a v1.0 blocker.
- **OD-6** — commits remain deferred until the Board approves Publication Readiness; on approval,
  the accumulated approved work (Handbook v1.0, Execution Framework, Specification Library,
  Reference, Examples, and this package) can be committed as clean, sequenced logical commits.

## Release action (pending Board decision)

On the Architecture Board's approval of Publication Readiness, and per the
[Version Control Policy](../governance/VERSION_CONTROL_POLICY.md) (one approved milestone → one
commit; tags only at publication milestones), the release actions are: lift OD-6; commit the
accumulated approved milestones as **one logical commit per milestone** (Handbook v1.0, Execution
Framework, Specification Framework, Specification Library, Reference Studies, Worked Examples, and
Publication Readiness), each traceable to its Board approval; and tag **APEF v1.0** at this
publication milestone. The Architecture Team will perform these only on explicit Board
authorization.
