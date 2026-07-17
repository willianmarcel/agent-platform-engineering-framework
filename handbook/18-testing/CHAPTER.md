# Chapter 18 — Testing

## Introduction

This chapter defines testing for an AI Agent Platform: the discipline that verifies the
platform's software is correct. Its prerequisites are
[Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md) and
[Chapter 07 — Runtime Platform](../07-runtime-platform/CHAPTER.md).

Testing and evaluation are distinct disciplines and are kept separate throughout the
Handbook: **testing verifies software correctness** — deterministic behavior that is right
or wrong — while **evaluation measures the quality of AI**, which is owned exclusively by
[Chapter 16 — Evaluation](../16-evaluation/CHAPTER.md). Testing never evaluates AI quality.
This chapter defines a testing strategy as an architectural discipline — what is verified,
at which level, and to what standard — not any testing tool, framework, or technology. No
product is named and no implementation is prescribed.

## Objectives

After reading this chapter, a reader will be able to:

- Explain testing as the verification of software correctness, distinct from AI evaluation.
- Distinguish the levels of testing and how they compose into a strategy.
- Reason about contract, runtime, platform, and agent testing.
- Apply the test pyramid, regression testing, and test automation to sustain test quality.

## Concepts

This chapter **owns** the concepts below; other chapters reference them without redefining
them.

**Testing Strategy.** The deliberate plan for how the platform's software correctness is
verified — which levels of testing apply, to what, and to what standard. A testing strategy
makes verification systematic rather than incidental, and is the frame the other testing
concepts fit within.

**Unit Testing.** The verification of the smallest testable parts of the software in
isolation, confirming each behaves correctly on its own. Unit tests are the fastest and most
numerous, forming the base of the strategy.

**Integration Testing.** The verification that separately correct parts work correctly
together across their boundaries. Integration testing confirms that units combine as
intended.

**End-to-End Testing.** The verification that a complete path through the platform behaves
correctly from the outside. End-to-end tests are the fewest and most encompassing,
confirming the whole works as a user would exercise it.

**Contract Testing.** The verification that the parties to a contract — such as the API
contracts owned by [Chapter 13](../13-api-platform/CHAPTER.md) — each uphold their side.
Contract testing confirms that an interface's promise holds without exercising the full
systems behind it.

**Runtime Testing.** The verification that the runtime plane executes work correctly — its
lifecycle, scheduling, isolation, and state handling behave as specified. Runtime testing
verifies the runtime software owned by [Chapter 07](../07-runtime-platform/CHAPTER.md); it
does not evaluate the AI that runs on it.

**Platform Testing.** The verification that the platform's capabilities behave correctly as
an integrated whole. Platform testing is testing raised to the level of the platform,
confirming that its planes and cross-cutting capabilities operate correctly together.

**Agent Testing.** The verification of the deterministic, software aspects of an agent — its
structure, contracts, and control flow — as distinct from the evaluation of its AI behavior.
Agent testing confirms an agent's software is correct; [Chapter 16](../16-evaluation/CHAPTER.md)
judges whether its behavior is good.

**Regression Testing.** The verification that changes have not broken previously correct
behavior. Regression testing is how correctness is protected over time as the software
evolves.

**Test Automation.** The practice of running tests automatically and repeatably, so
verification is continual rather than occasional. Test automation is what makes a testing
strategy sustainable at scale.

**Test Pyramid.** The principle that a healthy strategy has many fast, isolated tests at the
base and few slow, encompassing tests at the top, with integration tests between. The test
pyramid balances confidence against cost and speed.

**Test Quality.** The degree to which tests are themselves trustworthy — meaningful, stable,
and maintained. Poor tests give false confidence; test quality is the discipline of keeping
the verification worth trusting.

## Principles

- **Test software; evaluate AI.** Verify deterministic correctness here, and leave the
  quality of model-dependent behavior to [Chapter 16](../16-evaluation/CHAPTER.md).
- **Shape the strategy as a pyramid.** Favor many fast, isolated tests over few slow ones,
  with integration in between.
- **Automate verification.** Run tests automatically and repeatably so correctness is
  continually protected.
- **Guard against regression.** Verify that change does not break what was correct.
- **Keep tests trustworthy.** Maintain test quality so the verification itself can be relied
  upon.
- **Uphold the platform's architectural principles.** Like every platform capability, testing
  is secure, observable, governable, explainable, and composable by design; provider-,
  cloud-, and runtime-agnostic; and vendor-neutral — as expressed in the
  [Platform Capability Model](../PLATFORM_CAPABILITY_MODEL.md) and owned by
  [Chapter 03](../03-engineering-principles/CHAPTER.md).

## Architecture

