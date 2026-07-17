# execution/commands — Reusable Command Definitions

## Overview
This directory defines reusable AI commands that encode common, framework-aware actions such as scaffolding an ADR or validating structure.

## Purpose
To make repeatable AI assistance explicit, named, and reviewable.

## Responsibilities
- Define named, parameterized commands that operate within APEF's conventions.
- Keep command behavior consistent across contributors and sessions.

## Contents
- Command definition files, one per command, once the Engineering phase authors them.

## Out of Scope
- [Personas.](../personas/)
- [Multi-step workflows.](../workflows/)
- Secrets, credentials, or API keys.
- Application, API, frontend, or backend code.

## Relationships
- [Workflows](../workflows/) — compose commands into larger processes.
- [Personas](../personas/) — the roles commands run under.

## References
- [Master Plan](../../bootstrap/MASTER_PLAN.md) — the constitution governing the framework
- [Architecture Decisions](../../bootstrap/ARCHITECTURE_DECISIONS.md) — the ratified Foundation decision record

## Conventions
- No commands are authored during Foundation; this README documents only the directory's responsibility.
