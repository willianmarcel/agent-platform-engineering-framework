# Repository Guide

The Repository Guide explains how the APEF repository is organized and where each kind of content
belongs. It gives contributors a single, authoritative map so that every artifact has one correct
home and the repository stays navigable as it grows. It describes structure and placement rules
only; it prescribes no technology.

The repository topology itself is a Board matter (per the
[Architecture Charter](../governance/ARCHITECTURE_CHARTER.md)); this guide documents that
topology and the rules for working within it.

## Repository map

| Directory | Holds | Entry point |
|-----------|-------|-------------|
| `bootstrap/` | The governing plan and engineering guides — the framework's constitution and how-to. | [`MASTER_PLAN.md`](MASTER_PLAN.md) |
| `governance/` | The Architecture Governance Package (Charter, Board, Operating Model, Escalation, Team Rules, Version Control Policy, Documentation Conventions). | [`../governance/README.md`](../governance/README.md) |
| `handbook/` | The 22-chapter Engineering Handbook — the normative body of knowledge and concept owner. | [`../handbook/HANDBOOK_SUMMARY.md`](../handbook/HANDBOOK_SUMMARY.md) |
| `.claude/` | The Execution Framework — commands, skills, workflows, review framework, execution gates. | [`../.claude/EXECUTION_FRAMEWORK.md`](../.claude/EXECUTION_FRAMEWORK.md) |
| `specifications/` | The Specification Framework and the 12-area Specification Library. | [`../specifications/SPECIFICATION_FRAMEWORK.md`](../specifications/SPECIFICATION_FRAMEWORK.md) |
| `adrs/` | Architecture Decision Records and the ADR engineering framework. | [`../adrs/README.md`](../adrs/README.md) |
| `architecture/` | Diagram-as-code architecture instances (ready-structure). | [`../architecture/README.md`](../architecture/README.md) |
| `playbooks/` | Repeatable operational procedures (ready-structure). | [`../playbooks/README.md`](../playbooks/README.md) |
| `templates/` | Reusable document templates. | [`../templates/README.md`](../templates/README.md) |
| `reference/` | Educational studies of external technologies (analysis, not prescription). | [`../reference/REFERENCE_INDEX.md`](../reference/REFERENCE_INDEX.md) |
| `examples/` | Non-executable worked examples (technology-neutral). | [`../examples/EXAMPLES_INDEX.md`](../examples/EXAMPLES_INDEX.md) |
| `docs/` | Framework-level publication and assessment artifacts. | [`../docs/FRAMEWORK_MAP.md`](../docs/FRAMEWORK_MAP.md) |
| `assets/` | Rendered diagram exports and static assets (ready-structure). | [`../assets/README.md`](../assets/README.md) |
| `scripts/` | Placement reserved by structure; executable automation is out of scope. | [`../scripts/README.md`](../scripts/README.md) |

## Where content belongs

- **Durable knowledge** (concepts, principles, architecture, patterns) → the owning Handbook
  chapter. Nothing else defines a concept.
- **Intent to be realized** (vision, discovery, capability, domain, requirement, release) → the
  matching Specification Library area.
- **A decision of architectural significance** → an ADR in `adrs/`.
- **How work is executed** (a command, role, workflow, or gate) → `.claude/`.
- **Analysis of an external technology** → `reference/` (never the Handbook or examples).
- **An illustrative, neutral walk-through** → `examples/`.
- **A reusable form** → `templates/`; **a repeatable procedure** → `playbooks/`.
- **A framework-wide report** (map, index, assessment, readiness) → `docs/`.

If a candidate artifact seems to fit two homes, it usually means it mixes two concerns — split it,
and place each part with its owner.

## Naming, numbering, and cross-linking

- **READMEs** follow the eight-section contract (AD-0001) and act as the frozen directory entry
  under the Module Entry Pattern; authoritative content lives in named entry documents beside them.
- **Numbering** is zero-padded and stable (Handbook chapters `00`–`21`; ADRs `NNNN`). Numbers are
  never reused or renumbered once assigned.
- **Naming** is descriptive and consistent within a module; directory names state a single
  responsibility (no catch-all names).
- **Cross-linking** is by relative path; a reference points to the owner rather than restating it;
  all internal links must resolve.

These rules are the repository expression of the
[Documentation Conventions](../governance/DOCUMENTATION_CONVENTIONS.md).

## Adding a new directory or artifact type

A new top-level directory changes the repository topology and is therefore a Board decision,
recorded as an ADR. Within an existing module, adding a new artifact type requires: a clear single
responsibility, a contract README if it is a new directory, placement consistent with the rules
above, and — where the addition reflects an architecturally significant choice — a corresponding
ADR. Ready-structure directories are populated through use; populating them follows the same
placement and README rules.

## Relationships

- Operationalizes the structure defined in [`MASTER_PLAN.md`](MASTER_PLAN.md).
- Complements [`ENGINEERING_GUIDE.md`](ENGINEERING_GUIDE.md) (how to work) and is applied through
  [`WORKFLOW.md`](WORKFLOW.md) (when).
- Governed by the [Architecture Charter](../governance/ARCHITECTURE_CHARTER.md) for topology
  changes and the [Documentation Conventions](../governance/DOCUMENTATION_CONVENTIONS.md) for
  placement and structure.
