# Release Process

The Release Process defines how versions of APEF are cut, reviewed, published, and communicated.
Because APEF is a documentation and engineering framework, a "release" is a versioned, coherent
state of its guidance — not a software build. This document describes the release methodology; it
prescribes no tooling.

## What a release is

A release is a named, immutable snapshot of the framework's guidance that adopters can depend on.
Between releases, the framework evolves through approved milestones; a release consolidates one or
more approved milestones into a coherent, published version.

## Versioning

APEF uses Semantic Versioning applied to *guidance*:

- **Major (`X.0.0`)** — a breaking change to guidance: a concept is redefined or moved to a new
  owner, a mandated principle changes, the repository topology changes in a way adopters depend on,
  or previously required practice is removed. Breaking changes are introduced only through ratified
  decisions and are recorded as superseding ADRs.
- **Minor (`x.Y.0`)** — additive, backward-compatible guidance: new chapters, new specification
  areas, new studies or examples, new ADRs that do not invalidate prior ones.
- **Patch (`x.y.Z`)** — corrections that do not change meaning: fixed links, clarified wording,
  typographical and editorial repairs.

## Preparing a release

1. **Freeze scope.** Identify the approved milestones the release consolidates. Only Board-approved
   work is eligible; nothing enters a release without its milestone approval.
2. **Verify the gates.** Every gate in [`QUALITY_GATES.md`](QUALITY_GATES.md) must pass across the
   release scope — completeness, single-ownership, link integrity, neutrality, traceability,
   decision integrity, and consistency. A release cannot be cut over a failing gate.
3. **Run the release review.** Conduct the review using the
   [release-review playbook](../playbooks/release-review/) and the multi-perspective review model.
   The review confirms internal consistency and produces the release's architecture review.
4. **Record the changes.** Update [`../CHANGELOG.md`](../CHANGELOG.md) with the release's additions,
   changes, and any breaking changes, each traceable to its milestone and ADRs.
5. **Confirm the roadmap position.** Ensure the release aligns with the phasing in
   [`ROADMAP.md`](ROADMAP.md).

## Approval, versioning control, and tagging

Releases follow the [Version Control Policy](../governance/VERSION_CONTROL_POLICY.md):

- Committing and tagging are **gated on Board approval**. Approved work is committed as **one
  logical commit per milestone**, each traceable to its approval.
- A **tag** is applied only at a publication milestone, naming the release version (for example,
  `APEF vX.Y`).
- The [Architecture Board](../governance/ARCHITECTURE_BOARD.md) renders the final release
  decision; the Architecture Team performs the commit and tag actions only on explicit
  authorization.

## Publishing and communicating

The published version is recorded under [`../docs/`](../docs/) via the release's manifest and
architecture review (the Release Candidate package is the template for this). The CHANGELOG is the
authoritative communication of what changed and whether any change is breaking; adopters use it and
the Semantic Version to judge the impact of upgrading.

## Relationships

- Consumes the outputs of [`QUALITY_GATES.md`](QUALITY_GATES.md); a passing gate set is a
  precondition.
- Follows the phasing in [`ROADMAP.md`](ROADMAP.md) and is driven by the
  [Version Control Policy](../governance/VERSION_CONTROL_POLICY.md).
- Pairs with the [release-review playbook](../playbooks/release-review/) and is triggered from the
  end of the [`WORKFLOW.md`](WORKFLOW.md) contribution flow.
