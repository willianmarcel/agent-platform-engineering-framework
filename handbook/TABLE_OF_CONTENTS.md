# Engineering Handbook — Table of Contents

This document defines the **official structure** of the APEF Engineering Handbook. It specifies every chapter's contract: objective, scope, prerequisites, expected outputs, related chapters, estimated complexity, and mandatory reading. It defines structure only — no chapter content is written here.

See the [Master Index](HANDBOOK.md) for reading strategy and policy, the [Knowledge Graph](KNOWLEDGE_GRAPH.md) for dependencies, and the [Writing Guide](WRITING_GUIDE.md) for the chapter template.

## Chapter summary

| # | Title | Complexity | Prerequisites |
|---|-------|------------|---------------|
| 00 | Introduction | Low | — |
| 01 | Platform Vision | Low | 00 |
| 02 | Product Thinking | Medium | 01 |
| 03 | Engineering Principles | Medium | 00 |
| 04 | Development Methodology | Medium | 03 |
| 05 | Domain-Driven Design | High | 04 |
| 06 | Reference Architecture | High | 01, 03, 05 |
| 07 | Runtime Platform | High | 06 |
| 08 | Builder Platform | High | 06, 07 |
| 09 | Provider Platform | Medium | 06, 07 |
| 10 | Plugin Platform | Medium | 06, 08 |
| 11 | Control Plane | High | 06 |
| 12 | Data Platform | High | 06 |
| 13 | API Platform | Medium | 06 |
| 14 | Observability | Medium | 06, 07 |
| 15 | Security | High | 06 |
| 16 | Evaluation | High | 06, 07 |
| 17 | UI/UX | Medium | 06, 08 |
| 18 | Testing | Medium | 06, 07 |
| 19 | DevOps | Medium | 06, 14 |
| 20 | Roadmap | Low | 01, 02 |
| 21 | Glossary | Low | — |
| 22 | Context & Prompt Engineering | High | 04, 07 |
| 23 | Tool & Function Architecture | High | 07, 11, 15 |
| 24 | Multi-Agent Coordination | High | 07, 11 |
| 25 | Memory & Conversational State | High | 07, 12 |
| 26 | Agentic Security | High | 15, 23 |
| 27 | Evaluation-Driven Development | High | 04, 16 |

## Chapter definitions

### Chapter 00 — Introduction

- **Chapter number:** 00
- **Chapter title:** Introduction
- **Objective:** Orient the reader and establish how to use the handbook.
- **Scope:** What APEF is and is not, who the handbook serves, and how the chapters, specifications, and architecture fit together.
- **Prerequisites:** None
- **Expected outputs:** The reader understands the handbook's structure and the recommended reading path.
- **Related chapters:** [01 — Platform Vision](01-platform-vision/), [21 — Glossary](21-glossary/)
- **Estimated complexity:** Low
- **Mandatory reading before this chapter:** None

### Chapter 01 — Platform Vision

- **Chapter number:** 01
- **Chapter title:** Platform Vision
- **Objective:** Establish the long-term platform vision and its success criteria.
- **Scope:** Outcomes an AI Agent Platform should deliver, guiding tenets, and the boundaries between vision, strategy, and implementation.
- **Prerequisites:** [00 — Introduction](00-introduction/)
- **Expected outputs:** A shared framing of what the platform is for and what good looks like.
- **Related chapters:** [02 — Product Thinking](02-product-thinking/), [06 — Reference Architecture](06-reference-architecture/), [20 — Roadmap](20-roadmap/)
- **Estimated complexity:** Low
- **Mandatory reading before this chapter:** [00 — Introduction](00-introduction/)

### Chapter 02 — Product Thinking

- **Chapter number:** 02
- **Chapter title:** Product Thinking
- **Objective:** Frame the platform as a product with users and jobs to be done.
- **Scope:** Platform users (builders, operators, end users), jobs-to-be-done, and capability-driven prioritization.
- **Prerequisites:** [01 — Platform Vision](01-platform-vision/)
- **Expected outputs:** A user- and value-centered lens for prioritizing platform work.
- **Related chapters:** [20 — Roadmap](20-roadmap/)
- **Estimated complexity:** Medium
- **Mandatory reading before this chapter:** [01 — Platform Vision](01-platform-vision/)

