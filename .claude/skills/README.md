# .claude/skills — Packaged Skill Definitions

## Overview
This directory holds packaged, task-specific skills that extend an AI collaborator's capabilities within APEF, such as diagram validation or specification linting.

## Purpose
To encapsulate reusable, discoverable skills the framework relies on.

## Responsibilities
- Keep each skill self-documenting and scoped to a single job done well.
- Organize one skill per subdirectory with its supporting files.

## Contents
- Skill definitions and their supporting files, organized one skill per subdirectory.

## Out of Scope
- [Personas.](../personas/)
- [Command definitions.](../commands/)
- Secrets, credentials, or API keys.
- Application, API, frontend, or backend code.

## Relationships
- [Workflows](../workflows/) — may invoke skills as steps.

## References
- [Master Plan](../../bootstrap/MASTER_PLAN.md) — the constitution governing the framework
- [Architecture Decisions](../../bootstrap/ARCHITECTURE_DECISIONS.md) — the ratified Foundation decision record

## Conventions
- Each skill is self-contained and scoped to one task.
