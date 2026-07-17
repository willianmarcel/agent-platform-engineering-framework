# Memory & Conversational State

> **Proposed chapter (P1 — Agentic Core).** Authored to Handbook standard; not yet integrated into
> the frozen Handbook numbering or Knowledge Graph. Owns the agent-memory concepts defined below;
> references other chapters for concepts they own — **persistence and retrieval** are owned by the
> Data Platform and **runtime state** by the Runtime Platform, and are referenced, not redefined,
> here.

## 1. Introduction

A model call is, in itself, stateless: it knows only what its context contains. Yet users expect an
agent to remember — to carry forward what was said, learn a preference, and not re-ask what it was
already told. That continuity is not a property of the model; it is an engineered capability. **Agent
memory** is what the platform chooses to carry across turns and sessions, and how it selects the right
remembered information back into context at the right moment.

Memory is easy to get superficially right and hard to get durably right. Remember too little and the
agent is forgetful; remember too much, or the wrong things, and context bloats, cost rises, stale
facts mislead, and private information leaks across boundaries it should not cross. **Memory
engineering** is the discipline of deciding what an agent remembers, at what scope, for how long, and
how remembered information is retrieved back into context — treating memory as a governed store, not
an ever-growing transcript. This chapter defines that discipline on top of the persistence and
retrieval the platform already owns.

## 2. Objectives

- Distinguish **working memory** from **long-term memory** and define each.
- Define **memory scope** (session, user, cross-session) and its boundaries.
- Establish **write** and **retention** policies — what is remembered and what is forgotten.
- Connect memory to **retrieval** and to **context assembly** without duplicating them.
- Preserve privacy and isolation of remembered information.

## 3. Concepts

This chapter **owns** the following concepts.

**Agent memory.** The information a platform carries across model calls on an agent's behalf and
selects back into context when relevant — distinct from the model's stateless call and from raw
persistence.

**Working memory.** The short-lived, in-task memory of the current interaction: the recent turns and
intermediate results the agent needs now, held within or just beyond the active context and bounded
to fit it.

**Long-term memory.** The durable memory that outlives a single interaction: facts, preferences,
summaries, and outcomes retained for future sessions and retrieved when relevant.

**Memory scope.** The boundary that governs who a memory belongs to and where it may be used —
per-**session**, per-**user**, or a shared scope — determining isolation.

**Memory write policy.** The rule governing what is committed to long-term memory, when, and in what
form (raw, summarized, or structured) — memory is curated, not everything that happens.

**Retention and forgetting.** The rule governing how long a memory persists and when it is expired,
corrected, or removed — including honoring a request to be forgotten.

**Memory retrieval into context.** The selection of relevant memories back into the assembled context
for a call, under the context budget — the bridge from memory to behavior.

Concepts referenced but **owned elsewhere**: **persistence, retrieval, and data governance** (Data
Platform); **runtime execution, state, and lifecycle** (Runtime Platform); **context assembly and the
context budget** (Context & Prompt Engineering); **identity, isolation, and privacy** (Security);
**evaluation** of whether memory improves outcomes (Evaluation).

## 4. Principles

1. **Memory is curated, not accumulated.** What the agent remembers is a deliberate write, not the
   entire transcript retained by default.
