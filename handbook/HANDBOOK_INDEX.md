# Handbook Index

The primary navigation artifact for the APEF Engineering Handbook. It maps every concept to its owning chapter and the chapters that reference it, so any concept can be located and traced. It is generated from the chapters and is consistent with the [Platform Capability Model](PLATFORM_CAPABILITY_MODEL.md) and the [Knowledge Graph](KNOWLEDGE_GRAPH.md).

**Method.** *Owning chapter* is the chapter that defines the concept. *Referenced by* lists other chapters whose text uses the exact term. *Related concepts* are the other concepts owned by the same chapter. Concept definitions live only in the owning chapter; the [Glossary](21-glossary/CHAPTER.md) standardizes terminology and owns no concepts.

**Totals.** 261 concepts across 28 chapters; each concept has exactly one owning chapter.

## Concept ownership by chapter

### Chapter 00 — Introduction

_Owns no concepts (standardizes terminology only)._

### Chapter 01 — Platform Vision

Owns 5 concept(s). Related concepts are the siblings listed here.

| Concept | Referenced by |
|---------|---------------|
| What an AI Agent Platform is (vision level) | — |
| Why this class of platform exists | — |
| Business problems addressed | — |
| Primary users (introduced here; analyzed in Chapter 02) | — |
| Differentiation from traditional automation | — |

### Chapter 02 — Product Thinking

Owns 19 concept(s). Related concepts are the siblings listed here.

| Concept | Referenced by |
|---------|---------------|
| Product Philosophy | — |
| Why traditional product thinking is insufficient | — |
| Product Vision translation into Product Strategy | — |
| Value Proposition | — |
| Product Personas | — |
| Jobs To Be Done | — |
| Customer Outcomes | — |
| Product Capabilities | — |
| Product Boundaries | — |
| Build vs Buy | — |
| Platform Thinking | — |
| Platform Composability | — |
| Ecosystem Thinking | — |
| Platform Network Effects | — |
| Extensibility as a Product Capability | — |
| Internal and External Platform Products | — |
| Product Evolution | 20 |
| Product Quality Attributes | — |
| Platform Adoption | — |

### Chapter 03 — Engineering Principles

Owns 9 concept(s). Related concepts are the siblings listed here.

| Concept | Referenced by |
|---------|---------------|
| Engineering Principles | 00, 01, 02, 04, 06, 13, 15, 20, 21 |
| Architectural Principles | — |
| Design Principles | 13 |
| Engineering Culture | — |
| Technical Excellence | — |
| Simplicity | — |
| Maintainability | — |
| Evolvability | — |
| Quality by Design | — |

### Chapter 04 — Development Methodology

Owns 8 concept(s). Related concepts are the siblings listed here.

| Concept | Referenced by |
|---------|---------------|
| Spec Driven Development | — |
| Iterative Development | — |
| Architecture Governance | — |
| Decision Records | 00 |
| Definition of Done | — |
| Engineering Workflow | — |
| Review Process | — |
| Delivery Lifecycle | — |

### Chapter 05 — Domain-Driven Design

Owns 8 concept(s). Related concepts are the siblings listed here.

| Concept | Referenced by |
|---------|---------------|
| Domain-Driven Design | 04, 06, 12, 13, 21 |
| Bounded Contexts | — |
| Ubiquitous Language | — |
| Entities | — |
| Value Objects | — |
| Aggregates | — |
| Domain Services | — |
| Events | 13 |

### Chapter 06 — Reference Architecture

Owns 7 concept(s). Related concepts are the siblings listed here.

| Concept | Referenced by |
|---------|---------------|
| Reference Architecture | 00, 01, 02, 03, 04, 05, 07, 08, 09, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21 |
| Platform Layers | — |
| Architectural Views | — |
| Building Blocks | — |
| Platform Planes | — |
| Architectural Quality Attributes | — |
| Architectural Boundaries | — |

### Chapter 07 — Runtime Platform

Owns 10 concept(s). Related concepts are the siblings listed here.

