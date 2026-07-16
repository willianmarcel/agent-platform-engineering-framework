# .claude — AI-Assisted Engineering Configuration

## Overview
This directory configures how AI assistants participate in engineering work on APEF, so that AI-assisted contributions are consistent, reviewable, and aligned with the framework's standards.

## Purpose
To make AI assistance a governed, transparent, and versioned part of the engineering process.

## Responsibilities
- Encode repeatable, framework-aware AI commands, personas, skills, hooks, and workflows.
- Keep AI configuration versioned alongside the content it operates on.

## Contents
- [commands](commands/) — reusable command definitions (documented only in Foundation).
- [personas](personas/) — AI collaborator roles (documented only in Foundation).
- [skills](skills/) — packaged, task-specific skill definitions.
- [hooks](hooks/) — automation triggered around AI or tool events.
- [workflows](workflows/) — multi-step orchestrations combining the above.

## Out of Scope
- Application, API, frontend, or backend code.
- Secrets, credentials, or API keys.
- Content that belongs in the handbook, specifications, or architecture.

## Relationships
- [Playbooks](../playbooks/) — human procedures that AI workflows may assist.
- [Scripts](../scripts/) — maintenance automation hooks may invoke.

## References
- [Master Plan](../bootstrap/MASTER_PLAN.md) — the constitution governing the framework
- [Architecture Decisions](../bootstrap/ARCHITECTURE_DECISIONS.md) — the ratified Foundation decision record

## Conventions
- During Foundation this directory defines only the responsibility of each subdirectory; no personas and no commands are authored yet.
