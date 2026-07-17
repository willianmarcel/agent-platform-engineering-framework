# Milestone — Reference Studies — Summary

Milestone record produced by the Architecture Team under the
[Architecture Charter](../governance/ARCHITECTURE_CHARTER.md) and
[Operating Model](../governance/ARCHITECTURE_OPERATING_MODEL.md). This milestone completes the
Reference Studies portion of **Roadmap Phase 4 — Reference & Examples**.

## Summary

The Architecture Team autonomously planned and executed the Reference Studies milestone: ten
analytical studies of external agent frameworks and platforms, each drawing architectural
lessons for the APEF, plus a navigation index and a takeaways-by-capability matrix.

- **Delivered:** `STUDY.md` in each of the ten reference directories
  ([LangGraph](langgraph/STUDY.md), [Agno](agno/STUDY.md),
  [OpenAI Agents SDK](openai-agents-sdk/STUDY.md), [Google ADK](google-adk/STUDY.md),
  [CrewAI](crewai/STUDY.md), [AutoGen](autogen/STUDY.md),
  [Azure AI Foundry](azure-ai-foundry/STUDY.md), [Copilot Studio](copilot-studio/STUDY.md),
  [Dify](dify/STUDY.md), [Flowise](flowise/STUDY.md)); the
  [Reference Index](REFERENCE_INDEX.md); and this milestone record with its
  [Compliance Report](REFERENCE_STUDIES_COMPLIANCE.md).
- **Structure per study:** overview, why the APEF studies it, model summary, strengths,
  trade-offs, takeaways mapped to the owning Handbook chapter, relationships, conventions.
- **Discipline:** analysis only — no endorsement, no recommendation, no implementation guidance,
  no source code, no marketing. External technologies are named only because analyzing them is
  the purpose of the reference area; the APEF itself remains neutral.

## Statistics

- 10 studies; 1 index; 2 milestone records.
- Takeaways map to 11 Handbook chapters/capabilities (07, 08, 09, 10, 11, 12, 14, 15, 16, 17, 19).
- 124 internal reference links; all resolve. No frozen artifact modified.

## Architecture Review

Validated against the Charter's quality gates:

- **Handbook consistency:** ✅ Every takeaway maps to the chapter that owns the concern and never
  contradicts it.
- **Concept Ownership:** ✅ The studies own no Handbook concepts; they reference owning chapters
  and the Platform Capability Model without redefining anything.
- **Traceability:** ✅ Each study links to its takeaway chapters, the Reference Index, and the PCM;
  the index provides a bidirectional study↔capability matrix.
- **Architectural consistency:** ✅ Consistent altitude (architectural analysis, not
  implementation); no code, no API detail, no version specifics.
- **Technology / vendor / framework neutrality:** ✅ The APEF's own guidance remains neutral;
  external names appear only as the analyzed subjects, with no prescription to adopt them
  (verified: zero "APEF should use/adopt" language).

No mandatory-escalation condition was triggered by this milestone; it lies entirely within the
Team's autonomous authority ("expand reference material").

## Outstanding Decisions (for the Architecture Board)

These are pre-existing items accumulated across prior work that require Board decision. They are
**not** introduced by this milestone; the Team surfaces them per the
[Escalation Policy](../governance/ARCHITECTURE_ESCALATION.md). Each affects Concept Ownership,
Governance, or Handbook chapters and is therefore a Board decision.

### OD-1 — Creator Experience ownership (Chapter 08 vs Chapter 17)
- **Problem:** Chapter 08 (frozen) owns *Creator Experience*; Sprint 04 also listed it under
  Chapter 17. Chapter 17 references it without redefining.
- **Alternatives:** (a) Keep ownership in Chapter 08, Chapter 17 references it; (b) move ownership
  to Chapter 17 via a superseding decision.
- **Recommendation:** (a). **Rationale:** Chapter 08 is frozen and its definition is sound;
  single ownership is preserved. **Impact:** documentation only. **Affected:** Chapters 08, 17.
- **Proposed decision:** Ratify Chapter 08 as the owner; Chapter 17 references it.

### OD-2 — Chapter 17 title (UI/UX vs User Experience)
- **Problem:** The frozen Table of Contents lists Chapter 17 as "UI/UX"; the chapter is titled
  "User Experience".
- **Alternatives:** (a) Confirm "User Experience" as canonical; (b) revert to "UI/UX".
- **Recommendation:** (a). **Rationale:** the chapter owns *User Experience*. **Impact:** a title
  discrepancy note. **Affected:** Chapter 17, Table of Contents. **Proposed decision:** confirm.

### OD-3 — Standing conventions to formalize as ADRs (adrs/ is empty)
- **Problem:** Two ratified-in-practice conventions are not recorded as ADRs: the README
  navigation `Reading`-section exception to AD-0001, and the `CHAPTER.md` chapter-content
  convention.
- **Recommendation:** Author accepted ADRs for both in [`../adrs/`](../adrs/). **Rationale:**
  make standing conventions auditable. **Impact:** additive ADRs. **Affected:** adrs/, AD-0001.
  **Proposed decision:** authorize the Team to draft the ADRs for Board ratification.

### OD-4 — Single home for the mandated architectural principles
- **Problem:** The cross-plane architectural principles are restated per chapter rather than
  owned once. **Recommendation:** define a single authoritative home (a Chapter 03 addendum or an
  ADR). **Impact:** editorial + one decision. **Affected:** Chapters 03–19. **Proposed decision:**
  Board to choose the home.

### OD-5 — Module-README entry points (specifications/ and reference/)
- **Problem:** Directory READMEs are frozen; the Team used new entry documents
  (`SPECIFICATION_FRAMEWORK.md`, `SPECIFICATION_LIBRARY_INDEX.md`, `REFERENCE_INDEX.md`,
  `*_SPECIFICATIONS.md`, `STUDY.md`) instead of modifying them. **Recommendation:** accept these
  entry documents as canonical; do not modify frozen READMEs. **Impact:** navigation only.
  **Proposed decision:** ratify the entry-document pattern.

### OD-6 — Uncommitted body of approved work
- **Problem:** A large body of approved-but-uncommitted work has accumulated (Handbook RC
  Chapters 18–21 + handbook artifacts + completion records; the Execution Framework in `execution/`;
  the full Specification Library; and this Reference Studies milestone). **Recommendation:**
  authorize commits as clean, separate logical commits per milestone. **Impact:** version-control
  hygiene; no content change. **Proposed decision:** grant commit authorization.

## Next Milestone Proposal

**Milestone: Worked Examples (Roadmap Phase 4, second half).** Populate the [`../examples/`](../examples/)
area with worked, **non-executable** examples (per AD-0014) for agents, workflows, providers,
plugins, supervisors, and evaluations — artifacts and models only, technology-neutral,
demonstrating the Handbook and Specification Framework in use. This is within the Team's
autonomous authority ("create additional examples") and triggers no mandatory escalation. The
Team proposes to proceed with it next, subject to Board acknowledgement of this milestone.
