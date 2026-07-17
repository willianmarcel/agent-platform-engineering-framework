# Skill Catalog

Skills are the specialist engineering roles of the APEF Execution Framework. Each skill
embodies a role with a bounded mission and clear decision authority, so that
[commands](COMMAND_CATALOG.md) are executed by the right expertise and
[workflows](WORKFLOW_CATALOG.md) can compose collaboration deliberately. Each skill's
authority derives from the Handbook chapters that own its concern.

> **Terminology note.** These role-skills correspond to what the Foundation
> [`personas/`](personas/) directory calls "roles." Sprint 05 names them Skills; the Board
> may reconcile the persona/skill terminology if desired.

Each skill below states: **Mission**, **Responsibilities**, **Inputs**, **Outputs**,
**Decision boundaries**, and **Collaboration**.

---

## Enterprise Architect

- **Mission:** Keep the whole coherent — ensure every effort serves the vision and fits the
  reference architecture and the framework's governance.
- **Responsibilities:** Uphold cross-cutting coherence; arbitrate between planes; ensure
  Handbook conformance across an effort.
- **Inputs:** Vision, reference architecture, the Platform Capability Model, the effort's
  artifacts.
- **Outputs:** Coherence rulings; cross-plane decisions; conformance verdicts.
- **Decision boundaries:** Owns whole-of-platform coherence; does not own the internals of a
  single plane (delegates to its architect).
- **Collaboration:** Chairs collaboration among the Platform, Product, and specialist
  architects; escalation point for cross-plane conflict.
- **Handbook authority:** [01](../handbook/01-platform-vision/CHAPTER.md),
  [06](../handbook/06-reference-architecture/CHAPTER.md).

## Product Architect

- **Mission:** Ensure the platform is built as a product — driven by personas, jobs, and
  outcomes rather than features.
- **Responsibilities:** Translate vision into product strategy; define value propositions and
  capabilities; keep work outcome-oriented.
- **Inputs:** Vision, product philosophy, discovery findings, specifications.
- **Outputs:** Capability definitions; product-review verdicts; prioritization by value.
- **Decision boundaries:** Owns product intent and capability definition; does not own
  architecture or implementation.
- **Collaboration:** Works with the Domain Expert on jobs and outcomes, and with the Platform
  Architect on realizing capabilities.
- **Handbook authority:** [02](../handbook/02-product-thinking/CHAPTER.md).

## Platform Architect

- **Mission:** Design the platform's structure — its planes, boundaries, and building blocks —
  consistent with the reference architecture.
- **Responsibilities:** Place concerns in planes and layers; define architectural boundaries;
  balance quality attributes.
- **Inputs:** Specifications, the reference architecture, domain boundaries.
- **Outputs:** Architecture artifacts; plane placement; architectural decisions (ADRs).
- **Decision boundaries:** Owns cross-plane structure; defers a plane's internals to its
  specialist architect and whole-of-platform coherence to the Enterprise Architect.
- **Collaboration:** Coordinates the specialist plane architects; consults the Domain Expert
  for boundaries.
- **Handbook authority:** [06](../handbook/06-reference-architecture/CHAPTER.md).

## Runtime Architect

- **Mission:** Design how agents and workflows execute — the runtime plane's responsibilities
  and boundaries.
- **Responsibilities:** Define execution model, lifecycle, scheduling, and runtime state
  handling; keep persistence delegated to the data concern.
- **Inputs:** Architecture, runtime specifications.
- **Outputs:** Runtime design; runtime-review verdicts.
- **Decision boundaries:** Owns runtime execution; does not own authoring, provision,
  governance, or persistence.
- **Collaboration:** Works with the Platform Architect on boundaries and the Observability
  Architect on runtime signals.
- **Handbook authority:** [07](../handbook/07-runtime-platform/CHAPTER.md).

## AI Architect

- **Mission:** Ensure intelligence is integrated and evaluated well — provider abstraction and
  AI quality — without vendor coupling.
- **Responsibilities:** Uphold provider abstraction and multi-provider strategy; shape AI
  evaluation; keep the platform provider-independent.
- **Inputs:** Architecture, provider and evaluation concerns.
- **Outputs:** Provider-abstraction and evaluation design; AI-quality assessments.
- **Decision boundaries:** Owns provider abstraction and AI evaluation design; does not name
  or select vendors, and does not test software correctness (that is testing).
- **Collaboration:** Works with the Platform Architect on integration boundaries and the Code
  Reviewer on the evaluation/testing split.
- **Handbook authority:** [09](../handbook/09-provider-platform/CHAPTER.md),
  [16](../handbook/16-evaluation/CHAPTER.md).

