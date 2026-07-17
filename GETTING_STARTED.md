# Getting Started with APEF

The Agent Platform Engineering Framework (APEF) is an **engineering framework** for building
enterprise-grade AI agent platforms — a body of methodology, knowledge, and governance, analogous to
a well-architected framework or an engineering handbook. It is **not software**: it contains no
application code and prescribes no technology or vendor. You bring the stack; APEF gives you the
discipline to build the platform well.

This guide is the on-ramp. It gives you a mental model in five minutes and a guided path to applying
the framework to your own platform. For the full map, see the [Framework Map](docs/FRAMEWORK_MAP.md).

## Who this is for

Enterprise, platform, software, AI, and security architects; platform engineering leads; and the
teams building an internal AI agent platform. If you are deciding *how* to engineer such a platform —
not which product to buy — APEF is for you.

## The five-minute mental model

APEF is organized in layers, each with one job:

| Layer | Answers | Start at |
|-------|---------|----------|
| **Knowledge** — the Handbook | *What* a platform is and how it should be architected | [Handbook Summary](handbook/HANDBOOK_SUMMARY.md) |
| **Specification** | How intent becomes specified work before it is built | [Specification Framework](specifications/SPECIFICATION_FRAMEWORK.md) |
| **Execution** | How engineering work is actually carried out (commands, roles, workflows, gates) | [Execution Framework](execution/EXECUTION_FRAMEWORK.md) |
| **Decision** | How significant choices are recorded and evolved | [ADR Framework](adrs/ADR_FRAMEWORK.md) |
| **Architecture Modeling** | How architecture is modeled, reviewed, and communicated | [Architecture Modeling Framework](architecture/ARCHITECTURE_MODELING_FRAMEWORK.md) |
| **Governance** | Who decides, and by what rules | [Architecture Charter](governance/ARCHITECTURE_CHARTER.md) |

The **Handbook is the source of truth**; every other layer conforms to it. Two ideas run through all
of it: **Specification-Driven Development** (specify intent before building) and, for the
probabilistic behavior of agents, **Evaluation-Driven Development** (gate every behavior-shaping
change on measured evaluation).

## Build your first agent platform with APEF

A guided path. Each step is a decision you make for *your* platform, pointing to the chapter or
framework that guides it. Nothing here names a technology — the neutrality is deliberate; you apply it
in your own stack.

1. **Frame the vision and the product.** Establish what your platform is for and who it serves, before
   any architecture. → [Ch 01 Platform Vision](handbook/01-platform-vision/CHAPTER.md),
   [Ch 02 Product Thinking](handbook/02-product-thinking/CHAPTER.md), captured as a
   [vision specification](specifications/vision/).
2. **Discover the domain.** Explore the domain and its capabilities. →
   [Ch 05 Domain-Driven Design](handbook/05-domain-driven-design/CHAPTER.md),
   [event storming](architecture/event-storming/MODELING.md) → [discovery](specifications/discovery/)
   and [capability](specifications/capabilities/) specifications.
3. **Set the architecture.** Anchor on the reference architecture and its planes; model the structure.
   → [Ch 06 Reference Architecture](handbook/06-reference-architecture/CHAPTER.md), the
   [Platform Capability Model](handbook/PLATFORM_CAPABILITY_MODEL.md), and
   [C4 view modeling](architecture/c4/MODELING.md).
4. **Design the platform capabilities.** Runtime, builder, provider, plugin, control, data, and API
   planes. → [Ch 07–13](handbook/HANDBOOK_SUMMARY.md).
5. **Engineer the agentic core.** The disciplines specific to agents — this is where agent platforms
   are won or lost. → [Ch 22 Context & Prompt Engineering](handbook/22-context-and-prompt-engineering/CHAPTER.md),
   [Ch 23 Tool & Function Architecture](handbook/23-tool-and-function-architecture/CHAPTER.md),
   [Ch 24 Multi-Agent Coordination](handbook/24-multi-agent-coordination/CHAPTER.md),
   [Ch 25 Memory & Conversational State](handbook/25-memory-and-conversational-state/CHAPTER.md).
6. **Secure it for agents.** Treat all model-facing content as untrusted; bound autonomy; gate
   irreversible actions. → [Ch 15 Security](handbook/15-security/CHAPTER.md) and
   [Ch 26 Agentic Security](handbook/26-agentic-security/CHAPTER.md).
7. **Make quality measurable.** Observe, test the deterministic parts, and **evaluate** the
   probabilistic behavior — gating every change. → [Ch 14 Observability](handbook/14-observability/CHAPTER.md),
   [Ch 18 Testing](handbook/18-testing/CHAPTER.md), [Ch 16 Evaluation](handbook/16-evaluation/CHAPTER.md),
   [Ch 27 Evaluation-Driven Development](handbook/27-evaluation-driven-development/CHAPTER.md).
8. **Record decisions and ship.** Capture significant choices as [ADRs](adrs/ADR_FRAMEWORK.md), pass the
   [quality gates](bootstrap/QUALITY_GATES.md), and release via the
   [release process](bootstrap/RELEASE_PROCESS.md).

You will not do these strictly in sequence — but this is the shape of engineering a platform with
APEF: intent → domain → architecture → capabilities → agentic core → security → measured quality →
governed release.

## Reading paths by role

- **Enterprise / Platform Architect:** Ch 00–06, then the plane chapters (07–13), then the
  [Architecture Modeling Framework](architecture/ARCHITECTURE_MODELING_FRAMEWORK.md).
- **AI / Agent Engineer:** the agentic core (Ch 22–25), then Ch 16 and Ch 27 (evaluation), then Ch 07
  (runtime).
- **Security Architect:** Ch 15, then Ch 26 (agentic security), then Ch 23 (tool safety).
- **Engineering Lead:** the [Execution Framework](execution/EXECUTION_FRAMEWORK.md), the
  [Specification Framework](specifications/SPECIFICATION_FRAMEWORK.md), and the
  [Workflow](bootstrap/WORKFLOW.md).

## Conventions worth knowing early

- **Technology-neutral.** The framework names no products; you map it onto your stack. External
  technologies are analyzed only in [reference studies](reference/REFERENCE_INDEX.md).
- **Single concept ownership.** Every concept is defined in exactly one chapter; everything else
  references it. Follow the link to the owner rather than expecting a redefinition.
- **Specify, then build; evaluate, then change.** SDD and EDD are the two habits the whole framework
  rests on.

## See it applied end to end

The [Reference Platform](examples/reference-platform/README.md) is a complete, neutral worked instance
that walks this exact path for one scenario — vision, domain, architecture, the agentic core,
evaluation, and decisions — so you can see what applying APEF actually produces before you start.

## Where to go next

- The [Framework Map](docs/FRAMEWORK_MAP.md) and [Framework Index](docs/FRAMEWORK_INDEX.md) for the
  full structure.
- The [Handbook](handbook/HANDBOOK_SUMMARY.md) to go deep.
- [CONTRIBUTING](CONTRIBUTING.md) and the [Engineering Guide](bootstrap/ENGINEERING_GUIDE.md) to
  contribute to the framework itself.
