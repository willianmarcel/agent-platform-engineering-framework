# Scripts — Repository-Maintenance Utilities

## Overview
This directory holds automation that maintains the framework repository itself: validation, generation, linting, and consistency checks. These utilities operate on the framework and are never platform implementation.

## Purpose
To keep the repository healthy and consistent through reproducible maintenance tooling.

## Responsibilities
- Automate quality gates such as link checking, structure validation, and placeholder detection.
- Generate scaffolding from the templates.

## Contents
- Utility scripts that lint, validate, or generate framework content, and their configuration.

## Out of Scope
- Application, API, frontend, or backend code for an AI Agent Platform.
- Business logic unrelated to maintaining this repository.
- Secrets, credentials, or API keys.

## Relationships
- [Templates](../templates/) — the source scaffolding generators may use.
- [Quality Gates](../bootstrap/QUALITY_GATES.md) — the gates scripts help enforce.

## References
- [Master Plan](../bootstrap/MASTER_PLAN.md) — the constitution governing the framework
- [Architecture Decisions](../bootstrap/ARCHITECTURE_DECISIONS.md) — the ratified Foundation decision record

## Conventions
- Scripts are repository-maintenance utilities only — never platform implementation. They should be idempotent and documented at the top of the file.