2. **Scope is a boundary, not a convenience.** Every memory has a scope, and memory never crosses a
   scope boundary it was not granted (a session memory does not leak into another user's context).
3. **Working and long-term memory are distinct.** Short-lived task memory and durable memory have
   different stores, budgets, and lifecycles.
4. **Retrieval serves the budget.** Memory enters context by relevance-ranked retrieval within the
   context budget, not by dumping history.
5. **Forgetting is a feature.** Retention is bounded; stale or corrected memory is expired, and a
   request to be forgotten is honored.
6. **Memory earns its place.** Remembered information is justified by improved outcomes, measured, not
   assumed.

## 5. Architecture

Memory is a governed capability layered on the Data Platform's persistence and retrieval, feeding the
context assembler:

- **Working store** — the bounded, short-lived memory of the current task, compacted (summarized or
  windowed) to fit the context budget.
- **Long-term store** — the durable memory, scoped per session/user/shared, holding curated facts,
  preferences, and summaries via the Data Platform's persistence.
- **Write policy** — the component deciding what, when, and in what form to commit to long-term
  memory, and enforcing scope on write.
- **Retrieval** — relevance-ranked selection of memories for the current call, delegated to the Data
  Platform's retrieval and bounded by the context budget.
- **Retention control** — the enforcement of expiry, correction, and removal, including
  right-to-be-forgotten.

The stores rely on the Data Platform for persistence and retrieval and on Security for isolation and
privacy; memory retrieved for a call is handed to the Context assembler, which places it within the
budget. This chapter adds the memory model — scope, write, retention, and the working/long-term split
— on top; it prescribes no storage or retrieval technology.

## 6. Patterns

- **Working/long-term split.** Keep short-lived task memory separate from durable memory, with
  different budgets and lifecycles.
- **Summarize-to-persist.** Commit distilled summaries or structured facts to long-term memory rather
  than raw transcripts.
- **Scoped retrieval.** Retrieve only memories within the caller's scope, ranked by relevance, and
  bound to the context budget.
- **History compaction.** Compress working memory (summarize older turns) to preserve continuity
  within the window.
- **Correction over accumulation.** Update or supersede a stored fact when it changes, rather than
  layering a contradiction beside it.
- **Expiry by policy.** Attach a retention rule to each memory class and enforce expiry automatically.

## 7. Anti-patterns

- **Transcript-as-memory.** Retaining and replaying the entire conversation, overflowing the window
  and raising cost with every turn.
- **Scope leakage.** Retrieving one user's or session's memory into another's context — a correctness
  and privacy failure.
- **Unbounded growth.** Long-term memory that only accumulates, never expires or corrects, so stale
  and contradictory facts mislead the agent.
- **Retrieve-everything.** Injecting all stored memory rather than a relevance-ranked, budgeted
  selection.
- **Silent staleness.** Trusting old memory as current when it has changed, with no correction path.
- **Unforgettable data.** No mechanism to expire or remove memory on request or by policy.

## 8. Best Practices

- Separate working and long-term memory with distinct stores, budgets, and lifecycles.
- Curate long-term memory: write summaries or structured facts, not raw transcripts.
- Attach a scope to every memory and enforce it on both write and retrieval.
- Retrieve by relevance within the context budget; never dump memory into context.
- Attach retention rules; expire, correct, and honor removal requests.
- Measure whether remembered information improves outcomes, via evaluation.

## 9. Examples

*Illustrative and technology-neutral; no runnable code.*

- **A returning user.** Across sessions, the agent recalls a stated preference (held in per-user
  long-term memory) and applies it, while the details of a prior unrelated session stay out of the
  current context because they are out of relevant scope.
- **A long conversation.** As turns accumulate, working memory is compacted — older turns summarized —
  so continuity is preserved without overflowing the context window.
- **A correction.** The user updates a fact the agent had stored; the write policy supersedes the old
  value rather than keeping both, and later retrieval returns only the current fact.
- **A removal request.** On request, the retention control expires the user's remembered information,
  and subsequent retrieval finds nothing to surface.

## 10. Checklist

- [ ] Working memory and long-term memory are distinct, with their own budgets and lifecycles.
- [ ] Every memory has a scope, enforced on write and on retrieval.
- [ ] Long-term memory is curated (summaries/structured facts), not raw transcripts.
- [ ] Memory enters context by relevance-ranked retrieval within the context budget.
- [ ] Retention rules expire, correct, and remove memory; removal requests are honored.
- [ ] No memory crosses a scope boundary it was not granted.
- [ ] Memory's contribution to outcomes is evaluated, not assumed.

## 11. References

- Data Platform — persistence, retrieval, and data governance that memory is built on.
- Runtime Platform — runtime execution, state, and lifecycle.
- Context & Prompt Engineering — the assembly and budget that memory retrieval feeds.
- Security — identity, isolation, and privacy that bound memory scope.
- Evaluation — the measure of whether memory improves outcomes.

## 12. Summary

Continuity is engineered, not inherent: agent memory is what the platform deliberately carries across
turns and sessions and selects back into context when relevant. It is curated rather than
accumulated, split into working and long-term stores, bounded by scope, governed by write and
retention policies, and retrieved within the context budget — layered on the Data Platform's
persistence and retrieval rather than reinventing them. Memory engineered this way makes an agent feel
attentive and stay private and current; memory left as an ever-growing transcript makes it expensive,
leaky, and misled. Forgetting, done deliberately, is as much a feature as remembering.
