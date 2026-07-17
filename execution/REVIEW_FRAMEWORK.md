# Review Framework

The Review Framework is the reusable, multi-dimension review model of the APEF Execution
Framework. Any artifact — specification, architecture, change, or release candidate — is
reviewed along the same nine dimensions, each owned by a [skill](SKILL_CATALOG.md), against
the Handbook chapter that owns the concern, and gated by the corresponding
[quality gate](QUALITY_GATES.md). Reviews find and record; they do not implement.

## The review model

Each review dimension has: an **owning skill**, the **question it answers**, its **Handbook
authority**, and its **gate**. A dimension applies when the artifact touches its concern; a
review pipeline runs the applicable dimensions in the order below.

| # | Dimension | Owning skill | Question it answers | Handbook | Gate |
|---|-----------|--------------|---------------------|----------|------|
| 1 | Product | Product Architect | Does it serve the right personas, jobs, and outcomes? | [02](../handbook/02-product-thinking/CHAPTER.md) | product gate |
| 2 | Domain | Domain Expert | Does it reflect the domain and its ubiquitous language? | [05](../handbook/05-domain-driven-design/CHAPTER.md) | domain gate |
| 3 | Architecture | Platform / Enterprise Architect | Does it fit the reference architecture and respect boundaries? | [06](../handbook/06-reference-architecture/CHAPTER.md) | architecture gate |
| 4 | Security | Security Architect | Is it secure by design against the trust model? | [15](../handbook/15-security/CHAPTER.md) | security gate |
| 5 | Runtime | Runtime Architect | Does it execute soundly within runtime boundaries? | [07](../handbook/07-runtime-platform/CHAPTER.md) | runtime gate |
| 6 | Performance | Runtime / Platform Architect | Does it meet the architectural quality attributes? | [06](../handbook/06-reference-architecture/CHAPTER.md) | performance gate |
| 7 | Observability | Observability Architect | Is it observable and operationally ready? | [14](../handbook/14-observability/CHAPTER.md) | observability gate |
| 8 | Testing | Code Reviewer | Is software correctness verified (distinct from AI evaluation)? | [18](../handbook/18-testing/CHAPTER.md) | testing gate |
| 9 | Documentation | Technical Writer | Is it clear, consistent, and terminology-compliant? | [21](../handbook/21-glossary/CHAPTER.md) | documentation gate |

AI quality is assessed through [evaluation](../handbook/16-evaluation/CHAPTER.md), which is a
distinct discipline from the Testing dimension and is engaged by the AI Architect where
model-dependent behavior is involved.

## How a review is conducted

1. **Scope** — determine which dimensions apply to the artifact.
2. **Assess** — the owning skill of each applicable dimension assesses against its question
   and Handbook authority.
3. **Record** — findings are recorded with severity; each dimension yields a verdict (pass,
   pass-with-findings, or return).
4. **Gate** — the artifact advances only when every applicable dimension passes its gate.

## Review verdict structure (illustrative, non-executable)

```
Artifact:     <what was reviewed>
Dimensions:   <applicable dimensions>
Findings:     <per dimension: finding, severity>
Verdicts:     <per dimension: pass | pass-with-findings | return>
Outcome:      <advance | return>  (advance only if all applicable gates pass)
```

## Composition

- A **command** invokes the review dimensions relevant to its output (see the
  [Command Catalog](COMMAND_CATALOG.md)).
- A **workflow** composes reviews across stages; the *Release preparation* workflow runs the
  full pipeline (all nine dimensions).
- The dimensions map one-to-one onto the framework's [quality gates](QUALITY_GATES.md).

## Extensibility

New review dimensions may be added when a new cross-cutting concern is introduced, provided
each has a single owning skill, a Handbook authority, and a measurable gate — preserving the
model's one-owner, one-gate discipline.
