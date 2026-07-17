# Example — Traceability (conceptual)

A conceptual example showing bidirectional traceability. It illustrates methodology only and
names no technology.

```mermaid
graph LR
  BO["Business objective:<br/>serve more requests consistently"] --> CAP["Capability:<br/>assisted request handling"]
  CAP --> SPEC["Functional Specification"]
  SPEC --> TEST["Testing Specification"]
  SPEC --> EVAL["Evaluation Specification"]
  TEST --> ACC["Acceptance"]
  EVAL --> ACC
  ACC -.traces back to.-> BO
```

Reading it forward answers "what realizes the objective?"; reading it backward answers "what
does this test serve?". Every link is navigable both ways.
