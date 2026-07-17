# execution/workflows — Multi-Step Orchestrations

## Overview
This directory defines workflows that orchestrate multiple steps — combining commands, personas, skills, and hooks — to accomplish larger engineering tasks.

## Purpose
To compose smaller building blocks into repeatable, higher-level processes.

## Responsibilities
- Describe ordered steps and the components each workflow invokes.
- Mirror the human procedures in the playbooks where AI assists them.

## Contents
- Workflow definitions describing ordered steps and the components they invoke.

## Out of Scope
- Standalone commands, personas, or skills — each has its own directory.
- Secrets, credentials, or API keys.
- Application, API, frontend, or backend code.

## Relationships
- [Playbooks](../../playbooks/) — the human procedures workflows may assist.
- [Commands](../commands/) — building blocks workflows compose.

## References
- [Master Plan](../../bootstrap/MASTER_PLAN.md) — the constitution governing the framework
- [Architecture Decisions](../../bootstrap/ARCHITECTURE_DECISIONS.md) — the ratified Foundation decision record

## Conventions
- Workflows compose existing building blocks and do not duplicate their definitions.
