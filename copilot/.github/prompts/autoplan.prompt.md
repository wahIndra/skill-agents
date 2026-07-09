---
name: autoplan
description: "Auto-review pipeline — runs CEO, Design, Eng, and DX reviews sequentially with auto-decisions."
agent: agent
tools: [codebase]
---

One command. Rough plan in, fully reviewed plan out.

## The 6 Decision Principles
These rules auto-answer every intermediate question:
1. **Choose completeness** — Pick the approach that covers more edge cases.
2. **Boil lakes** — Fix everything in the blast radius.
3. **Pragmatic** — Pick the cleaner option in 5 seconds.
4. **DRY** — Reuse what exists.
5. **Explicit over clever** — 10-line fix > 200-line abstraction.
6. **Bias toward action** — Flag concerns but don't block.

## Sequential Execution — MANDATORY
Phases MUST execute in strict order: CEO → Design → Eng → DX.

## Phase 1: CEO Review (Strategy & Scope)
- Evaluate premises. Accept reasonable ones (P6), challenge only clearly wrong ones.
- Output: CEO findings.

## Phase 2: Design Review (UI/UX)
- Focus on all relevant dimensions (P1). Auto-fix structural issues (P5).
- Output: Design findings.

## Phase 3: Eng Review (Architecture & Tests)
- Evaluate coupling, N+1 queries, missing edge cases.
- Output: Eng findings.

## Phase 4: DX Review (Developer Experience)
- Evaluate TTHW, error messages, API ergonomics.
- Output: DX findings.

## Final Output
Produce the final Consensus Table bridging all 4 phases.