| Concept | Referenced by |
|---------|---------------|
| Runtime Platform | 06, 08, 09, 11, 12, 14, 16, 18, 19, 21 |
| Agent Runtime | — |
| Agent Lifecycle | — |
| Runtime Responsibilities | — |
| Execution Model | — |
| Scheduling | — |
| State | 00, 01, 02, 03, 05, 12, 15 |
| Session | — |
| Memory Coordination | — |
| Runtime Boundaries | — |

### Chapter 08 — Builder Platform

Owns 12 concept(s). Related concepts are the siblings listed here.

| Concept | Referenced by |
|---------|---------------|
| Builder Experience | — |
| Design-Time Experience | — |
| Creator Experience | — |
| Visual Composition | — |
| No-Code Development | — |
| Low-Code Development | — |
| Agent Assembly | — |
| Workflow Composition | — |
| Prompt Assets | — |
| Templates | — |
| Blueprints | — |
| Reusable Components | — |

### Chapter 09 — Provider Platform

Owns 12 concept(s). Related concepts are the siblings listed here.

| Concept | Referenced by |
|---------|---------------|
| LLM Providers | — |
| Provider Abstraction | 21 |
| Model Catalog | — |
| Provider Capabilities | — |
| Capability Matching | — |
| Multi-Provider Strategy | — |
| Routing Policies | — |
| Model Selection | — |
| Cost Awareness | — |
| Latency Awareness | — |
| Provider Independence | — |
| Vendor Neutrality | — |

### Chapter 10 — Plugin Platform

Owns 12 concept(s). Related concepts are the siblings listed here.

| Concept | Referenced by |
|---------|---------------|
| Plugin Architecture | — |
| Platform Extensibility | — |
| Extensions | — |
| Capabilities | 02, 09 |
| Connectors | — |
| Skills | — |
| Tools | — |
| External Systems | — |
| MCP Integration | — |
| A2A Integration | — |
| Plugin Contracts | — |
| Plugin Lifecycle | — |

### Chapter 11 — Control Plane

Owns 11 concept(s). Related concepts are the siblings listed here.

| Concept | Referenced by |
|---------|---------------|
| Platform Governance | — |
| Operational Governance | — |
| Configuration | — |
| Platform Configuration | — |
| Policies | 09 |
| Multi-Tenancy | — |
| Identity | — |
| Authorization | — |
| Quotas | — |
| Feature Flags | — |
| Administration | — |

### Chapter 12 — Data Platform

Owns 12 concept(s). Related concepts are the siblings listed here.

| Concept | Referenced by |
|---------|---------------|
| Platform Data | 21 |
| State Persistence | — |
| Memory Persistence | — |
| Conversation Persistence | — |
| Knowledge Assets | — |
| Vector Data | — |
| Structured Data | — |
| Metadata | — |
| Event Storage | — |
| Audit Data | — |
| Data Ownership | — |
| Data Lifecycle | — |

### Chapter 13 — API Platform

Owns 12 concept(s). Related concepts are the siblings listed here.

| Concept | Referenced by |
|---------|---------------|
| Platform APIs | — |
| Public APIs | — |
| Internal APIs | — |
| Event APIs | — |
| Integration APIs | — |
| API Contracts | — |
| API Versioning | — |
| API Consistency | — |
| API Design Principles | — |
| API Governance | — |
| API Lifecycle | — |
| API Discovery | — |

### Chapter 14 — Observability

Owns 12 concept(s). Related concepts are the siblings listed here.

| Concept | Referenced by |
|---------|---------------|
| Observability | 06, 07, 12, 13, 15, 16, 17, 19, 21 |
| Platform Signals | — |
| Telemetry | — |
| Logs | — |
| Metrics | 16 |
| Traces | — |
| Correlation | — |
| Operational Visibility | — |
| Health | — |
| Monitoring | — |
| Diagnostics | — |
| SLO | 21 |

### Chapter 15 — Security

Owns 11 concept(s). Related concepts are the siblings listed here.

