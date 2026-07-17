# execution — Execution Framework

## Overview
This directory is the Execution Framework: the engineering operating system that defines how engineering work is carried out on APEF — its commands, roles, workflows, review framework, and quality gates — so that work is consistent, reviewable, and aligned with the framework's standards. See [`EXECUTION_FRAMEWORK.md`](EXECUTION_FRAMEWORK.md) for the authoritative entry document.

## Purpose
To make engineering execution repeatable, governed, transparent, and versioned.

## Responsibilities
- Encode repeatable, framework-aware commands, roles (skills), workflows, reviews, and gates.
- Keep the execution model versioned alongside the content it operates on.

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
