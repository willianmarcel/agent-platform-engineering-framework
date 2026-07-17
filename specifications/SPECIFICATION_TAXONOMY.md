# Specification Taxonomy

The canonical categories of specification in the APEF. Every specification is of exactly one category, and each category has a single owning Handbook chapter and review authority. This is part of the [Specification Framework](SPECIFICATION_FRAMEWORK.md); ownership and authority are governed by [Specification Governance](SPECIFICATION_GOVERNANCE.md).

There are **22** canonical specification categories.

## Category summary

| # | Category | Owning chapter | Review authority |
|---|----------|----------------|------------------|
| 1 | Product Specification | [02](../handbook/02-product-thinking/CHAPTER.md) | Product |
| 2 | Business Capability Specification | [02](../handbook/02-product-thinking/CHAPTER.md) | Product |
| 3 | Functional Specification | [02](../handbook/02-product-thinking/CHAPTER.md) | Product |
| 4 | Non-Functional Specification | [06](../handbook/06-reference-architecture/CHAPTER.md) | Architecture |
| 5 | Domain Specification | [05](../handbook/05-domain-driven-design/CHAPTER.md) | Domain |
| 6 | Architecture Specification | [06](../handbook/06-reference-architecture/CHAPTER.md) | Architecture |
| 7 | API Specification | [13](../handbook/13-api-platform/CHAPTER.md) | Architecture |
| 8 | Integration Specification | [10](../handbook/10-plugin-platform/CHAPTER.md) | Architecture |
| 9 | Workflow Specification | [08](../handbook/08-builder-platform/CHAPTER.md) | Product |
| 10 | Security Specification | [15](../handbook/15-security/CHAPTER.md) | Security |
| 11 | Observability Specification | [14](../handbook/14-observability/CHAPTER.md) | Observability |
| 12 | Testing Specification | [18](../handbook/18-testing/CHAPTER.md) | Testing |
| 13 | Evaluation Specification | [16](../handbook/16-evaluation/CHAPTER.md) | Evaluation |
| 14 | Deployment Specification | [19](../handbook/19-devops/CHAPTER.md) | Operations |
| 15 | Operational Specification | [19](../handbook/19-devops/CHAPTER.md) | Operations |
| 16 | Governance Specification | [11](../handbook/11-control-plane/CHAPTER.md) | Governance |
| 17 | Data Specification | [12](../handbook/12-data-platform/CHAPTER.md) | Architecture |
| 18 | Agent Specification | [07](../handbook/07-runtime-platform/CHAPTER.md) | Runtime |
| 19 | Plugin Specification | [10](../handbook/10-plugin-platform/CHAPTER.md) | Architecture |
| 20 | Provider Specification | [09](../handbook/09-provider-platform/CHAPTER.md) | Provider |
| 21 | Runtime Specification | [07](../handbook/07-runtime-platform/CHAPTER.md) | Runtime |
| 22 | Platform Specification | [06](../handbook/06-reference-architecture/CHAPTER.md) | Architecture |

## Category definitions

### 1. Product Specification

- **Purpose:** Product Specification
- **Scope:** States the product intent for a body of work: the outcomes it must deliver.
- **Inputs:** Personas, jobs, and outcomes for one product concern.
- **Outputs:** A normative statement of product intent and outcome criteria.
- **Dependencies:** Discovery findings.
- **Owning chapter:** [Chapter 02](../handbook/02-product-thinking/CHAPTER.md)
- **Review authority:** Product review (see [Specification Review](SPECIFICATION_REVIEW.md))
- **Completion criteria:** Outcomes and value proposition stated; personas and jobs identified; acceptance criteria defined.

### 2. Business Capability Specification