| Concept | Referenced by |
|---------|---------------|
| Security Principles | — |
| Secure by Design | — |
| Zero Trust | — |
| Defense in Depth | — |
| Threat Modeling | — |
| Platform Trust Model | — |
| Security Architecture | — |
| Secrets Management | — |
| Cryptography Principles | — |
| Privacy | — |
| Compliance | — |

### Chapter 16 — Evaluation

Owns 11 concept(s). Related concepts are the siblings listed here.

| Concept | Referenced by |
|---------|---------------|
| AI Evaluation | 21 |
| Agent Evaluation | — |
| Prompt Evaluation | — |
| Quality Evaluation | — |
| Human Evaluation | — |
| Automated Evaluation | — |
| Benchmarking | — |
| Success Metrics | — |
| Continuous Evaluation | — |
| Reliability Evaluation | — |
| Evaluation Framework | — |

### Chapter 17 — User Experience

Owns 10 concept(s). Related concepts are the siblings listed here.

| Concept | Referenced by |
|---------|---------------|
| User Experience | 16 |
| Platform Experience | — |
| Operator Experience | — |
| Administrator Experience | — |
| Human Interaction | — |
| Explainability | — |
| Transparency | — |
| Feedback | — |
| Human in the Loop | — |
| Accessibility | — |

### Chapter 18 — Testing

Owns 12 concept(s). Related concepts are the siblings listed here.

| Concept | Referenced by |
|---------|---------------|
| Testing Strategy | — |
| Unit Testing | — |
| Integration Testing | — |
| End-to-End Testing | — |
| Contract Testing | — |
| Runtime Testing | — |
| Platform Testing | — |
| Agent Testing | — |
| Regression Testing | — |
| Test Automation | — |
| Test Pyramid | — |
| Test Quality | — |

### Chapter 19 — DevOps

Owns 12 concept(s). Related concepts are the siblings listed here.

| Concept | Referenced by |
|---------|---------------|
| DevOps | 18, 20 |
| Engineering Operations | — |
| Platform Operations | — |
| Continuous Integration | — |
| Continuous Delivery | — |
| Continuous Deployment | — |
| Deployment Pipelines | — |
| Release Management | — |
| GitOps | — |
| Infrastructure Lifecycle | — |
| Operational Automation | — |
| Operational Readiness | — |

### Chapter 20 — Roadmap

Owns 10 concept(s). Related concepts are the siblings listed here.

| Concept | Referenced by |
|---------|---------------|
| Evolution Strategy | — |
| Long-term Evolution | — |
| Capability Evolution | — |
| Product Evolution Roadmap | — |
| Architectural Evolution | — |
| Backward Compatibility | — |
| Versioning Strategy | — |
| Release Philosophy | — |
| Technical Debt Strategy | — |
| Innovation Management | — |

### Chapter 21 — Glossary

Owns 5 concept(s). Related concepts are the siblings listed here.

| Concept | Referenced by |
|---------|---------------|
| Canonical Terminology | — |
| Definitions | — |
| Vocabulary | — |
| Acronyms | — |
| Naming Standards | — |

## Alphabetical concept lookup

