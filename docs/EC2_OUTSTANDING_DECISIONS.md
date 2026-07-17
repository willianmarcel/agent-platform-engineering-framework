# EC-2 — Outstanding Decisions

Decisions EC-2 surfaces for the Architecture Board, following the "surface, don't silently resolve"
discipline. Prior ODs are recapped for continuity; EC-2 raises OD-11 and OD-12 and requests
confirmation of OD-10.

## Confirmation requested

### OD-10 — interpretation of the established decision
- **Situation:** The Board's EC-2 authorization stated "OD-10 Established" without accompanying text.
- **Interpretation applied:** The Architecture Team read OD-10 as the Board's formal establishment of
  the EC-2 operational-completeness mandate itself. No scope beyond the four stated objectives was
  assumed on OD-10's behalf.
- **Ask:** Confirm this reading, or supply OD-10's intended content so any additional scope can be
  addressed in a subsequent milestone.

## New — raised by EC-2

### OD-11 — Chapter 17 title / TOC / directory reconciliation
- **Question:** [ADR-0003](../adrs/decisions/0003-chapter-17-titled-user-experience.md) formalizes
  the "User Experience" title (OD-2), but the chapter **directory** remains `handbook/17-ui-ux/` and
  the frozen **Table of Contents** still lists the original "UI/UX" label. These are frozen Handbook
  artifacts, which EC-2 was directed not to modify.
- **Ask:** Direct the governed correction — whether to (a) update the frozen TOC label and/or
  directory name under Board authorization, or (b) accept the residual label discrepancy as immaterial
  and let ADR-0003 stand as the authoritative title record.
- **Recommendation:** (b) accept ADR-0003 as authoritative for the title and leave the frozen
  structural path as-is (renaming a frozen directory is disruptive and low-value); optionally correct
  only the TOC label if the Board wishes, as a governed one-line change.

### OD-12 — Authorize APEF v1.0 publication
- **Question:** With EC-1 and EC-2 complete, the framework is **conceptually, methodologically, and
  operationally complete**. Publication was already assessed READY at
  [Publication Readiness](PUBLICATION_READINESS.md); EC-1/EC-2 strengthened it further.
- **Ask:** Authorize v1.0 publication — lift OD-6, commit the accumulated approved milestones as one
  logical commit each (per the [Version Control Policy](../governance/VERSION_CONTROL_POLICY.md)), and
  tag **APEF v1.0**.
- **Recommendation:** Approve, after the [Release Review procedure](../playbooks/release-review/PROCEDURE.md)
  is run over the full scope. The Architecture Team will act only on explicit Board authorization.

## Carried forward — prior ODs

| OD | Status after EC-2 |
|----|-------------------|
| OD-1, OD-2, OD-5 | **Formalized** as ADR-0002, ADR-0003, ADR-0004. |
| OD-3 | Discharged; remains the Documentation Conventions standard. |
| OD-4 | Deferred to Release 1.1 (single home for the mandated architectural principles); an ADR is authored when resolved. |
| OD-6 | **In force** — no commit performed in EC-2; lifted only by OD-12 approval. |
| OD-7 | **Ratified** and applied (adrs/ internal structure). |
| OD-8 | **Ratified** and applied (future `AD-` supersession authored as `ADR-`). |
| OD-9 | **Approved** and executed (migration). |

## Summary

| OD | Disposition sought |
|----|--------------------|
| OD-10 | Confirm interpretation (EC-2 mandate) |
| OD-11 | Direct the Chapter 17 title/TOC/directory reconciliation |
| OD-12 | Authorize v1.0 publication (lift OD-6, commit, tag) |
| OD-4 | Remains deferred to 1.1 |
| OD-6 | Remains in force until OD-12 |
