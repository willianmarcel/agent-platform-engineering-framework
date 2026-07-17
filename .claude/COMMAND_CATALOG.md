# Command Catalog

Commands are the repeatable engineering activities of the APEF Execution Framework. Each is
defined as a **contract** — purpose, inputs, outputs, and execution flow — not as
implementation. Every command derives its authority from the Handbook chapter that owns its
concern, is executed by one or more [skills](SKILL_CATALOG.md) under a
[prompt contract](EXECUTION_FRAMEWORK.md#prompt-contracts), and admits its output only when
the applicable [reviews](REVIEW_FRAMEWORK.md) and [quality gates](QUALITY_GATES.md) pass.

Commands do not implement platform code, write CLI scripts, or create executable automation.

## Command contract structure

Each command below states: **Purpose**, **Inputs**, **Outputs**, **Execution flow**,
**Primary skills**, **Reviews & gates**, and **Handbook authority**.

---

## `init-project`

- **Purpose:** Establish a new engineering effort with the structure, conventions, and
  governance the framework requires.
- **Inputs:** The intent for the effort; the Handbook; the repository conventions.
- **Outputs:** An initialized project structure and the initial governance artifacts
  (conventions, decision log location, workflow selection).
- **Execution flow:** Frame the effort → select the applicable workflow → establish structure
  and conventions → record the initialization decision.
- **Primary skills:** Enterprise Architect, Platform Architect.
- **Reviews & gates:** Documentation review; Foundation-consistency gate.
- **Handbook authority:** [00 Introduction](../handbook/00-introduction/CHAPTER.md),
  [06 Reference Architecture](../handbook/06-reference-architecture/CHAPTER.md).

## `discover-domain`

- **Purpose:** Model the problem domain and establish its bounded contexts and ubiquitous
  language before specification.
- **Inputs:** The problem context; stakeholder knowledge; the vision.
- **Outputs:** A domain model — bounded contexts, ubiquitous language, key events — as
  specification input.
- **Execution flow:** Explore the domain → identify bounded contexts → establish ubiquitous
  language → surface domain events → record the model.
- **Primary skills:** Domain Expert, Product Architect.
- **Reviews & gates:** Domain review; terminology-consistency gate.
- **Handbook authority:** [05 Domain-Driven Design](../handbook/05-domain-driven-design/CHAPTER.md).

## `write-spec`

- **Purpose:** Capture intent as a normative specification before implementation.
- **Inputs:** The domain model; the capability or need; the applicable templates.
- **Outputs:** A specification satisfying its acceptance criteria, authored from the
  specification template.
- **Execution flow:** State intent → define scope and acceptance criteria → capture
  constraints → record significant decisions as ADRs → produce the specification.
- **Primary skills:** Product Architect, Domain Expert, relevant plane architect.
- **Reviews & gates:** Product review; Domain review; specification-completeness gate.
- **Handbook authority:** [04 Development Methodology](../handbook/04-development-methodology/CHAPTER.md).

## `review-spec`

- **Purpose:** Verify that a specification is complete, consistent, and faithful to intent
  before architecture or implementation proceeds.
- **Inputs:** A specification; the vision and domain model; the review framework.
- **Outputs:** A review verdict with findings, and an accepted or returned specification.
- **Execution flow:** Check against acceptance criteria → check ownership and terminology →
  check feasibility → record findings and verdict.
- **Primary skills:** Product Architect, Enterprise Architect.
- **Reviews & gates:** Product review; Domain review; specification-completeness gate.
- **Handbook authority:** [04 Development Methodology](../handbook/04-development-methodology/CHAPTER.md).

## `design-architecture`

- **Purpose:** Produce or extend the architecture that satisfies a specification, consistent
  with the reference architecture.
- **Inputs:** An accepted specification; the reference architecture; the Platform Capability
  Model.
- **Outputs:** Architecture artifacts (views, boundaries, plane placement) and the decisions
  behind them.
- **Execution flow:** Locate concerns in the planes and layers → define boundaries from
  bounded contexts → choose among options against quality attributes → record decisions as
  ADRs.
- **Primary skills:** Platform Architect, Enterprise Architect, Runtime/AI/Security/Observability
  Architect as the concern requires.
- **Reviews & gates:** Architecture review; architectural-consistency gate.
- **Handbook authority:** [06 Reference Architecture](../handbook/06-reference-architecture/CHAPTER.md).

## `write-adr`

- **Purpose:** Record a significant decision — context, options, and consequences — durably.
- **Inputs:** The decision at hand; its context and options; the ADR template.
- **Outputs:** A numbered Architecture Decision Record.
- **Execution flow:** State context → enumerate options → decide → record consequences →
  number and file the ADR.
- **Primary skills:** The architect owning the decision's concern.
- **Reviews & gates:** Architecture review; decision-record gate.
- **Handbook authority:** [04 Development Methodology](../handbook/04-development-methodology/CHAPTER.md).

## `implement-feature`

- **Purpose:** Realize a specified, designed feature to the definition of done. *(Within this
  framework, "implement" means producing the specified engineering artifacts and their
  verification design — not platform application code, which is out of scope.)*
- **Inputs:** An accepted specification and architecture; the definition of done.
- **Outputs:** The feature's engineering artifacts and its verification and evaluation design,
  satisfying the definition of done.
- **Execution flow:** Confirm specification and architecture → produce the artifacts in
  complete increments → design tests and evaluation → satisfy the definition of done.
- **Primary skills:** The relevant plane architect; Code Reviewer; Domain Expert.
- **Reviews & gates:** Architecture, Runtime, Testing reviews; definition-of-done gate.
- **Handbook authority:** [04 Development Methodology](../handbook/04-development-methodology/CHAPTER.md),
  [07 Runtime Platform](../handbook/07-runtime-platform/CHAPTER.md).

## `review-code`

- **Purpose:** Review produced engineering artifacts for correctness, clarity, and
  consistency with principles and architecture.
- **Inputs:** The artifacts under review; the specification and architecture; the review
  framework.
- **Outputs:** A review verdict with findings, and accepted or returned artifacts.
- **Execution flow:** Check against specification and architecture → check principles and
  terminology → check testability → record findings and verdict.
- **Primary skills:** Code Reviewer, relevant plane architect.
- **Reviews & gates:** Architecture, Testing, Documentation reviews; correctness gate.
- **Handbook authority:** [03 Engineering Principles](../handbook/03-engineering-principles/CHAPTER.md),
  [18 Testing](../handbook/18-testing/CHAPTER.md).

## `generate-tests`

- **Purpose:** Design the testing that verifies software correctness for a feature, distinct
  from AI evaluation.
- **Inputs:** The specification and architecture; the feature's artifacts; the testing
  strategy.
- **Outputs:** A test design across the appropriate levels (unit, integration, end-to-end,
  contract), as a test plan — not test code.
- **Execution flow:** Identify what must be verified → place tests on the pyramid → design
  contract and regression coverage → record the test design.
- **Primary skills:** Code Reviewer, Runtime Architect.
- **Reviews & gates:** Testing review; test-coverage gate.
- **Handbook authority:** [18 Testing](../handbook/18-testing/CHAPTER.md); AI quality is
  evaluated separately per [16 Evaluation](../handbook/16-evaluation/CHAPTER.md).

## `security-review`

- **Purpose:** Review a specification, architecture, or change for security risk against the
  platform's security principles.
- **Inputs:** The artifact under review; the security principles and trust model; the review
  framework.
- **Outputs:** A security review verdict with findings and required mitigations.
- **Execution flow:** Threat-model the change → check against zero trust and defense in depth
  → check secrets, privacy, and compliance → record findings and severity.
- **Primary skills:** Security Architect.
- **Reviews & gates:** Security review; security gate.
- **Handbook authority:** [15 Security](../handbook/15-security/CHAPTER.md); operational
  identity and authorization per [11 Control Plane](../handbook/11-control-plane/CHAPTER.md).

## `release`

- **Purpose:** Prepare and reason about a release consistent with the release philosophy and
  operational readiness.
- **Inputs:** The change set; the evolution and release philosophy; operational readiness
  criteria.
- **Outputs:** A release decision with its readiness assessment and release notes.
- **Execution flow:** Verify quality gates → assess operational readiness → check backward
  compatibility and versioning → decide and record the release.
- **Primary skills:** Platform Architect, Observability Architect, Security Architect.
- **Reviews & gates:** Full review pipeline; release-readiness gate.
- **Handbook authority:** [19 DevOps](../handbook/19-devops/CHAPTER.md),
  [20 Roadmap](../handbook/20-roadmap/CHAPTER.md).

---

## Command summary

| Command | Primary concern | Handbook chapter |
|---------|-----------------|------------------|
| init-project | Project establishment | 00, 06 |
| discover-domain | Domain modeling | 05 |
| write-spec | Specification | 04 |
| review-spec | Specification review | 04 |
| design-architecture | Architecture | 06 |
| write-adr | Decision record | 04 |
| implement-feature | Realization to done | 04, 07 |
| review-code | Artifact review | 03, 18 |
| generate-tests | Test design | 18 |
| security-review | Security review | 15 |
| release | Release preparation | 19, 20 |