### Chapter 03 — Engineering Principles

- **Chapter number:** 03
- **Chapter title:** Engineering Principles
- **Objective:** State the engineering principles that govern every platform decision.
- **Scope:** Maintainability, extensibility, long-term evolution, simplicity, and how trade-offs are resolved.
- **Prerequisites:** [00 — Introduction](00-introduction/)
- **Expected outputs:** A principle set every later chapter can appeal to.
- **Related chapters:** [04 — Development Methodology](04-development-methodology/), [06 — Reference Architecture](06-reference-architecture/)
- **Estimated complexity:** Medium
- **Mandatory reading before this chapter:** [00 — Introduction](00-introduction/)

### Chapter 04 — Development Methodology

- **Chapter number:** 04
- **Chapter title:** Development Methodology
- **Objective:** Define how intent becomes specification, architecture, and evaluation.
- **Scope:** Specification-Driven Development, the role of ADRs, and how implementation stays faithful to intent.
- **Prerequisites:** [03 — Engineering Principles](03-engineering-principles/)
- **Expected outputs:** A shared methodology for turning decisions into artifacts.
- **Related chapters:** [05 — Domain-Driven Design](05-domain-driven-design/), [16 — Evaluation](16-evaluation/), [18 — Testing](18-testing/)
- **Estimated complexity:** Medium
- **Mandatory reading before this chapter:** [03 — Engineering Principles](03-engineering-principles/)

### Chapter 05 — Domain-Driven Design

- **Chapter number:** 05
- **Chapter title:** Domain-Driven Design
- **Objective:** Establish the domain model, boundaries, and ubiquitous language.
- **Scope:** Bounded contexts, context mapping, aggregates and events, and how domain models connect to specifications and event storming.
- **Prerequisites:** [04 — Development Methodology](04-development-methodology/)
- **Expected outputs:** A domain-modeling approach and the seed of the ubiquitous language.
- **Related chapters:** [06 — Reference Architecture](06-reference-architecture/), [12 — Data Platform](12-data-platform/), [21 — Glossary](21-glossary/)
- **Estimated complexity:** High
- **Mandatory reading before this chapter:** [04 — Development Methodology](04-development-methodology/)

### Chapter 06 — Reference Architecture

- **Chapter number:** 06
- **Chapter title:** Reference Architecture
- **Objective:** Present the reference architecture that ties the platform's planes into a coherent whole.
- **Scope:** The layered and modular structure, how the planes relate, cross-cutting concerns, and the seams between components.
- **Prerequisites:** [01 — Platform Vision](01-platform-vision/), [03 — Engineering Principles](03-engineering-principles/), [05 — Domain-Driven Design](05-domain-driven-design/)
- **Expected outputs:** The canonical mental model that every plane and cross-cutting chapter builds on.
- **Related chapters:** [07 — Runtime Platform](07-runtime-platform/), [08 — Builder Platform](08-builder-platform/), [09 — Provider Platform](09-provider-platform/), [10 — Plugin Platform](10-plugin-platform/), [11 — Control Plane](11-control-plane/), [12 — Data Platform](12-data-platform/), [13 — API Platform](13-api-platform/), [14 — Observability](14-observability/), [15 — Security](15-security/), [16 — Evaluation](16-evaluation/), [17 — UI/UX](17-ui-ux/), [18 — Testing](18-testing/), [19 — DevOps](19-devops/)
- **Estimated complexity:** High
- **Mandatory reading before this chapter:** [01 — Platform Vision](01-platform-vision/), [03 — Engineering Principles](03-engineering-principles/), [05 — Domain-Driven Design](05-domain-driven-design/)

### Chapter 07 — Runtime Platform

