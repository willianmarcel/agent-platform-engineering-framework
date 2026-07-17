# execution/hooks — Event Automation

## Overview
This directory defines hooks: automation that runs around AI or tool events to enforce APEF's standards automatically rather than relying on memory.

## Purpose
To bind quality gates to the moments where they matter.

## Responsibilities
- Automate guardrails such as placeholder detection, link checking, or formatting.
- Reference the scripts they invoke rather than duplicating logic.

## Contents
- Hook configuration and the scripts they invoke or reference.

## Out of Scope
- Secrets, credentials, or API keys.
- Business logic for an AI Agent Platform.
- Application, API, frontend, or backend code.

## Relationships
- [Scripts](../../scripts/) — the maintenance utilities hooks invoke.
- [Quality Gates](../../bootstrap/QUALITY_GATES.md) — the gates hooks enforce.

## References
- [Master Plan](../../bootstrap/MASTER_PLAN.md) — the constitution governing the framework
- [Architecture Decisions](../../bootstrap/ARCHITECTURE_DECISIONS.md) — the ratified Foundation decision record

## Conventions
- Hooks should be fast, deterministic, and safe to run repeatedly.