| Concept | Owning chapter |
|---------|----------------|
| A2A Integration | [10](10-plugin-platform/CHAPTER.md) |
| Accessibility | [17](17-ui-ux/CHAPTER.md) |
| Acronyms | [21](21-glossary/CHAPTER.md) |
| Administration | [11](11-control-plane/CHAPTER.md) |
| Administrator Experience | [17](17-ui-ux/CHAPTER.md) |
| Agent Assembly | [08](08-builder-platform/CHAPTER.md) |
| Agent Evaluation | [16](16-evaluation/CHAPTER.md) |
| Agent Lifecycle | [07](07-runtime-platform/CHAPTER.md) |
| Agent Runtime | [07](07-runtime-platform/CHAPTER.md) |
| Agent Testing | [18](18-testing/CHAPTER.md) |
| Aggregates | [05](05-domain-driven-design/CHAPTER.md) |
| AI Evaluation | [16](16-evaluation/CHAPTER.md) |
| API Consistency | [13](13-api-platform/CHAPTER.md) |
| API Contracts | [13](13-api-platform/CHAPTER.md) |
| API Design Principles | [13](13-api-platform/CHAPTER.md) |
| API Discovery | [13](13-api-platform/CHAPTER.md) |
| API Governance | [13](13-api-platform/CHAPTER.md) |
| API Lifecycle | [13](13-api-platform/CHAPTER.md) |
| API Versioning | [13](13-api-platform/CHAPTER.md) |
| Architectural Boundaries | [06](06-reference-architecture/CHAPTER.md) |
| Architectural Evolution | [20](20-roadmap/CHAPTER.md) |
| Architectural Principles | [03](03-engineering-principles/CHAPTER.md) |
| Architectural Quality Attributes | [06](06-reference-architecture/CHAPTER.md) |
| Architectural Views | [06](06-reference-architecture/CHAPTER.md) |
| Architecture Governance | [04](04-development-methodology/CHAPTER.md) |
| Audit Data | [12](12-data-platform/CHAPTER.md) |
| Authorization | [11](11-control-plane/CHAPTER.md) |
| Automated Evaluation | [16](16-evaluation/CHAPTER.md) |
| Backward Compatibility | [20](20-roadmap/CHAPTER.md) |
| Benchmarking | [16](16-evaluation/CHAPTER.md) |
| Blueprints | [08](08-builder-platform/CHAPTER.md) |
| Bounded Contexts | [05](05-domain-driven-design/CHAPTER.md) |
| Build vs Buy | [02](02-product-thinking/CHAPTER.md) |
| Builder Experience | [08](08-builder-platform/CHAPTER.md) |
| Building Blocks | [06](06-reference-architecture/CHAPTER.md) |
| Business problems addressed | [01](01-platform-vision/CHAPTER.md) |
| Canonical Terminology | [21](21-glossary/CHAPTER.md) |
| Capabilities | [10](10-plugin-platform/CHAPTER.md) |
| Capability Evolution | [20](20-roadmap/CHAPTER.md) |
| Capability Matching | [09](09-provider-platform/CHAPTER.md) |
| Compliance | [15](15-security/CHAPTER.md) |
| Configuration | [11](11-control-plane/CHAPTER.md) |
| Connectors | [10](10-plugin-platform/CHAPTER.md) |
| Continuous Delivery | [19](19-devops/CHAPTER.md) |
| Continuous Deployment | [19](19-devops/CHAPTER.md) |
| Continuous Evaluation | [16](16-evaluation/CHAPTER.md) |
| Continuous Integration | [19](19-devops/CHAPTER.md) |
| Contract Testing | [18](18-testing/CHAPTER.md) |
| Conversation Persistence | [12](12-data-platform/CHAPTER.md) |
| Correlation | [14](14-observability/CHAPTER.md) |
| Cost Awareness | [09](09-provider-platform/CHAPTER.md) |
| Creator Experience | [08](08-builder-platform/CHAPTER.md) |
| Cryptography Principles | [15](15-security/CHAPTER.md) |
| Customer Outcomes | [02](02-product-thinking/CHAPTER.md) |
| Data Lifecycle | [12](12-data-platform/CHAPTER.md) |
| Data Ownership | [12](12-data-platform/CHAPTER.md) |
| Decision Records | [04](04-development-methodology/CHAPTER.md) |
| Defense in Depth | [15](15-security/CHAPTER.md) |
| Definition of Done | [04](04-development-methodology/CHAPTER.md) |
| Definitions | [21](21-glossary/CHAPTER.md) |
| Delivery Lifecycle | [04](04-development-methodology/CHAPTER.md) |
| Deployment Pipelines | [19](19-devops/CHAPTER.md) |
| Design Principles | [03](03-engineering-principles/CHAPTER.md) |
| Design-Time Experience | [08](08-builder-platform/CHAPTER.md) |
| DevOps | [19](19-devops/CHAPTER.md) |
| Diagnostics | [14](14-observability/CHAPTER.md) |
| Differentiation from traditional automation | [01](01-platform-vision/CHAPTER.md) |
| Domain Services | [05](05-domain-driven-design/CHAPTER.md) |
| Domain-Driven Design | [05](05-domain-driven-design/CHAPTER.md) |
| Ecosystem Thinking | [02](02-product-thinking/CHAPTER.md) |
| End-to-End Testing | [18](18-testing/CHAPTER.md) |
| Engineering Culture | [03](03-engineering-principles/CHAPTER.md) |
| Engineering Operations | [19](19-devops/CHAPTER.md) |
| Engineering Principles | [03](03-engineering-principles/CHAPTER.md) |
| Engineering Workflow | [04](04-development-methodology/CHAPTER.md) |
| Entities | [05](05-domain-driven-design/CHAPTER.md) |
| Evaluation Framework | [16](16-evaluation/CHAPTER.md) |
| Event APIs | [13](13-api-platform/CHAPTER.md) |
| Event Storage | [12](12-data-platform/CHAPTER.md) |
| Events | [05](05-domain-driven-design/CHAPTER.md) |
| Evolution Strategy | [20](20-roadmap/CHAPTER.md) |
| Evolvability | [03](03-engineering-principles/CHAPTER.md) |
| Execution Model | [07](07-runtime-platform/CHAPTER.md) |
| Explainability | [17](17-ui-ux/CHAPTER.md) |
| Extensibility as a Product Capability | [02](02-product-thinking/CHAPTER.md) |
| Extensions | [10](10-plugin-platform/CHAPTER.md) |
| External Systems | [10](10-plugin-platform/CHAPTER.md) |
| Feature Flags | [11](11-control-plane/CHAPTER.md) |
| Feedback | [17](17-ui-ux/CHAPTER.md) |
| GitOps | [19](19-devops/CHAPTER.md) |
| Health | [14](14-observability/CHAPTER.md) |
| Human Evaluation | [16](16-evaluation/CHAPTER.md) |
| Human in the Loop | [17](17-ui-ux/CHAPTER.md) |
| Human Interaction | [17](17-ui-ux/CHAPTER.md) |
| Identity | [11](11-control-plane/CHAPTER.md) |
| Infrastructure Lifecycle | [19](19-devops/CHAPTER.md) |
| Innovation Management | [20](20-roadmap/CHAPTER.md) |
| Integration APIs | [13](13-api-platform/CHAPTER.md) |
| Integration Testing | [18](18-testing/CHAPTER.md) |
| Internal and External Platform Products | [02](02-product-thinking/CHAPTER.md) |
| Internal APIs | [13](13-api-platform/CHAPTER.md) |
| Iterative Development | [04](04-development-methodology/CHAPTER.md) |
| Jobs To Be Done | [02](02-product-thinking/CHAPTER.md) |
| Knowledge Assets | [12](12-data-platform/CHAPTER.md) |
| Latency Awareness | [09](09-provider-platform/CHAPTER.md) |
| LLM Providers | [09](09-provider-platform/CHAPTER.md) |
| Logs | [14](14-observability/CHAPTER.md) |
| Long-term Evolution | [20](20-roadmap/CHAPTER.md) |
| Low-Code Development | [08](08-builder-platform/CHAPTER.md) |
| Maintainability | [03](03-engineering-principles/CHAPTER.md) |
| MCP Integration | [10](10-plugin-platform/CHAPTER.md) |
| Memory Coordination | [07](07-runtime-platform/CHAPTER.md) |
| Memory Persistence | [12](12-data-platform/CHAPTER.md) |
| Metadata | [12](12-data-platform/CHAPTER.md) |
| Metrics | [14](14-observability/CHAPTER.md) |
| Model Catalog | [09](09-provider-platform/CHAPTER.md) |
| Model Selection | [09](09-provider-platform/CHAPTER.md) |
| Monitoring | [14](14-observability/CHAPTER.md) |
| Multi-Provider Strategy | [09](09-provider-platform/CHAPTER.md) |
| Multi-Tenancy | [11](11-control-plane/CHAPTER.md) |
| Naming Standards | [21](21-glossary/CHAPTER.md) |
| No-Code Development | [08](08-builder-platform/CHAPTER.md) |
| Observability | [14](14-observability/CHAPTER.md) |
| Operational Automation | [19](19-devops/CHAPTER.md) |
| Operational Governance | [11](11-control-plane/CHAPTER.md) |
| Operational Readiness | [19](19-devops/CHAPTER.md) |
| Operational Visibility | [14](14-observability/CHAPTER.md) |
| Operator Experience | [17](17-ui-ux/CHAPTER.md) |
| Platform Adoption | [02](02-product-thinking/CHAPTER.md) |
| Platform APIs | [13](13-api-platform/CHAPTER.md) |
| Platform Composability | [02](02-product-thinking/CHAPTER.md) |
| Platform Configuration | [11](11-control-plane/CHAPTER.md) |
| Platform Data | [12](12-data-platform/CHAPTER.md) |
| Platform Experience | [17](17-ui-ux/CHAPTER.md) |
| Platform Extensibility | [10](10-plugin-platform/CHAPTER.md) |
| Platform Governance | [11](11-control-plane/CHAPTER.md) |
| Platform Layers | [06](06-reference-architecture/CHAPTER.md) |
| Platform Network Effects | [02](02-product-thinking/CHAPTER.md) |
| Platform Operations | [19](19-devops/CHAPTER.md) |
| Platform Planes | [06](06-reference-architecture/CHAPTER.md) |
| Platform Signals | [14](14-observability/CHAPTER.md) |
| Platform Testing | [18](18-testing/CHAPTER.md) |
| Platform Thinking | [02](02-product-thinking/CHAPTER.md) |
| Platform Trust Model | [15](15-security/CHAPTER.md) |
| Plugin Architecture | [10](10-plugin-platform/CHAPTER.md) |
| Plugin Contracts | [10](10-plugin-platform/CHAPTER.md) |
| Plugin Lifecycle | [10](10-plugin-platform/CHAPTER.md) |
| Policies | [11](11-control-plane/CHAPTER.md) |
| Primary users (introduced here; analyzed in Chapter 02) | [01](01-platform-vision/CHAPTER.md) |
| Privacy | [15](15-security/CHAPTER.md) |
| Product Boundaries | [02](02-product-thinking/CHAPTER.md) |
| Product Capabilities | [02](02-product-thinking/CHAPTER.md) |
| Product Evolution | [02](02-product-thinking/CHAPTER.md) |
| Product Evolution Roadmap | [20](20-roadmap/CHAPTER.md) |
| Product Personas | [02](02-product-thinking/CHAPTER.md) |
| Product Philosophy | [02](02-product-thinking/CHAPTER.md) |
| Product Quality Attributes | [02](02-product-thinking/CHAPTER.md) |
| Product Vision translation into Product Strategy | [02](02-product-thinking/CHAPTER.md) |
| Prompt Assets | [08](08-builder-platform/CHAPTER.md) |
| Prompt Evaluation | [16](16-evaluation/CHAPTER.md) |
| Provider Abstraction | [09](09-provider-platform/CHAPTER.md) |
| Provider Capabilities | [09](09-provider-platform/CHAPTER.md) |
| Provider Independence | [09](09-provider-platform/CHAPTER.md) |
| Public APIs | [13](13-api-platform/CHAPTER.md) |
| Quality by Design | [03](03-engineering-principles/CHAPTER.md) |
| Quality Evaluation | [16](16-evaluation/CHAPTER.md) |
| Quotas | [11](11-control-plane/CHAPTER.md) |
| Reference Architecture | [06](06-reference-architecture/CHAPTER.md) |
| Regression Testing | [18](18-testing/CHAPTER.md) |
| Release Management | [19](19-devops/CHAPTER.md) |
| Release Philosophy | [20](20-roadmap/CHAPTER.md) |
| Reliability Evaluation | [16](16-evaluation/CHAPTER.md) |
| Reusable Components | [08](08-builder-platform/CHAPTER.md) |
| Review Process | [04](04-development-methodology/CHAPTER.md) |
| Routing Policies | [09](09-provider-platform/CHAPTER.md) |
| Runtime Boundaries | [07](07-runtime-platform/CHAPTER.md) |
| Runtime Platform | [07](07-runtime-platform/CHAPTER.md) |
| Runtime Responsibilities | [07](07-runtime-platform/CHAPTER.md) |
| Runtime Testing | [18](18-testing/CHAPTER.md) |
| Scheduling | [07](07-runtime-platform/CHAPTER.md) |
| Secrets Management | [15](15-security/CHAPTER.md) |
| Secure by Design | [15](15-security/CHAPTER.md) |
| Security Architecture | [15](15-security/CHAPTER.md) |
| Security Principles | [15](15-security/CHAPTER.md) |
| Session | [07](07-runtime-platform/CHAPTER.md) |
| Simplicity | [03](03-engineering-principles/CHAPTER.md) |
| Skills | [10](10-plugin-platform/CHAPTER.md) |
| SLO | [14](14-observability/CHAPTER.md) |
| Spec Driven Development | [04](04-development-methodology/CHAPTER.md) |
| State | [07](07-runtime-platform/CHAPTER.md) |
| State Persistence | [12](12-data-platform/CHAPTER.md) |
| Structured Data | [12](12-data-platform/CHAPTER.md) |
| Success Metrics | [16](16-evaluation/CHAPTER.md) |
| Technical Debt Strategy | [20](20-roadmap/CHAPTER.md) |
| Technical Excellence | [03](03-engineering-principles/CHAPTER.md) |
| Telemetry | [14](14-observability/CHAPTER.md) |
| Templates | [08](08-builder-platform/CHAPTER.md) |
| Test Automation | [18](18-testing/CHAPTER.md) |
| Test Pyramid | [18](18-testing/CHAPTER.md) |
| Test Quality | [18](18-testing/CHAPTER.md) |
| Testing Strategy | [18](18-testing/CHAPTER.md) |
| Threat Modeling | [15](15-security/CHAPTER.md) |
| Tools | [10](10-plugin-platform/CHAPTER.md) |
| Traces | [14](14-observability/CHAPTER.md) |
| Transparency | [17](17-ui-ux/CHAPTER.md) |
| Ubiquitous Language | [05](05-domain-driven-design/CHAPTER.md) |
| Unit Testing | [18](18-testing/CHAPTER.md) |
| User Experience | [17](17-ui-ux/CHAPTER.md) |
| Value Objects | [05](05-domain-driven-design/CHAPTER.md) |
| Value Proposition | [02](02-product-thinking/CHAPTER.md) |
| Vector Data | [12](12-data-platform/CHAPTER.md) |
| Vendor Neutrality | [09](09-provider-platform/CHAPTER.md) |
| Versioning Strategy | [20](20-roadmap/CHAPTER.md) |
| Visual Composition | [08](08-builder-platform/CHAPTER.md) |
| Vocabulary | [21](21-glossary/CHAPTER.md) |
| What an AI Agent Platform is (vision level) | [01](01-platform-vision/CHAPTER.md) |
| Why this class of platform exists | [01](01-platform-vision/CHAPTER.md) |
| Why traditional product thinking is insufficient | [02](02-product-thinking/CHAPTER.md) |
| Workflow Composition | [08](08-builder-platform/CHAPTER.md) |
| Zero Trust | [15](15-security/CHAPTER.md) |