- **Chapter number:** 07
- **Chapter title:** Runtime Platform
- **Objective:** Define the runtime that executes agents and workflows.
- **Scope:** The execution model, state and lifecycle, and scaling, isolation, and reliability.
- **Prerequisites:** [06 — Reference Architecture](06-reference-architecture/)
- **Expected outputs:** A shared understanding of runtime behavior for builders and operators.
- **Related chapters:** [08 — Builder Platform](08-builder-platform/), [09 — Provider Platform](09-provider-platform/), [14 — Observability](14-observability/), [16 — Evaluation](16-evaluation/), [18 — Testing](18-testing/)
- **Estimated complexity:** High
- **Mandatory reading before this chapter:** [06 — Reference Architecture](06-reference-architecture/)

### Chapter 08 — Builder Platform

- **Chapter number:** 08
- **Chapter title:** Builder Platform
- **Objective:** Define the authoring model and developer experience for builders.
- **Scope:** Composition of agents, tools, and workflows, and validation and iteration during building.
- **Prerequisites:** [06 — Reference Architecture](06-reference-architecture/), [07 — Runtime Platform](07-runtime-platform/)
- **Expected outputs:** A model of how platforms are built on the runtime.
- **Related chapters:** [10 — Plugin Platform](10-plugin-platform/), [17 — UI/UX](17-ui-ux/)
- **Estimated complexity:** High
- **Mandatory reading before this chapter:** [06 — Reference Architecture](06-reference-architecture/), [07 — Runtime Platform](07-runtime-platform/)

### Chapter 09 — Provider Platform

- **Chapter number:** 09
- **Chapter title:** Provider Platform
- **Objective:** Define the provider abstraction and integration model.
- **Scope:** The provider contract, integration patterns, and portability and multi-provider strategies.
- **Prerequisites:** [06 — Reference Architecture](06-reference-architecture/), [07 — Runtime Platform](07-runtime-platform/)
- **Expected outputs:** A portable approach to integrating model and service providers.
- **Related chapters:** [13 — API Platform](13-api-platform/)
- **Estimated complexity:** Medium
- **Mandatory reading before this chapter:** [06 — Reference Architecture](06-reference-architecture/), [07 — Runtime Platform](07-runtime-platform/)

### Chapter 10 — Plugin Platform

- **Chapter number:** 10
- **Chapter title:** Plugin Platform
- **Objective:** Define the extensibility model based on plugins.
- **Scope:** The plugin contract, lifecycle, isolation, discovery, and compatibility.
- **Prerequisites:** [06 — Reference Architecture](06-reference-architecture/), [08 — Builder Platform](08-builder-platform/)
- **Expected outputs:** A safe model for growing the platform through extensions.
- **Related chapters:** [09 — Provider Platform](09-provider-platform/)
- **Estimated complexity:** Medium
- **Mandatory reading before this chapter:** [06 — Reference Architecture](06-reference-architecture/), [08 — Builder Platform](08-builder-platform/)

### Chapter 11 — Control Plane

- **Chapter number:** 11
- **Chapter title:** Control Plane
- **Objective:** Define the control plane that governs, configures, and operates the platform.
- **Scope:** Configuration, policy, orchestration, multi-tenancy, access control, and administration.
- **Prerequisites:** [06 — Reference Architecture](06-reference-architecture/)
- **Expected outputs:** A model of how the platform is governed and operated.
- **Related chapters:** [15 — Security](15-security/), [13 — API Platform](13-api-platform/), [19 — DevOps](19-devops/)
- **Estimated complexity:** High
- **Mandatory reading before this chapter:** [06 — Reference Architecture](06-reference-architecture/)

### Chapter 12 — Data Platform

- **Chapter number:** 12
- **Chapter title:** Data Platform
- **Objective:** Define how the platform stores, retrieves, and governs data.
- **Scope:** Data models, persistence and retrieval (including vector and knowledge stores), lifecycle, and governance.
- **Prerequisites:** [06 — Reference Architecture](06-reference-architecture/)
- **Expected outputs:** A model of the platform's data foundations.
- **Related chapters:** [14 — Observability](14-observability/), [15 — Security](15-security/), [16 — Evaluation](16-evaluation/)
- **Estimated complexity:** High
- **Mandatory reading before this chapter:** [06 — Reference Architecture](06-reference-architecture/)