- **Purpose:** Business Capability Specification
- **Scope:** Defines a durable business capability the platform must provide.
- **Inputs:** One capability, independent of implementation.
- **Outputs:** A capability definition with inputs, outputs, and acceptance.
- **Dependencies:** Product Specification.
- **Owning chapter:** [Chapter 02](../handbook/02-product-thinking/CHAPTER.md)
- **Review authority:** Product review (see [Specification Review](SPECIFICATION_REVIEW.md))
- **Completion criteria:** Capability named from the user's view; boundaries and acceptance defined.

### 3. Functional Specification

- **Purpose:** Functional Specification
- **Scope:** States what a capability must functionally do.
- **Inputs:** The functional behavior of one capability.
- **Outputs:** Functional requirements and acceptance criteria.
- **Dependencies:** Business Capability Specification.
- **Owning chapter:** [Chapter 02](../handbook/02-product-thinking/CHAPTER.md)
- **Review authority:** Product review (see [Specification Review](SPECIFICATION_REVIEW.md))
- **Completion criteria:** Functional behavior and acceptance criteria complete and unambiguous.

### 4. Non-Functional Specification

- **Purpose:** Non-Functional Specification
- **Scope:** States the quality attributes an artifact must meet.
- **Inputs:** Performance, scalability, reliability, and other quality attributes.
- **Outputs:** Quality-attribute requirements with measurable targets.
- **Dependencies:** Functional Specification.
- **Owning chapter:** [Chapter 06](../handbook/06-reference-architecture/CHAPTER.md)
- **Review authority:** Architecture review (see [Specification Review](SPECIFICATION_REVIEW.md))
- **Completion criteria:** Quality attributes stated with measurable targets and trade-offs.

### 5. Domain Specification

- **Purpose:** Domain Specification
- **Scope:** Specifies a domain: its bounded contexts and ubiquitous language.
- **Inputs:** One bounded context and its model.
- **Outputs:** Bounded contexts, ubiquitous language, and domain events.
- **Dependencies:** Product and Capability specifications.
- **Owning chapter:** [Chapter 05](../handbook/05-domain-driven-design/CHAPTER.md)
- **Review authority:** Domain review (see [Specification Review](SPECIFICATION_REVIEW.md))
- **Completion criteria:** Bounded contexts, language, and events defined and terminology-consistent.

### 6. Architecture Specification

- **Purpose:** Architecture Specification
- **Scope:** States the architectural constraints and structure an artifact must satisfy.
- **Inputs:** Architecture of one concern, consistent with the reference architecture.
- **Outputs:** Architectural constraints, boundaries, and views.
- **Dependencies:** Domain and Non-Functional specifications.
- **Owning chapter:** [Chapter 06](../handbook/06-reference-architecture/CHAPTER.md)
- **Review authority:** Architecture review (see [Specification Review](SPECIFICATION_REVIEW.md))
- **Completion criteria:** Boundaries derived from domain; quality attributes addressed; ADRs referenced.

### 7. API Specification

- **Purpose:** API Specification
- **Scope:** Specifies an interaction boundary as a technology-neutral contract.
- **Inputs:** One API and its contract.
- **Outputs:** API contract, versioning, and consistency rules.
- **Dependencies:** Architecture Specification.
- **Owning chapter:** [Chapter 13](../handbook/13-api-platform/CHAPTER.md)
- **Review authority:** Architecture review (see [Specification Review](SPECIFICATION_REVIEW.md))
- **Completion criteria:** Contract, versioning, and consistency defined; no transport prescribed.

### 8. Integration Specification

- **Purpose:** Integration Specification
- **Scope:** Specifies how the platform integrates with an external system.
- **Inputs:** One integration boundary.
- **Outputs:** Integration contract and dependency model.
- **Dependencies:** API and Architecture specifications.
- **Owning chapter:** [Chapter 10](../handbook/10-plugin-platform/CHAPTER.md)
- **Review authority:** Architecture review (see [Specification Review](SPECIFICATION_REVIEW.md))
- **Completion criteria:** Integration contract defined via open protocol; boundary explicit.

### 9. Workflow Specification

