# EC-3 — Outstanding Decisions

Decisions EC-3 surfaces for the Architecture Board, following the "surface, don't silently resolve"
discipline. EC-3 raises **OD-13**. Prior open items are recapped for continuity.

## New — raised by EC-3

### OD-13 — C4 view model vs AD-0010 directory scope
- **Situation:** The Board's EC-3 brief directs the `c4` module to "define the canonical architectural
  view model" **including Deployment and Dynamic Views**. Foundation **AD-0010** (immutable) scopes the
  `architecture/c4/` **directory** to only the four core C4 views (Context, Container, Component,
  Code), with Deployment in `deployment/` and Dynamic views in `sequences/` and `state-machines/`.
- **Reconciliation applied:** The [c4 view model](../../architecture/c4/MODELING.md) **defines** all six
  view *types* (so the canonical view model is complete, per the brief) but **locates** the Deployment
  and Dynamic view *artifacts* in their dedicated modules (per AD-0010), referencing them rather than
  holding them. This honors both the Board's brief and the immutable AD.
- **Ask:** Confirm this reconciliation. No change to AD-0010 is proposed and none is needed; if the
  Board instead wishes the Deployment/Dynamic view artifacts to live in `c4/`, that would require a
  superseding ADR to AD-0010 (per OD-8, authored as an `ADR-`).
- **Recommendation:** Confirm as reconciled; leave AD-0010 in force.

## Carried forward — prior open items

| OD | Status |
|----|--------|
| OD-4 | Deferred to Release 1.1 (single home for the mandated architectural principles). |
| OD-6 | In force — no commit performed in EC-3; lifted only by v1.0 publication authorization. |
| OD-10 | Confirmation of the EC-2-mandate interpretation still requested (from EC-2). |
| OD-11 | Chapter 17 title/TOC/directory reconciliation — still awaiting Board direction (from EC-2). |
| OD-12 | Authorize v1.0 publication — see the [Publication Readiness Impact](EC3_PUBLICATION_READINESS_IMPACT.md). |

## Summary

| OD | Disposition sought |
|----|--------------------|
| OD-13 | Confirm the c4 / AD-0010 reconciliation |
| OD-10, OD-11 | Still awaiting Board direction (carried from EC-2) |
| OD-12 | Authorize v1.0 publication (now with the architecture module complete) |
| OD-4, OD-6 | Remain as previously dispositioned |

No other outstanding decision arose in EC-3.