### Chapter 13 — API Platform

- **Chapter number:** 13
- **Chapter title:** API Platform
- **Objective:** Define the API surface through which the platform is consumed.
- **Scope:** API paradigms and contracts, versioning and deprecation, and authentication and rate control at the edge.
- **Prerequisites:** [06 — Reference Architecture](06-reference-architecture/)
- **Expected outputs:** A consistent, versioned contract model for the platform.
- **Related chapters:** [11 — Control Plane](11-control-plane/), [15 — Security](15-security/), [09 — Provider Platform](09-provider-platform/)
- **Estimated complexity:** Medium
- **Mandatory reading before this chapter:** [06 — Reference Architecture](06-reference-architecture/)

### Chapter 14 — Observability

- **Chapter number:** 14
- **Chapter title:** Observability
- **Objective:** Define how the platform is made observable.
- **Scope:** Metrics, logs, and distributed tracing, instrumentation standards, dashboards, alerting, and SLOs.
- **Prerequisites:** [06 — Reference Architecture](06-reference-architecture/), [07 — Runtime Platform](07-runtime-platform/)
- **Expected outputs:** An instrumentation and insight model spanning the planes.
- **Related chapters:** [19 — DevOps](19-devops/), [16 — Evaluation](16-evaluation/)
- **Estimated complexity:** Medium
- **Mandatory reading before this chapter:** [06 — Reference Architecture](06-reference-architecture/), [07 — Runtime Platform](07-runtime-platform/)

### Chapter 15 — Security

- **Chapter number:** 15
- **Chapter title:** Security
- **Objective:** Define the security model and the framework's security expectations.
- **Scope:** Threat modeling for agent platforms, identity, secrets, isolation, and prompt/tool/data security.
- **Prerequisites:** [06 — Reference Architecture](06-reference-architecture/)
- **Expected outputs:** A designed-in security posture the other planes must uphold.
- **Related chapters:** [11 — Control Plane](11-control-plane/), [12 — Data Platform](12-data-platform/), [13 — API Platform](13-api-platform/)
- **Estimated complexity:** High
- **Mandatory reading before this chapter:** [06 — Reference Architecture](06-reference-architecture/)

### Chapter 16 — Evaluation

- **Chapter number:** 16
- **Chapter title:** Evaluation
- **Objective:** Define how the AI systems — agents, workflows, and the platform — are evaluated for quality.
- **Scope:** Evaluation of model-dependent, non-deterministic AI behavior: strategies, datasets, metrics, offline/online/continuous evaluation, and regression detection. A distinct discipline from software Testing (Chapter 18).
- **Prerequisites:** [06 — Reference Architecture](06-reference-architecture/), [07 — Runtime Platform](07-runtime-platform/)
- **Expected outputs:** A model for measuring and tracking AI behavioral quality.
- **Related chapters:** [18 — Testing](18-testing/), [12 — Data Platform](12-data-platform/)
- **Estimated complexity:** High
- **Mandatory reading before this chapter:** [06 — Reference Architecture](06-reference-architecture/), [07 — Runtime Platform](07-runtime-platform/)

### Chapter 17 — UI/UX

- **Chapter number:** 17
- **Chapter title:** UI/UX
- **Objective:** Define interaction models and design principles for platform surfaces.
- **Scope:** Interaction models for building, operating, and using agents, and clarity, trust, control, and accessibility.
- **Prerequisites:** [06 — Reference Architecture](06-reference-architecture/), [08 — Builder Platform](08-builder-platform/)
- **Expected outputs:** A shared approach to the platform's user experience.
- **Related chapters:** None
- **Estimated complexity:** Medium
- **Mandatory reading before this chapter:** [06 — Reference Architecture](06-reference-architecture/), [08 — Builder Platform](08-builder-platform/)

### Chapter 18 — Testing

