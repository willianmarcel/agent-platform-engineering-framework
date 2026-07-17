# Execution Architecture

How the parts of the APEF Execution Framework relate, shown conceptually. These diagrams
explain the framework's structure and process; they are not implementation and contain no
technology. They are consistent with the [Execution Framework](EXECUTION_FRAMEWORK.md) and the
Handbook it operationalizes.

## The model in one sentence

A **workflow** advances through stages; each stage runs a **command** executed by **skills**
under a **prompt contract**; the command's output is admitted only when the applicable
**reviews** pass their **quality gates** — and every part traces to the Handbook chapter that
owns its concern.

## 1. Command orchestration

The commands as they typically sequence, from establishing an effort to release. Not every
command runs in every workflow; workflows select and order them.

```mermaid
graph LR
  IP["init-project"] --> DD["discover-domain"]
  DD --> WS["write-spec"]
  WS --> RS["review-spec"]
  RS --> DA["design-architecture"]
  DA --> WA["write-adr"]
  DA --> IF["implement-feature"]
  IF --> GT["generate-tests"]
  IF --> RC["review-code"]
  RC --> SR["security-review"]
  SR --> REL["release"]
```

## 2. Skill collaboration

The specialist skills and who defers to whom. The Enterprise Architect holds
whole-of-platform coherence; the Security Architect is consulted across all; the Code Reviewer
hands AI-quality concerns to the AI Architect.

```mermaid
graph TB
  EA["Enterprise Architect<br/>(coherence)"]
  PA["Product Architect"]
  PLA["Platform Architect"]
  RA["Runtime Architect"]
  AIA["AI Architect"]
  OA["Observability Architect"]
  DE["Domain Expert"]
  SA["Security Architect"]
  TW["Technical Writer"]
  CR["Code Reviewer"]
  EA --> PA
  EA --> PLA
  PA --> DE
  PLA --> RA
  PLA --> AIA
  PLA --> OA
  DE --> PA
  CR --> TW
  CR --> AIA
  SA --> EA
```

## 3. Workflow lifecycle

The stages a workflow passes through, each gated; a failed gate returns the work to the
previous stage.

```mermaid
stateDiagram-v2
  [*] --> Specify
  Specify --> Design: specification gate
  Design --> Realize: architecture gate
  Realize --> Review: definition-of-done gate
  Review --> Release: all dimension gates
  Release --> [*]: release-readiness gate
  Review --> Realize: return
  Design --> Specify: return
```

## 4. Decision flow

The gate decision applied at the end of every stage.

```mermaid
graph TD
  A["Stage output"] --> B{"Applicable gates pass?"}
  B -->|yes| C["Advance to next stage"]
  B -->|no| D["Record findings by severity"]
  D --> E["Return to owning skill"]
  E --> A
```

## 5. Review pipeline

The nine review dimensions in order; the artifact advances only when all applicable
dimensions pass.

```mermaid
graph LR
  P["Product"] --> D["Domain"] --> A["Architecture"] --> S["Security"] --> R["Runtime"] --> PF["Performance"] --> O["Observability"] --> T["Testing"] --> DOC["Documentation"] --> V{"All applicable pass?"}
  V -->|yes| ADV["Advance"]
  V -->|no| RET["Return with findings"]
```

## Traceability

Every element above traces to the Handbook: commands and reviews cite their owning chapters
in the [Command Catalog](COMMAND_CATALOG.md) and [Review Framework](REVIEW_FRAMEWORK.md);
skills cite theirs in the [Skill Catalog](SKILL_CATALOG.md); gates cite theirs in
[Quality Gates](QUALITY_GATES.md). The framework is an operating layer over the normative
Handbook and never contradicts it.

## Conventions

- The diagrams are conceptual and technology-neutral; they name framework elements and their
  relationships, never technologies.
- They are kept consistent with the catalogs; if a catalog changes, the diagrams change with
  it.
