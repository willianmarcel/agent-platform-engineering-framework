# APEF Execution Framework

The Execution Framework turns the [APEF Engineering Handbook](../handbook/HANDBOOK_SUMMARY.md)
— the normative source of truth — into an **executable engineering framework**: a set of
commands, skills, workflows, prompt contracts, a review model, and quality gates through
which important engineering activities become repeatable. It is the engineering operating
system for AI-assisted development of AI Agent Platforms.

This framework produces **no application code, no CLI scripts, and no executable
automation**. It defines architecture, contracts, and engineering process. It is provider-,
language-, and technology-agnostic, consistent with the Handbook it operationalizes.

## The parts and how they fit

| Part | Document | What it defines |
|------|----------|-----------------|
| Commands | [COMMAND_CATALOG.md](COMMAND_CATALOG.md) | Repeatable engineering activities, as contracts |
| Skills | [SKILL_CATALOG.md](SKILL_CATALOG.md) | Specialist engineering roles and their boundaries |
| Workflows | [WORKFLOW_CATALOG.md](WORKFLOW_CATALOG.md) | End-to-end orchestrations of commands and skills |
| Reviews | [REVIEW_FRAMEWORK.md](REVIEW_FRAMEWORK.md) | The reusable multi-dimension review model |
| Quality gates | [QUALITY_GATES.md](QUALITY_GATES.md) | Measurable gates every workflow must pass to progress |
| Architecture | [EXECUTION_ARCHITECTURE.md](EXECUTION_ARCHITECTURE.md) | How the parts relate, with conceptual diagrams |

A **workflow** orchestrates **commands**; each command is executed by one or more **skills**
following a **prompt contract**; a command's output is admitted only when it passes the
relevant **reviews** and **quality gates**. Every command and skill derives its authority
from the Handbook chapter that owns the concern it addresses.

## Principles

- **Handbook-normative.** Every command, skill, and workflow traces to the Handbook chapter
  that owns its concern; the framework never contradicts the Handbook.
- **Specification-driven.** Work proceeds from specification to architecture to
  implementation, per [Chapter 04](../handbook/04-development-methodology/CHAPTER.md).
- **Contracts, not scripts.** The framework defines what each activity requires, produces,
  and guarantees — never how it is implemented.
- **Separation of concerns.** Each skill has a bounded mission and decision authority; each
  command has one responsibility.
- **Gate before progress.** No workflow stage advances until its quality gates pass.
- **Technology-agnostic.** No provider, language, framework, or tool is named or required.

## Prompt Contracts

Every prompt the framework uses — to invoke a command or engage a skill — follows one
standard structure, so that engagements are consistent, reviewable, and reproducible. A
prompt contract has seven parts:

1. **Context** — the situation and the relevant Handbook chapters and prior artifacts the
   work builds on.
2. **Objectives** — what the engagement must achieve, stated as outcomes.
3. **Constraints** — the boundaries that must hold (architectural altitude, concept
   ownership, technology neutrality, and any activity-specific limits).
4. **Inputs** — the artifacts and information provided, each identified and located.
5. **Expected Outputs** — the artifacts to be produced, with their form and destination.
6. **Validation** — how the outputs are checked: the reviews and quality gates that apply.
7. **Completion Criteria** — the explicit conditions under which the engagement is done.

A prompt contract is satisfied only when every Expected Output exists, Validation passes, and
the Completion Criteria are met. Commands and skills declare their prompt contract by
reference to this structure; workflows compose them.

### Prompt contract template (illustrative, non-executable)

```
Context:            <situation; Handbook chapters; prior artifacts>
Objectives:         <outcomes to achieve>
Constraints:        <altitude, ownership, neutrality, activity limits>
Inputs:             <identified artifacts and information>
Expected Outputs:   <artifacts, form, destination>
Validation:         <applicable reviews and quality gates>
Completion Criteria:<explicit done conditions>
```

## How to read this framework

- Start here for the model, then read [EXECUTION_ARCHITECTURE.md](EXECUTION_ARCHITECTURE.md)
  for how the parts relate.
- Consult the catalogs for the definitions of commands, skills, and workflows.
- Apply [REVIEW_FRAMEWORK.md](REVIEW_FRAMEWORK.md) and [QUALITY_GATES.md](QUALITY_GATES.md)
  at every stage.

## Relationship to the repository

- The Handbook ([`../handbook/`](../handbook/)) is the normative source of truth this
  framework executes.
- The framework's role definitions live in [`skills/`](skills/), command contracts in
  [`commands/`](commands/), and workflow definitions in [`workflows/`](workflows/); each
  file points to its full definition in the corresponding catalog.
- Templates the commands produce artifacts from live in [`../templates/`](../templates/); the
  playbooks the reviews draw on live in [`../playbooks/`](../playbooks/).