- **Chapter number:** 18
- **Chapter title:** Testing
- **Objective:** Define how the platform's software systems are tested for correctness.
- **Scope:** Testing of deterministic software behavior: test levels and strategy, test data and environments, and how testing delegates model-dependent behavioral quality to Evaluation (Chapter 16). A distinct discipline from AI Evaluation.
- **Prerequisites:** [06 — Reference Architecture](06-reference-architecture/), [07 — Runtime Platform](07-runtime-platform/)
- **Expected outputs:** A software test strategy that complements, but is distinct from, evaluation.
- **Related chapters:** [16 — Evaluation](16-evaluation/), [19 — DevOps](19-devops/)
- **Estimated complexity:** Medium
- **Mandatory reading before this chapter:** [06 — Reference Architecture](06-reference-architecture/), [07 — Runtime Platform](07-runtime-platform/)

### Chapter 19 — DevOps

- **Chapter number:** 19
- **Chapter title:** DevOps
- **Objective:** Define how the platform is built, deployed, and operated reliably.
- **Scope:** CI/CD, environments, infrastructure and release automation, and production readiness.
- **Prerequisites:** [06 — Reference Architecture](06-reference-architecture/), [14 — Observability](14-observability/)
- **Expected outputs:** A delivery and operations model for the platform.
- **Related chapters:** [11 — Control Plane](11-control-plane/), [18 — Testing](18-testing/)
- **Estimated complexity:** Medium
- **Mandatory reading before this chapter:** [06 — Reference Architecture](06-reference-architecture/), [14 — Observability](14-observability/)

### Chapter 20 — Roadmap

- **Chapter number:** 20
- **Chapter title:** Roadmap
- **Objective:** Explain how the platform's roadmap is shaped, sequenced, and communicated.
- **Scope:** How vision and product thinking translate into a sequenced roadmap and how it relates to framework phases.
- **Prerequisites:** [01 — Platform Vision](01-platform-vision/), [02 — Product Thinking](02-product-thinking/)
- **Expected outputs:** An approach to planning and sequencing platform capabilities.
- **Related chapters:** [06 — Reference Architecture](06-reference-architecture/)
- **Estimated complexity:** Low
- **Mandatory reading before this chapter:** [01 — Platform Vision](01-platform-vision/), [02 — Product Thinking](02-product-thinking/)

### Chapter 21 — Glossary

- **Chapter number:** 21
- **Chapter title:** Glossary
- **Objective:** Provide the canonical vocabulary — the ubiquitous language — used across the handbook.
- **Scope:** Definitions of core terms, disambiguation of overloaded industry terms, and cross-references to elaborating chapters.
- **Prerequisites:** None
- **Expected outputs:** A single, authoritative term list the whole handbook conforms to.
- **Related chapters:** [05 — Domain-Driven Design](05-domain-driven-design/)
- **Estimated complexity:** Low
- **Mandatory reading before this chapter:** None

> **Agentic Engineering (chapters 22–26).** Added after the initial 00–21 body, these chapters cover the engineering disciplines specific to agentic systems. The Glossary (21) remains the terminology reference.

### Chapter 22 — Context & Prompt Engineering

- **Chapter number:** 22
- **Chapter title:** Context & Prompt Engineering
- **Objective:** Make context and prompts first-class, versioned engineering artifacts.
- **Scope:** Context, prompts, assembly, the context window, budget, and the prompt lifecycle.
- **Prerequisites:** [04 — Development Methodology](04-development-methodology/), [07 — Runtime Platform](07-runtime-platform/)
- **Expected outputs:** A shared engineering understanding of context & prompt engineering for builders and operators.
- **Related chapters:** [04 — Development Methodology](04-development-methodology/), [09 — Provider Platform](09-provider-platform/), [16 — Evaluation](16-evaluation/)
- **Estimated complexity:** High
- **Mandatory reading before this chapter:** [04 — Development Methodology](04-development-methodology/), [07 — Runtime Platform](07-runtime-platform/)

### Chapter 23 — Tool & Function Architecture

