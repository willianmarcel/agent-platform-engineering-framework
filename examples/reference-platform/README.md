# Reference Platform — a worked end-to-end instance

## Overview
A single, coherent worked instance that applies APEF end to end to one concrete (but
technology-neutral) scenario. It fills in the actual artifact set the framework prescribes — vision,
capabilities, domain, architecture models, the agentic-core design, an evaluation plan, and decision
records — so a reader can see exactly what engineering a platform *with* APEF produces.

## Purpose
To make the methodology concrete. The Handbook says *how* to engineer an agent platform; this instance
shows the *result* of doing so for one case — a complete, reviewable design, not prose about designing.

## Responsibilities
- Demonstrate the full APEF path (vision → domain → architecture → agentic core → evaluation →
  decisions) on one scenario, consistently.
- Show that the framework's artifacts compose into a coherent whole.

## Contents
- [`01-design.md`](01-design.md) — vision, capabilities, domain, and architecture (with C4 models).
- [`02-agentic-engineering.md`](02-agentic-engineering.md) — the agentic core applied: context, tools,
  memory, coordination, and security for this platform.
- [`03-evaluation-and-decisions.md`](03-evaluation-and-decisions.md) — the evaluation plan (behavioral
  gates) and the significant decisions as worked ADRs.

## Out of Scope
- Executable or deployable code (this is a **non-executable** worked instance, per AD-0014).
- Any technology, vendor, product, or SDK name (strict neutrality).
- Redefining concepts — every concept is owned by its Handbook chapter and referenced here.

## Relationships
- [Getting Started](../../GETTING_STARTED.md) — the guided path this instance realizes.
- [Handbook](../../handbook/HANDBOOK_SUMMARY.md) — the source of the concepts applied here.
- [Examples Index](../EXAMPLES_INDEX.md) — the other worked examples.

## References
- [AR-001 review](../../docs/AR-001_ARCHITECTURE_REVIEW.md) — identified the need for a concrete
  end-to-end instance; this is the neutral answer to it.

## Conventions
- Illustrative and non-executable: it may contain specifications, models, diagrams-as-code, and
  decision records, but no runnable code (AD-0014).
- Technology-neutral throughout; the reader maps it onto their own stack.

---

## The scenario (neutral)

**A Support Operations Assistant Platform.** An internal platform on which an enterprise builds agents
that help its support teams: an agent answers a support question from approved internal knowledge and,
where appropriate, takes *bounded* actions on the team's behalf — looking up a case, drafting a
response for review, or escalating. The platform serves many support teams (tenants), each with its
own knowledge and policies. It is described here entirely in business-and-architecture terms; no
technology is named. Read it alongside the [Getting Started](../../GETTING_STARTED.md) path — this
instance walks the same eight steps.