- **Purpose:** Workflow Specification
- **Scope:** Specifies a coordinated composition of work.
- **Inputs:** One workflow's structure and intent.
- **Outputs:** Workflow composition and acceptance.
- **Dependencies:** Capability and Domain specifications.
- **Owning chapter:** [Chapter 08](../handbook/08-builder-platform/CHAPTER.md)
- **Review authority:** Product review (see [Specification Review](SPECIFICATION_REVIEW.md))
- **Completion criteria:** Composition, steps, and acceptance defined at design time.

### 10. Security Specification

- **Purpose:** Security Specification
- **Scope:** States the security requirements an artifact must meet.
- **Inputs:** Security of one concern.
- **Outputs:** Threats, controls, and assurances required.
- **Dependencies:** Architecture Specification.
- **Owning chapter:** [Chapter 15](../handbook/15-security/CHAPTER.md)
- **Review authority:** Security review (see [Specification Review](SPECIFICATION_REVIEW.md))
- **Completion criteria:** Threat-modeled; controls and assurances defined; consistent with the trust model.

### 11. Observability Specification

- **Purpose:** Observability Specification
- **Scope:** States what must be observable and to what standard.
- **Inputs:** Observability of one concern.
- **Outputs:** Signals, correlation, and SLOs required.
- **Dependencies:** Architecture and Runtime specifications.
- **Owning chapter:** [Chapter 14](../handbook/14-observability/CHAPTER.md)
- **Review authority:** Observability review (see [Specification Review](SPECIFICATION_REVIEW.md))
- **Completion criteria:** Required signals and SLOs defined; operational visibility addressed.

### 12. Testing Specification

- **Purpose:** Testing Specification
- **Scope:** Specifies how software correctness is verified for an artifact.
- **Inputs:** Testing of one artifact.
- **Outputs:** Test strategy and coverage design.
- **Dependencies:** Functional and Architecture specifications.
- **Owning chapter:** [Chapter 18](../handbook/18-testing/CHAPTER.md)
- **Review authority:** Testing review (see [Specification Review](SPECIFICATION_REVIEW.md))
- **Completion criteria:** Levels, coverage, and regression design defined; distinct from evaluation.

### 13. Evaluation Specification

- **Purpose:** Evaluation Specification
- **Scope:** Specifies how AI quality is measured for an artifact.
- **Inputs:** Evaluation of one AI concern.
- **Outputs:** Evaluation framework, datasets, and metrics design.
- **Dependencies:** Functional and Product specifications.
- **Owning chapter:** [Chapter 16](../handbook/16-evaluation/CHAPTER.md)
- **Review authority:** Evaluation review (see [Specification Review](SPECIFICATION_REVIEW.md))
- **Completion criteria:** Metrics, methods, and success criteria defined; distinct from testing.

### 14. Deployment Specification

- **Purpose:** Deployment Specification
- **Scope:** States how an artifact is deployed and made operable.
- **Inputs:** Deployment of one concern.
- **Outputs:** Deployment topology and pipeline requirements.
- **Dependencies:** Architecture and Operational specifications.
- **Owning chapter:** [Chapter 19](../handbook/19-devops/CHAPTER.md)
- **Review authority:** Operations review (see [Specification Review](SPECIFICATION_REVIEW.md))
- **Completion criteria:** Topology and readiness requirements defined; no tool prescribed.

### 15. Operational Specification

- **Purpose:** Operational Specification
- **Scope:** States the operational conditions an artifact must meet in production.
- **Inputs:** Operations of one concern.
- **Outputs:** Operational readiness and runbook requirements.
- **Dependencies:** Deployment and Observability specifications.
- **Owning chapter:** [Chapter 19](../handbook/19-devops/CHAPTER.md)
- **Review authority:** Operations review (see [Specification Review](SPECIFICATION_REVIEW.md))
- **Completion criteria:** Operational readiness criteria defined; recoverability addressed.

### 16. Governance Specification