This section describes the structure of the *testing discipline*, within the
[Platform Capability Model](../PLATFORM_CAPABILITY_MODEL.md) and the reference architecture
owned by [Chapter 06](../06-reference-architecture/CHAPTER.md).

A testing strategy is organized by level and protected over time:

1. **Unit**, **integration**, and **end-to-end testing** form the **test pyramid**;
   **contract testing** verifies boundaries.
2. **Runtime**, **platform**, and **agent testing** apply these levels to specific subjects.
3. **Regression testing**, **test automation**, and **test quality** sustain verification as
   the software changes.

Testing verifies the software correctness of every plane and is the software counterpart to
AI [evaluation](../16-evaluation/CHAPTER.md); together they give a complete account of
quality. It is a discipline applied within the development methodology owned by
[Chapter 04](../04-development-methodology/CHAPTER.md), whose definition of done it helps
satisfy.

## Patterns

- **Pyramid-shaped strategy.** *Context:* designing verification. Build many fast unit tests,
  fewer integration tests, and few end-to-end tests.
- **Boundary contract tests.** *Context:* interfaces between parts. Verify each side of a
  contract independently so integration failures are localized.
- **Automated regression.** *Context:* evolving software. Run the suite automatically on
  change so regressions are caught immediately.

## Anti-patterns

- **Testing used to judge AI.** *Why it fails:* correctness tests cannot judge
  model-dependent quality. *Instead:* test software; evaluate AI.
- **Inverted pyramid.** *Why it fails:* relying on many slow end-to-end tests is fragile and
  costly. *Instead:* shape the strategy as a pyramid.
- **Manual-only verification.** *Why it fails:* verification that is not automated is not
  sustained. *Instead:* automate verification.
- **Untrustworthy tests.** *Why it fails:* flaky or meaningless tests give false confidence.
  *Instead:* keep tests trustworthy.

## Best Practices

- Verify software correctness here and delegate AI quality to
  [Chapter 16](../16-evaluation/CHAPTER.md).
- Compose unit, integration, and end-to-end testing as a pyramid, with contract testing at
  boundaries.
- Automate the suite and run it on every change to guard against regression.
- Maintain test quality so verification stays trustworthy.
- Let testing serve the definition of done owned by
  [Chapter 04](../04-development-methodology/CHAPTER.md).

## Examples

The following are illustrative, non-executable aids.

**Levels of testing (the pyramid):**

| Level | Verifies | Relative count |
|-------|----------|----------------|
| Unit | Smallest parts in isolation | Many |
| Integration | Parts working together | Fewer |
| End-to-end | A complete path from outside | Fewest |

**Testing and evaluation, distinguished:**

| Discipline | Judges | Owned by |
|------------|--------|----------|
| Testing | Correctness of deterministic software | This chapter |
| Evaluation | Quality of model-dependent AI behavior | [Chapter 16](../16-evaluation/CHAPTER.md) |

## Checklist

A reader is ready to proceed to
[Chapter 19 — DevOps](../19-devops/CHAPTER.md) when they can confirm:

- [ ] I can explain testing as verifying software correctness, distinct from evaluation.
- [ ] I can distinguish the levels of testing and shape them as a pyramid.
- [ ] I can reason about contract, runtime, platform, and agent testing.
- [ ] I can sustain verification through automation, regression testing, and test quality.

## References

- [Chapter 04 — Development Methodology](../04-development-methodology/CHAPTER.md) — owns the
  definition of done testing helps satisfy.
- [Chapter 06 — Reference Architecture](../06-reference-architecture/CHAPTER.md) — the frame
  that places testing.
- [Chapter 07 — Runtime Platform](../07-runtime-platform/CHAPTER.md) — the runtime software
  runtime testing verifies.
- [Chapter 13 — API Platform](../13-api-platform/CHAPTER.md) — owns the API contracts
  contract testing verifies.
- [Chapter 16 — Evaluation](../16-evaluation/CHAPTER.md) — measures AI quality, distinct from
  testing.
- [Platform Capability Model](../PLATFORM_CAPABILITY_MODEL.md) — the canonical model this
  capability belongs to.
- [Glossary](../21-glossary/CHAPTER.md) — canonical terms used in this chapter.

## Summary

Testing verifies that the platform's software is correct. A testing strategy composes unit,
integration, and end-to-end testing as a pyramid, with contract testing at boundaries, and
applies them as runtime, platform, and agent testing — all sustained by regression testing,
test automation, and test quality. Testing verifies software correctness; evaluation
measures AI quality, and the two are kept distinct. The next chapter,
[Chapter 19 — DevOps](../19-devops/CHAPTER.md), defines how the platform is built, delivered,
and operated.
