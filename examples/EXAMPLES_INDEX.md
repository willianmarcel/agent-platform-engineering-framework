# Examples Index

The navigation index for the APEF worked examples: non-executable, technology-neutral artifacts that demonstrate APEF concepts. Per the Architecture Board's permanent rule, examples **demonstrate APEF concepts and never depend on any vendor-specific technology, product, framework, SDK, or implementation detail** (reference material, by contrast, analyzes external technologies). Every example is illustrative and names no technology.

**6 example areas.** Each area follows the Module Entry Pattern: a frozen directory README plus an `*_EXAMPLES.md` entry document and worked example artifacts.

## Example areas

| Area | Worked example | Demonstrates chapters |
|------|----------------|-----------------------|
| [Agent](./agents/AGENT_EXAMPLES.md) | [assistant-agent](./agents/example-assistant-agent.md) | 07, 08, 02, 09, 11 |
| [Workflow](./workflows/WORKFLOW_EXAMPLES.md) | [review-workflow](./workflows/example-review-workflow.md) | 08, 07, 17 |
| [Provider](./providers/PROVIDER_EXAMPLES.md) | [provider-integration](./providers/example-provider-integration.md) | 09 |
| [Plugin](./plugins/PLUGIN_EXAMPLES.md) | [lookup-tool-plugin](./plugins/example-lookup-tool-plugin.md) | 10 |
| [Supervisor](./supervisors/SUPERVISOR_EXAMPLES.md) | [coordinating-supervisor](./supervisors/example-coordinating-supervisor.md) | 11, 07, 17 |
| [Evaluation](./evaluations/EVALUATION_EXAMPLES.md) | [agent-evaluation](./evaluations/example-agent-evaluation.md) | 16, 18 |
| [Reference Platform](./reference-platform/README.md) | [end-to-end worked instance](./reference-platform/01-design.md) | 01–27 (end to end) |

## Concepts demonstrated by area

| Area | APEF concepts demonstrated |
|------|----------------------------|
| Agent | agent intent & lifecycle, agent assembly, provider abstraction, governance |
| Workflow | workflow composition, design-time vs run-time, human-in-the-loop |
| Provider | provider abstraction, model catalog, routing, cost/latency awareness, provider independence |
| Plugin | plugin architecture, contracts, lifecycle, protocol-oriented integration |
| Supervisor | coordination, control-plane governance, runtime execution, oversight |
| Evaluation | AI evaluation, human/automated methods, benchmarking, continuous evaluation, evaluation-vs-testing |
| Reference Platform | the full APEF path applied end to end: vision, domain, architecture, the agentic core (context, tools, memory, coordination, security), evaluation, and decisions |

## Conventions

- Examples are non-executable and name no technology, vendor, product, framework, or SDK.
- Every concept is referenced from its owning chapter and never redefined.
- Frozen directory READMEs are unchanged; entry documents carry the content (Module Entry Pattern).