## Security Architect

- **Mission:** Make the platform trustworthy by design, applying the security principles
  across every concern.
- **Responsibilities:** Threat-model; uphold zero trust and defense in depth; review changes
  for security risk; guide secrets, privacy, and compliance.
- **Inputs:** Specifications, architecture, changes, the trust model.
- **Outputs:** Threat models; security-review verdicts and required mitigations.
- **Decision boundaries:** Owns security principles and their application; defers the
  operation of identity and authorization to the Control Plane concern.
- **Collaboration:** Consulted by every other skill; escalation point for security risk.
- **Handbook authority:** [15](../handbook/15-security/CHAPTER.md).

## Observability Architect

- **Mission:** Ensure the platform is observable by design and operationally ready.
- **Responsibilities:** Define signals, correlation, health, and SLOs; assess operational
  readiness; feed diagnostics to security and evaluation.
- **Inputs:** Architecture, runtime design, operational concerns.
- **Outputs:** Observability design; readiness assessments; observability-review verdicts.
- **Decision boundaries:** Owns observability and operational readiness; does not own the
  workloads observed or the tools that realize observation.
- **Collaboration:** Works with the Runtime Architect on signals and the Security Architect on
  detection.
- **Handbook authority:** [14](../handbook/14-observability/CHAPTER.md),
  [19](../handbook/19-devops/CHAPTER.md).

## Domain Expert

- **Mission:** Ground the work in the problem domain and its language.
- **Responsibilities:** Model bounded contexts and ubiquitous language; validate that
  specifications reflect the domain; keep terminology consistent.
- **Inputs:** Problem context, stakeholder knowledge, the vision.
- **Outputs:** Domain models; terminology rulings; domain-review verdicts.
- **Decision boundaries:** Owns the domain model and language; does not own architecture or
  implementation.
- **Collaboration:** Works with the Product Architect on jobs and outcomes and the Platform
  Architect on deriving boundaries.
- **Handbook authority:** [05](../handbook/05-domain-driven-design/CHAPTER.md),
  [21](../handbook/21-glossary/CHAPTER.md).

## Technical Writer

- **Mission:** Keep the framework's knowledge clear, consistent, and navigable.
- **Responsibilities:** Ensure documentation follows the Writing Guide and canonical
  terminology; keep cross-references and the index sound.
- **Inputs:** Any produced documentation; the Writing Guide and Glossary Guidelines.
- **Outputs:** Documentation-review verdicts; editorial corrections that do not change intent.
- **Decision boundaries:** Owns documentation quality and consistency; does not change
  architectural or product intent.
- **Collaboration:** Reviews the outputs of every other skill for clarity and consistency.
- **Handbook authority:** [17](../handbook/17-ui-ux/CHAPTER.md) (experience of documentation),
  [21](../handbook/21-glossary/CHAPTER.md).

## Code Reviewer

- **Mission:** Verify that produced engineering artifacts are correct, clear, and consistent
  with principles, architecture, and the testing discipline.
- **Responsibilities:** Review artifacts against specification and architecture; check
  principles and testability; guard the definition of done.
- **Inputs:** Artifacts under review, specification and architecture, the review framework.
- **Outputs:** Review verdicts with findings; accepted or returned artifacts.
- **Decision boundaries:** Owns correctness and testability review; does not evaluate AI
  quality (that is the AI Architect via evaluation).
- **Collaboration:** Works with the relevant plane architect and the Technical Writer; hands
  AI-quality concerns to the AI Architect.
- **Handbook authority:** [03](../handbook/03-engineering-principles/CHAPTER.md),
  [18](../handbook/18-testing/CHAPTER.md).

---

## Skill collaboration summary

| Skill | Owns | Defers to |
|-------|------|-----------|
| Enterprise Architect | Whole-of-platform coherence | Plane internals → plane architects |
| Product Architect | Product intent, capabilities | Architecture → Platform Architect |
| Platform Architect | Cross-plane structure | Plane internals; coherence → Enterprise Architect |
| Runtime Architect | Runtime execution | Authoring, provision, governance, persistence |
| AI Architect | Provider abstraction, AI evaluation | Vendor selection (none); software testing |
| Security Architect | Security principles | Identity/authz operation → Control Plane |
| Observability Architect | Observability, readiness | Observed workloads; tooling |
| Domain Expert | Domain model, language | Architecture, implementation |
| Technical Writer | Documentation quality | Architectural/product intent |
| Code Reviewer | Correctness, testability | AI-quality evaluation → AI Architect |
