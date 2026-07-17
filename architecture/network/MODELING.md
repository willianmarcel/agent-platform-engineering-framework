# Network Modeling

The methodology for modeling the platform's **network architecture** — its trust boundaries,
segmentation, and connectivity. Entry document for [`network/`](README.md) (frozen README remains the
contract).

## Overview
Network modeling describes how the platform is segmented into zones of trust, how traffic enters and
leaves, and how services find and reach one another. The trust, identity, and isolation concepts it
depicts are owned by [15 — Security](../../handbook/15-security/CHAPTER.md); the structural placement
is owned by [06 — Reference Architecture](../../handbook/06-reference-architecture/CHAPTER.md). This
module owns the modeling method and stays strictly technology-neutral.

## Purpose
To make the network's trust boundaries and traffic paths explicit and reviewable, so segmentation and
exposure are deliberate and defensible.

## Scope
**In scope:** modeling trust boundaries, segmentation, connectivity, name resolution (DNS), service
discovery, ingress, egress, and private networking. **Out of scope:** defining security concepts
(Ch 15) and the deployment topology ([`deployment/`](../deployment/MODELING.md)).

## Principles
Segment by trust; default-deny connectivity; make every ingress and egress explicit; keep internal
traffic private by default; model roles and zones, never products.

## Modeling Process
1. **Zones** — model the trust zones and what distinguishes them.
2. **Boundaries** — draw the trust boundaries between zones and what may cross each.
3. **Connectivity** — model the allowed paths between zones (default-deny; allow by exception).
4. **Ingress/Egress** — model how external traffic enters and how the platform reaches outward.
5. **Resolution & discovery** — model name resolution (DNS) and service discovery within and across
   zones.
6. **Private networking** — model which paths stay private and how.

## Guidelines & Notation
- Draw trust boundaries first; connectivity follows from them.
- Express rules as allow-by-exception over a default-deny baseline.
- Author as diagram-as-code (zone/segmentation diagrams with annotated boundaries and paths). Use
  generic terms (zone, boundary, gateway, resolver) — never a specific product, appliance, or
  provider.

## Views & Artifacts
- **Trust-zone model** — zones and their trust levels.
- **Segmentation & connectivity map** — boundaries and allowed paths.
- **Ingress/egress model** — external entry and exit points.
- **Resolution & discovery model** — DNS and service discovery.

## Patterns & Anti-patterns
**Patterns:** default-deny segmentation; minimal, explicit ingress; controlled egress; private
internal paths; identity-aware boundaries. **Anti-patterns:** a flat network with implicit trust;
undocumented egress; exposing internal services directly; conflating network segmentation with
deployment topology; naming a specific networking product.

## Review Checklist & Quality Criteria
- [ ] Every zone has a stated trust level and boundary.
- [ ] Connectivity is default-deny with explicit exceptions.
- [ ] All ingress and egress points are modeled and justified.
- [ ] Name resolution and service discovery are modeled.
- [ ] Trust-boundary concepts reference [Security (Ch 15)](../../handbook/15-security/CHAPTER.md).
- [ ] The model names no technology, product, or provider.

## Cross-Module Integration
- **Upstream:** [`deployment/`](../deployment/MODELING.md) (the topology the network overlays),
  [`security` specifications](../../specifications/security/) (trust/segmentation requirements).
- **Downstream:** [`integrations/`](../integrations/MODELING.md) (the paths integrations traverse).
- **Related:** [`c4/`](../c4/MODELING.md) (Deployment/Container context).
- **Shared concepts (owned elsewhere):** trust boundaries, identity, isolation (Ch 15); structure
  (Ch 06). This module defines none of them.

## Traceability & References
- **Handbook:** [15 — Security](../../handbook/15-security/CHAPTER.md),
  [06 — Reference Architecture](../../handbook/06-reference-architecture/CHAPTER.md).
- **Specifications:** [`security`](../../specifications/security/),
  [`architecture-requirements`](../../specifications/architecture-requirements/).
- **ADRs:** network decisions are recorded via the [ADR framework](../../adrs/ADR_FRAMEWORK.md);
  reviewed by the [security-review playbook](../../playbooks/security-review/PROCEDURE.md).
- **Worked Examples:** network model instances are ready-structure for Phase 5.