## Chapter cross-reference matrix

Which chapters each chapter links to (chapter-level).

| Chapter | References |
|---------|-----------|
| 00 Introduction | 01, 02, 03, 04, 06, 20, 21 |
| 01 Platform Vision | 00, 02, 03, 06, 16, 20, 21 |
| 02 Product Thinking | 01, 03, 06, 10, 16, 20, 21 |
| 03 Engineering Principles | 00, 02, 04, 06, 21 |
| 04 Development Methodology | 00, 03, 05, 06, 16, 18, 21 |
| 05 Domain-Driven Design | 04, 06, 21 |
| 06 Reference Architecture | 01, 02, 03, 05, 07, 08, 09, 10, 11, 12, 13, 14, 15, 16, 21 |
| 07 Runtime Platform | 06, 08, 09, 10, 11, 12, 14, 15, 16, 21 |
| 08 Builder Platform | 02, 03, 06, 07, 09, 10, 11, 12, 21 |
| 09 Provider Platform | 02, 03, 06, 07, 10, 11, 21 |
| 10 Plugin Platform | 02, 03, 06, 07, 08, 09, 11, 12, 21 |
| 11 Control Plane | 03, 06, 07, 08, 09, 10, 12, 15, 21 |
| 12 Data Platform | 03, 05, 06, 07, 08, 11, 14, 21 |
| 13 API Platform | 03, 05, 06, 10, 11, 12, 14, 21 |
| 14 Observability | 03, 06, 07, 12, 15, 16, 21 |
| 15 Security | 03, 06, 11, 12, 14, 16, 21 |
| 16 Evaluation | 01, 02, 03, 06, 07, 08, 12, 14, 17, 18, 21 |
| 17 User Experience | 02, 03, 06, 08, 11, 14, 21 |
| 18 Testing | 03, 04, 06, 07, 13, 16, 19, 21 |
| 19 DevOps | 03, 06, 07, 11, 14, 18, 20, 21 |
| 20 Roadmap | 01, 02, 03, 06, 13, 19, 21 |
| 21 Glossary | 01, 02, 03, 04, 05, 06, 07, 09, 10, 11, 12, 14, 15, 16 |

