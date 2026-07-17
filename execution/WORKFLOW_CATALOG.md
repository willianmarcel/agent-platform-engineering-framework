# Workflow Catalog

Workflows are the end-to-end engineering processes of the APEF Execution Framework. Each
orchestrates [commands](COMMAND_CATALOG.md) executed by [skills](SKILL_CATALOG.md), advancing
through stages only when the relevant [reviews](REVIEW_FRAMEWORK.md) and
[quality gates](QUALITY_GATES.md) pass. Workflows define process, not implementation.

Each workflow states: **Purpose**, **Stages** (command · skills · gate), and **Exit
criteria**.

---

## Greenfield development

- **Purpose:** Take a new AI Agent Platform effort from intent to a first realized, verified
  capability.
- **Stages:**
  1. `init-project` · Enterprise + Platform Architect · *Foundation-consistency gate*
  2. `discover-domain` · Domain Expert + Product Architect · *terminology gate*
  3. `write-spec` → `review-spec` · Product Architect + Domain Expert · *specification-completeness gate*
  4. `design-architecture` (+ `write-adr`) · Platform + specialist architects · *architectural-consistency gate*
  5. `implement-feature` + `generate-tests` · plane architect + Code Reviewer · *definition-of-done gate*
  6. `security-review` · Security Architect · *security gate*
  7. `release` · Platform + Observability Architect · *release-readiness gate*
- **Exit criteria:** A specified, designed, realized, verified, and reviewed first capability,
  released per the release-readiness gate.

## New feature

- **Purpose:** Add a capability to an existing platform, consistent with its architecture.
- **Stages:**
  1. `write-spec` → `review-spec` · Product Architect + Domain Expert · *specification-completeness gate*
  2. `design-architecture` (if structure changes; + `write-adr`) · Platform Architect · *architectural-consistency gate*
  3. `implement-feature` + `generate-tests` · plane architect + Code Reviewer · *definition-of-done gate*
  4. `review-code` · Code Reviewer · *correctness gate*
  5. `security-review` · Security Architect · *security gate*
- **Exit criteria:** The feature satisfies its specification and the definition of done, passes
  code and security review, and is ready to release.

## Architectural refactoring

- **Purpose:** Change the platform's structure to improve it without changing external
  behavior, preserving coherence.
- **Stages:**
  1. `write-adr` (motivating decision) · Platform + Enterprise Architect · *decision-record gate*
  2. `design-architecture` · Platform + affected specialist architects · *architectural-consistency gate*
  3. `implement-feature` (structure change) + `generate-tests` (regression) · plane architects + Code Reviewer · *definition-of-done gate; regression coverage*
  4. `review-code` · Code Reviewer + Enterprise Architect · *correctness gate; coherence*
- **Exit criteria:** The structure is improved, external behavior is preserved (regression
  verified), coherence is maintained, and decisions are recorded.

## Bug fixing

- **Purpose:** Correct a defect while protecting against recurrence.
- **Stages:**
  1. Diagnose · Runtime/relevant architect + Observability Architect · *(diagnosis grounded in
     observability signals)*
  2. `generate-tests` (a failing regression case first) · Code Reviewer · *regression coverage gate*
  3. `implement-feature` (the fix) · plane architect · *definition-of-done gate*
  4. `review-code` · Code Reviewer · *correctness gate*
  5. `security-review` (if the defect has security impact) · Security Architect · *security gate*
- **Exit criteria:** The defect is corrected, a regression test guards it, and review passes;
  a defect with security impact clears the security gate.

## Release preparation

- **Purpose:** Bring a change set to a considered, ready release.
- **Stages:**
  1. Verify the full [review pipeline](REVIEW_FRAMEWORK.md) · all review skills · *all
     dimension gates*
  2. `security-review` · Security Architect · *security gate*
  3. Assess operational readiness · Observability Architect · *operational-readiness gate*
  4. `release` · Platform Architect · *release-readiness gate*
- **Exit criteria:** Every review dimension and quality gate passes, operational readiness is
  confirmed, backward compatibility and versioning are honored, and the release decision is
  recorded.

---

## Workflow selection

| Situation | Workflow |
|-----------|----------|
| A new platform effort | Greenfield development |
| A new capability on an existing platform | New feature |
| Improving structure without changing behavior | Architectural refactoring |
| Correcting a defect | Bug fixing |
| Readying a change set for release | Release preparation |

Every workflow is specification-driven, gates each stage before progressing, and derives its
authority from the Handbook — principally
[Chapter 04 — Development Methodology](../handbook/04-development-methodology/CHAPTER.md).
