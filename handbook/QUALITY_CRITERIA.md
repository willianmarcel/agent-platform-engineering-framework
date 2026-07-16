# Engineering Handbook — Quality Criteria

This document defines the **Definition of Done** for a handbook chapter: the measurable
quality gates every chapter must pass before it is accepted. A chapter is "done" only
when it passes **all** gates. The gates are objective so they can be checked by a
reviewer and, where possible, automated.

## Definition of Done

A chapter is done when every gate below is satisfied.

### 1. Structural conformance
- The chapter uses the twelve mandatory sections of the canonical template from the
  [Writing Guide](WRITING_GUIDE.md), in order, with none removed or renamed. The only
  permitted additional section is the optional *Security Considerations* section, which —
  when present — appears immediately after *Best Practices*.
- **Measure:** 12/12 mandatory sections present and correctly ordered; no non-permitted
  sections added.

### 2. Contract conformance
- The chapter matches its entry in the [Table of Contents](TABLE_OF_CONTENTS.md):
  objective, scope, prerequisites, and expected outputs.
- **Measure:** 0 discrepancies between the chapter and its Table-of-Contents contract.

### 3. Architectural consistency
- The chapter is consistent with [`06-reference-architecture`](06-reference-architecture/)
  and does not contradict any accepted decision in [`../adrs/`](../adrs/) or
  [`../bootstrap/ARCHITECTURE_DECISIONS.md`](../bootstrap/ARCHITECTURE_DECISIONS.md).
- The chapter upholds the ratified boundaries: security **principles** stay in
  [`15-security`](15-security/) (a *Security Considerations* section carries implications
  only), and AI **Evaluation** ([`16-evaluation`](16-evaluation/)) stays distinct from
  software **Testing** ([`18-testing`](18-testing/)).
- **Measure:** 0 unresolved architectural contradictions raised in review.

### 4. No duplicated concepts
- Every concept the chapter uses but does not own is linked to its owning chapter per the
  [Knowledge Graph](KNOWLEDGE_GRAPH.md); the chapter defines only the concepts it owns.
- **Measure:** 0 concepts redefined outside their owning chapter.

### 5. Dependency integrity
- The chapter's declared prerequisites are acyclic and already written and approved; any
  forward reference is a non-binding related link.
- **Measure:** prerequisite graph remains acyclic; 0 references to unwritten prerequisites.

### 6. References validated
- Every reference is a relative Markdown link and resolves; every external link is
  reachable.
- **Measure:** 100% of internal links resolve; 0 broken references.

### 7. Terminology compliant
- The chapter uses only canonical terms and no forbidden synonyms, following the
  [Glossary Guidelines](GLOSSARY_GUIDELINES.md); specialized terms link to
  [`21-glossary`](21-glossary/) on first use.
- **Measure:** 0 forbidden synonyms; all first-use specialized terms linked.

### 8. Examples reviewed
- Every example is non-executable and consistent with the [`../templates/`](../templates/)
  and [`../examples/`](../examples/) policy; no production or runnable application code.
- **Measure:** 0 executable-code examples; all examples reviewed and approved.

### 9. Completeness and no placeholders
- The chapter fully covers its declared scope and contains no `TODO`, `TBD`, or
  `Coming Soon`.
- **Measure:** 0 prohibited placeholders; scope fully addressed.

### 10. Review and approval
- The chapter has passed peer review and the applicable
  [`../playbooks/architecture-review/`](../playbooks/architecture-review/) checks, and is
  approved.
- **Measure:** required approvals recorded.

## Chapter Acceptance Checklist

- [ ] Twelve template sections present and ordered (Gate 1)
- [ ] Matches its Table-of-Contents contract (Gate 2)
- [ ] Consistent with the Reference Architecture and accepted decisions (Gate 3)
- [ ] No concept redefined outside its owner (Gate 4)
- [ ] Prerequisites acyclic, written, and approved (Gate 5)
- [ ] All references resolve (Gate 6)
- [ ] Terminology compliant; terms linked to the glossary (Gate 7)
- [ ] Examples non-executable and reviewed (Gate 8)
- [ ] Scope complete; no placeholders (Gate 9)
- [ ] Reviewed and approved (Gate 10)

## Relationship to Other Standards

- Chapter structure: [Writing Guide](WRITING_GUIDE.md).
- Chapter contracts: [Table of Contents](TABLE_OF_CONTENTS.md).
- Dependencies and ownership: [Knowledge Graph](KNOWLEDGE_GRAPH.md).
- Terminology: [Glossary Guidelines](GLOSSARY_GUIDELINES.md).
- Repository quality gates: [`../bootstrap/QUALITY_GATES.md`](../bootstrap/QUALITY_GATES.md).
