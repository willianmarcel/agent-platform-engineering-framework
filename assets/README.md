# Assets — Shared Binary and Design Assets

## Overview
This directory stores binary and design assets referenced across the framework: logos, icons, exported diagram renders, illustrations, and other media that documents link to.

## Purpose
To give shared media a single, predictable home and keep content directories readable.

## Responsibilities
- Provide one home for shared media.
- Keep large or binary files out of content directories.

## Contents
- Images (.png, .svg, .jpg), exported diagram renders, and brand or design assets.
- Fonts or media explicitly licensed for use in the framework.

## Out of Scope
- [Editable diagram sources — those live in the architecture directory.](../architecture/)
- Documentation prose or specifications.
- Secrets, credentials, or API keys.

## Relationships
- [Architecture](../architecture/) — the source of diagrams whose renders are stored here.

## References
- [Master Plan](../bootstrap/MASTER_PLAN.md) — the constitution governing the framework
- [Architecture Decisions](../bootstrap/ARCHITECTURE_DECISIONS.md) — the ratified Foundation decision record

## Conventions
- Prefer vector formats (SVG) for diagrams and icons; reference assets with relative links from the documents that use them.
