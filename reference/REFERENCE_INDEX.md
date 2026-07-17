# Reference Index

The navigation index for the APEF reference studies: analytical studies of external agent frameworks and platforms, each drawing architectural lessons for the APEF without endorsing or prescribing any technology. The APEF itself remains technology- and vendor-neutral; these studies name external technologies only because analyzing them is the purpose of this area.

**10 studies.** Each maps its takeaways to the [Platform Capability Model](../handbook/PLATFORM_CAPABILITY_MODEL.md) capability that owns the concern.

## Studies

| Study | Category | Informs chapters |
|-------|----------|------------------|
| [LangGraph](./langgraph/STUDY.md) | agent orchestration library | 07, 08, 12 |
| [Agno](./agno/STUDY.md) | lightweight multi-agent framework | 07, 08, 12 |
| [OpenAI Agents SDK](./openai-agents-sdk/STUDY.md) | provider-native agents SDK | 07, 09, 15 |
| [Google ADK](./google-adk/STUDY.md) | enterprise agent development kit | 11, 16, 19 |
| [CrewAI](./crewai/STUDY.md) | role-based multi-agent framework | 08, 11, 16 |
| [AutoGen](./autogen/STUDY.md) | conversational multi-agent framework | 07, 14, 17 |
| [Azure AI Foundry](./azure-ai-foundry/STUDY.md) | enterprise AI platform | 09, 11, 16 |
| [Copilot Studio](./copilot-studio/STUDY.md) | low-code agent builder | 08, 10, 11 |
| [Dify](./dify/STUDY.md) | open-source LLMOps platform | 08, 12, 19 |
| [Flowise](./flowise/STUDY.md) | visual LLM workflow builder | 08, 17 |

## Takeaways by capability (which studies inform each chapter)

| Capability (chapter) | Studies that inform it |
|----------------------|------------------------|
| 07 Runtime Platform | LangGraph, Agno, OpenAI Agents SDK, AutoGen |
| 08 Builder Platform | LangGraph, Agno, CrewAI, Copilot Studio, Dify, Flowise |
| 09 Provider Platform | OpenAI Agents SDK, Azure AI Foundry |
| 10 Plugin Platform | Copilot Studio |
| 11 Control Plane | Google ADK, CrewAI, Azure AI Foundry, Copilot Studio |
| 12 Data Platform | LangGraph, Agno, Dify |
| 14 Observability | AutoGen |
| 15 Security | OpenAI Agents SDK |
| 16 Evaluation | Google ADK, CrewAI, Azure AI Foundry |
| 17 User Experience | AutoGen, Flowise |
| 19 DevOps | Google ADK, Dify |

## Conventions

- Every study is analysis, not endorsement or implementation guidance.
- Takeaways are architectural lessons for the APEF, mapped to the owning chapter, and never prescribe adopting a studied technology.
- Directory READMEs are frozen Foundation artifacts and are unchanged; each study lives in its directory's `STUDY.md`.
