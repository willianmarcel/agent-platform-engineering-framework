# Quality Gates

## Purpose
This document defines the quality gates every contribution must pass before it is
accepted. Gates make quality objective and repeatable rather than a matter of opinion.

## Contents
- The mandatory checks for any change (for example: no `TODO`/`TBD`/`Coming Soon`
  placeholders; every directory has a useful README; internal links resolve).
- Structure-validation rules that keep the repository consistent with the master plan.
- Documentation-quality criteria (clarity, completeness, correct placement).
- The mapping between gates and the automation in [`../scripts/`](../scripts/) and the
  hooks in [`../.claude/hooks/`](../.claude/hooks/) that enforce them.
- The relationship between gates and the review [`../playbooks/`](../playbooks/).

## Relationships
Gates enforce the standards in [`ENGINEERING_GUIDE.md`](ENGINEERING_GUIDE.md) and are a
precondition of the [`RELEASE_PROCESS.md`](RELEASE_PROCESS.md). [`WORKFLOW.md`](WORKFLOW.md)
describes when each gate is applied.

## Current state
Purpose-defined during Foundation. The concrete gate definitions and their automation
are authored in the Engineering phase.
