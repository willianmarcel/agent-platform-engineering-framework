# Templates — Canonical Document Templates

## Overview
This directory provides the canonical, reusable templates that keep APEF artifacts consistent. The specification template is the base template; specialized templates extend it.

## Purpose
To reduce variance so artifacts are comparable and reviewable, and to serve as the source generators may scaffold from.

## Responsibilities
- Define the required structure and sections for each artifact type.
- Maintain the base-and-extension relationship among templates.

## Contents
- [adr](adr/)
- [specification](specification/) — the base template.
- [epic](epic/)
- [feature](feature/)
- [story](story/)
- [task](task/)
- [runtime](runtime/)
- [plugin](plugin/)
- [provider](provider/)
- [evaluation](evaluation/)
- [api](api/)
- [architecture](architecture/)

## Out of Scope
- Filled-in, real artifacts — those belong in their destination directories.
- Application, API, frontend, or backend code.

## Relationships
- [Specifications](../specifications/) — where completed specifications live.
- [Examples](../examples/) — worked examples, as opposed to blank templates.

## References
- [Master Plan](../bootstrap/MASTER_PLAN.md) — the constitution governing the framework
- [Architecture Decisions](../bootstrap/ARCHITECTURE_DECISIONS.md) — the ratified Foundation decision record

## Conventions
- The specification template is the base; the runtime, plugin, provider, api, and other specialized templates extend it. The full inheritance is documented in a later phase.
- A template is a blank form with guidance, not an example.