- **Chapter number:** 23
- **Chapter title:** Tool & Function Architecture
- **Objective:** Define what an agent may do, under what authority, with what safeguards.
- **Scope:** Tool contracts, permissioning, side-effect classes, and safe action.
- **Prerequisites:** [07 — Runtime Platform](07-runtime-platform/), [11 — Control Plane](11-control-plane/), [15 — Security](15-security/)
- **Expected outputs:** A shared engineering understanding of tool & function architecture for builders and operators.
- **Related chapters:** [10 — Plugin Platform](10-plugin-platform/), [11 — Control Plane](11-control-plane/), [15 — Security](15-security/)
- **Estimated complexity:** High
- **Mandatory reading before this chapter:** [07 — Runtime Platform](07-runtime-platform/), [11 — Control Plane](11-control-plane/), [15 — Security](15-security/)

### Chapter 24 — Multi-Agent Coordination

- **Chapter number:** 24
- **Chapter title:** Multi-Agent Coordination
- **Objective:** Bound multi-agent designs with roles, handoff contracts, and convergence.
- **Scope:** Agent roles, coordination topologies, handoffs, and termination.
- **Prerequisites:** [07 — Runtime Platform](07-runtime-platform/), [11 — Control Plane](11-control-plane/)
- **Expected outputs:** A shared engineering understanding of multi-agent coordination for builders and operators.
- **Related chapters:** [07 — Runtime Platform](07-runtime-platform/), [11 — Control Plane](11-control-plane/), [08 — Builder Platform](08-builder-platform/)
- **Estimated complexity:** High
- **Mandatory reading before this chapter:** [07 — Runtime Platform](07-runtime-platform/), [11 — Control Plane](11-control-plane/)

### Chapter 25 — Memory & Conversational State

- **Chapter number:** 25
- **Chapter title:** Memory & Conversational State
- **Objective:** Engineer memory as a governed, scoped, retained store — not a transcript.
- **Scope:** Working and long-term memory, scope, retention, and retrieval into context.
- **Prerequisites:** [07 — Runtime Platform](07-runtime-platform/), [12 — Data Platform](12-data-platform/)
- **Expected outputs:** A shared engineering understanding of memory & conversational state for builders and operators.
- **Related chapters:** [12 — Data Platform](12-data-platform/), [07 — Runtime Platform](07-runtime-platform/), [15 — Security](15-security/)
- **Estimated complexity:** High
- **Mandatory reading before this chapter:** [07 — Runtime Platform](07-runtime-platform/), [12 — Data Platform](12-data-platform/)

### Chapter 26 — Agentic Security

- **Chapter number:** 26
- **Chapter title:** Agentic Security
- **Objective:** Defend a system whose control flow is shaped by untrusted content and whose actions have effect.
- **Scope:** The agentic threat surface, guardrails, autonomy levels, and least authority.
- **Prerequisites:** [15 — Security](15-security/), [23 — Tool & Function Architecture](23-tool-and-function-architecture/)
- **Expected outputs:** A shared engineering understanding of agentic security for builders and operators.
- **Related chapters:** [15 — Security](15-security/), [16 — Evaluation](16-evaluation/), [23 — Tool & Function Architecture](23-tool-and-function-architecture/)
- **Estimated complexity:** High
- **Mandatory reading before this chapter:** [15 — Security](15-security/), [23 — Tool & Function Architecture](23-tool-and-function-architecture/)

### Chapter 27 — Evaluation-Driven Development

- **Chapter number:** 27
- **Chapter title:** Evaluation-Driven Development
- **Objective:** Make evaluation a peer of specification, gating every behavior-shaping change.
- **Scope:** The evaluation-first workflow, behavioral acceptance criteria, and the behavioral regression gate.
- **Prerequisites:** [04 — Development Methodology](04-development-methodology/), [16 — Evaluation](16-evaluation/)
- **Expected outputs:** A shared methodology for gating non-deterministic behavior on evidence.
- **Related chapters:** [04 — Development Methodology](04-development-methodology/), [16 — Evaluation](16-evaluation/), [18 — Testing](18-testing/)
- **Estimated complexity:** High
- **Mandatory reading before this chapter:** [04 — Development Methodology](04-development-methodology/), [16 — Evaluation](16-evaluation/)
