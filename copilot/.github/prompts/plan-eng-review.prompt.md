---
name: plan-eng-review
description: "Architecture and edge case reviewer. Locks data flow and failure modes."
agent: ask
tools: [codebase]
---

Review this plan for architectural issues, missing edge cases, and hidden complexity.

## 1. Architecture & Coupling
- Is component structure sound? 200-line abstraction when 10-line fix would do?

## 2. Edge Cases & Failure Modes
- What breaks under 10x load? Nil/empty/error path? Mid-operation DB disconnect?

## 3. Test Coverage
- What's missing? What breaks at 2am Friday? Are we just happy-path testing?

## 4. Security & Performance
- New attack surface? N+1 queries? Caching aggressive enough?

Output a "Failure Modes Registry" tracking all failure scenarios and mitigations.