- **Purpose:** Governance Specification
- **Scope:** Specifies the governance an artifact is subject to.
- **Inputs:** Governance of one concern.
- **Outputs:** Policies, quotas, and multi-tenancy requirements.
- **Dependencies:** Architecture Specification.
- **Owning chapter:** [Chapter 11](../handbook/11-control-plane/CHAPTER.md)
- **Review authority:** Governance review (see [Specification Review](SPECIFICATION_REVIEW.md))
- **Completion criteria:** Policies, limits, and tenancy requirements defined.

### 17. Data Specification

- **Purpose:** Data Specification
- **Scope:** Specifies the data an artifact persists and governs.
- **Inputs:** Data of one concern.
- **Outputs:** Data model, ownership, and lifecycle requirements.
- **Dependencies:** Domain and Architecture specifications.
- **Owning chapter:** [Chapter 12](../handbook/12-data-platform/CHAPTER.md)
- **Review authority:** Architecture review (see [Specification Review](SPECIFICATION_REVIEW.md))
- **Completion criteria:** Data model, ownership, and lifecycle defined; persistence delegated correctly.

### 18. Agent Specification

- **Purpose:** Agent Specification
- **Scope:** Specifies an agent's intent and structure at design time.
- **Inputs:** One agent.
- **Outputs:** Agent composition, jobs, and acceptance.
- **Dependencies:** Capability and Domain specifications.
- **Owning chapter:** [Chapter 07](../handbook/07-runtime-platform/CHAPTER.md)
- **Review authority:** Runtime review (see [Specification Review](SPECIFICATION_REVIEW.md))
- **Completion criteria:** Agent intent, composition, and acceptance defined; execution delegated to runtime.

### 19. Plugin Specification

- **Purpose:** Plugin Specification
- **Scope:** Specifies an extension and its contract.
- **Inputs:** One plugin.
- **Outputs:** Plugin contract, lifecycle, and capability.
- **Dependencies:** Integration and Architecture specifications.
- **Owning chapter:** [Chapter 10](../handbook/10-plugin-platform/CHAPTER.md)
- **Review authority:** Architecture review (see [Specification Review](SPECIFICATION_REVIEW.md))
- **Completion criteria:** Plugin contract and lifecycle defined; isolation addressed.

### 20. Provider Specification

- **Purpose:** Provider Specification
- **Scope:** Specifies a provider integration behind the provider abstraction.
- **Inputs:** One provider integration.
- **Outputs:** Provider capability contract and routing criteria.
- **Dependencies:** Architecture Specification.
- **Owning chapter:** [Chapter 09](../handbook/09-provider-platform/CHAPTER.md)
- **Review authority:** Provider review (see [Specification Review](SPECIFICATION_REVIEW.md))
- **Completion criteria:** Capability contract defined vendor-neutrally; routing criteria stated.

### 21. Runtime Specification

- **Purpose:** Runtime Specification
- **Scope:** Specifies runtime behavior an artifact requires.
- **Inputs:** Runtime of one concern.
- **Outputs:** Execution, lifecycle, and state requirements.
- **Dependencies:** Architecture Specification.
- **Owning chapter:** [Chapter 07](../handbook/07-runtime-platform/CHAPTER.md)
- **Review authority:** Runtime review (see [Specification Review](SPECIFICATION_REVIEW.md))
- **Completion criteria:** Execution model, lifecycle, and state requirements defined.

### 22. Platform Specification

- **Purpose:** Platform Specification
- **Scope:** States platform-wide requirements spanning multiple planes.
- **Inputs:** The platform as a whole.
- **Outputs:** Cross-plane requirements and coherence constraints.
- **Dependencies:** All plane specifications.
- **Owning chapter:** [Chapter 06](../handbook/06-reference-architecture/CHAPTER.md)
- **Review authority:** Architecture review (see [Specification Review](SPECIFICATION_REVIEW.md))
- **Completion criteria:** Cross-plane coherence and platform-wide constraints defined.
