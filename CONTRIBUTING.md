# Contributing to APEF

Thank you for helping build the Agent Platform Engineering Framework. APEF is an
engineering framework: contributions are specifications, architecture, handbook
prose, templates, playbooks, and reference research — not application code.

## Ground rules

1. **No application code.** APEF does not contain APIs, frontend, or backend
   implementations. Contributions that add running software will be declined.
2. **Specification-Driven Development.** Propose and agree on a specification or ADR
   before large changes. See [`bootstrap/WORKFLOW.md`](bootstrap/WORKFLOW.md).
3. **No empty placeholders.** Do not commit `TODO`, `TBD`, or `Coming Soon`. Every
   document must be useful on the day it merges.
4. **Respect directory contracts.** Each directory's `README.md` states what belongs
   there and what must never be placed there. Honor it.

## How to contribute

1. Open an issue or discussion describing the change and its motivation.
2. For decisions with long-term impact, add an ADR using
   [`templates/adr/`](templates/adr/) and place the accepted record in [`adrs/`](adrs/).
3. Create a topic branch, make focused and logically grouped commits, and open a
   pull request.
4. Ensure your change passes the checks in [`bootstrap/QUALITY_GATES.md`](bootstrap/QUALITY_GATES.md).

## Style

- Write in clear, direct English. Prefer short sentences and concrete language.
- Use relative Markdown links between documents so navigation stays intact.
- Match the tone and structure of neighboring documents.

## Code of conduct

Participation is governed by [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md).