### Chapter 22 — Context & Prompt Engineering

Owns 8 concept(s). Related concepts are the siblings listed here.

| Concept | Referenced by |
|---------|---------------|
| Context Engineering | — |
| Prompt | — |
| Prompt layering | — |
| Context | — |
| Context assembly | — |
| Context window | — |
| Context budget | — |
| Prompt lifecycle | — |

### Chapter 23 — Tool & Function Architecture

Owns 7 concept(s). Related concepts are the siblings listed here.

| Concept | Referenced by |
|---------|---------------|
| Tool | — |
| Tool contract | — |
| Tool registry | — |
| Tool permissioning | — |
| Side-effect class | — |
| Human-in-the-loop approval | — |
| Action reversibility | — |

### Chapter 24 — Multi-Agent Coordination

Owns 7 concept(s). Related concepts are the siblings listed here.

| Concept | Referenced by |
|---------|---------------|
| Multi-agent system | — |
| Agent role | — |
| Coordination topology | — |
| Supervisor pattern | — |
| Handoff | — |
| Agent-to-agent contract | — |
| Convergence and termination | — |

### Chapter 25 — Memory & Conversational State

Owns 7 concept(s). Related concepts are the siblings listed here.

| Concept | Referenced by |
|---------|---------------|
| Agent memory | — |
| Working memory | — |
| Long-term memory | — |
| Memory scope | — |
| Memory write policy | — |
| Retention and forgetting | — |
| Memory retrieval into context | — |

### Chapter 26 — Agentic Security

Owns 7 concept(s). Related concepts are the siblings listed here.

| Concept | Referenced by |
|---------|---------------|
| Agentic threat surface | — |
| Prompt injection | — |
| Jailbreak | — |
| Guardrail | — |
| Autonomy level | — |
| Human-in-the-loop safety boundary | — |
| Least-authority agent | — |

### Chapter 27 — Evaluation-Driven Development

Owns 5 concept(s). Related concepts are the siblings listed here.

| Concept | Referenced by |
|---------|---------------|
| Evaluation-Driven Development | — |
| Evaluation-first workflow | — |
| Behavioral acceptance criteria | — |
| Behavioral regression gate | — |
| Behavioral baseline | — |
