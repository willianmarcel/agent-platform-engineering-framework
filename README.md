# Agent Platform Engineering Framework (APEF)

## Overview
APEF is an engineering framework for designing and building enterprise-grade AI Agent Platforms. It is not itself a platform, an SDK, or a running system; it is the body of principles, specifications, architecture, playbooks, templates, and reference research that guides the construction of such platforms.

## Purpose
To provide a durable engineering foundation — comparable to the Spring Framework, .NET Aspire, Backstage, the Kubernetes documentation, or the AWS Well-Architected Framework — that keeps platform-engineering decisions coherent over years.

## Responsibilities
- Anchor the repository and orient readers to its structure and methodology.
- Point to the governing plan, the ratified decisions, and the entry points for reading and contributing.

## Contents
- [bootstrap](bootstrap/) — governing plan, roadmap, and engineering process for the framework itself.
- [handbook](handbook/) — the narrative engineering handbook, organized as numbered chapters.
- [specifications](specifications/) — Specification-Driven Development artifacts.
- [architecture](architecture/) — C4, event-storming, deployment, runtime, and other diagram sources.
- [playbooks](playbooks/) — repeatable review and readiness procedures.
- [templates](templates/) — canonical templates for framework artifacts.
- [examples](examples/) — worked, non-executable reference examples.
- [reference](reference/) — study notes on external agent frameworks and platforms.
- [adrs](adrs/) — accepted Architecture Decision Records.
- [docs](docs/) — documentation derived from the handbook.
- [assets](assets/) — shared binary and design assets.
- [scripts](scripts/) — repository-maintenance utilities.
- [execution](execution/) — the Execution Framework: commands, roles, workflows, review, and quality gates.

## Out of Scope
- Application, API, frontend, or backend code.
- Any AI Agent Platform implementation — APEF describes how to build one, it is not one.

## Relationships
- [Master Plan](bootstrap/MASTER_PLAN.md) — the constitution the repository obeys.
- [Architecture Decisions](bootstrap/ARCHITECTURE_DECISIONS.md) — the ratified Foundation decisions.
- [Roadmap](ROADMAP.md) — navigation to the authoritative roadmap.
- [Contributing](CONTRIBUTING.md) — how to contribute.

## References
- [Getting Started](GETTING_STARTED.md) — the practical on-ramp for new readers.
- [Introduction chapter](handbook/00-introduction/) — the narrative starting point.
- [License](LICENSE) — Apache License 2.0.

## Conventions
- The framework is built with Specification-Driven Development; during the Foundation phase the repository contains structure and documentation only.
- Every README follows the eight-section contract, and every cross-reference is a relative link.
