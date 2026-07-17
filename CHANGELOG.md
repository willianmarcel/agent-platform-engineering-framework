# Changelog

All notable changes to the Agent Platform Engineering Framework (APEF) are
documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).
Because APEF is a documentation and engineering framework, "changes" refer to
additions, revisions, and removals of specifications, architecture, handbook
chapters, templates, and playbooks rather than software behavior.

## [Foundation v1.0.0] - 2026-07-16

The Foundation phase, accepted and frozen by the Architecture Board. The repository
structure, governance model, and repository conventions are now immutable.

### Added
- Foundation repository structure: complete directory tree (95 directories) with a
  README in every directory following the ratified eight-section contract.
- Root governance files: README, LICENSE (Apache-2.0), CONTRIBUTING, CODE_OF_CONDUCT,
  SECURITY, ROADMAP, and this CHANGELOG.
- Bootstrap governance documents: MASTER_PLAN, ARCHITECTURE_DECISIONS (ratified),
  ROADMAP (authoritative), ENGINEERING_GUIDE, REPOSITORY_GUIDE, QUALITY_GATES,
  RELEASE_PROCESS, WORKFLOW, and FOUNDATION_COMPLETE.
- `execution/` structure for AI-assisted engineering (commands, personas, skills,
  hooks, workflows) — directories documented, no personas or commands authored yet.
- Handbook (chapters 00–21), specifications, architecture, playbooks, templates,
  examples, and reference scaffolding — each with a responsibility-defining README.
- Repository `.gitignore`.

### Changed
- Renamed `specifications/architecture/` to `specifications/architecture-requirements/`
  (AD-0007).
- Roadmap ownership consolidated: `bootstrap/ROADMAP.md` is authoritative and the root
  `ROADMAP.md` is a navigation document (AD-0005).
- Every README rewritten to the ordered eight-section contract; all cross-references
  converted to relative Markdown links (AD-0001, AD-0002, AD-0003).

### Removed
- Generic `architecture/diagrams/` catch-all directory; every artifact now belongs to a
  defined category (AD-0008).

[Foundation v1.0.0]: https://github.com/willianmarcel/agent-platform-engineering-framework/releases/tag/foundation-v1.0.0
