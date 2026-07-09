# AGENTS.md Reference

Technical reference for the global rules file that governs all skill behavior.

**File location:** `.agents/AGENTS.md`

---

## Section 1: The 6 Decision Principles

These principles are used by `/autoplan` and all review skills to auto-answer intermediate questions without user input.

| # | Principle | Rule |
|---|-----------|------|
| P1 | Choose completeness | Ship the whole thing. Pick the approach that covers more edge cases. |
| P2 | Boil lakes | Fix everything in the blast radius (files modified + direct importers). |
| P3 | Pragmatic | If two options fix the same thing, pick the cleaner one. 5 seconds choosing. |
| P4 | DRY | Duplicates existing functionality? Reject. Reuse what exists. |
| P5 | Explicit over clever | 10-line obvious fix > 200-line abstraction. |
| P6 | Bias toward action | Merge > review cycles > stale deliberation. Flag concerns but don't block. |

**Scope:** Referenced explicitly in `/autoplan`, `/plan-ceo-review`, `/plan-design-review`, `/plan-eng-review`, and `/plan-devex-review`.

---

## Section 2: Token Efficiency Protocol (Prompt Diet)

This protocol is **ALWAYS ACTIVE** — it applies to every skill and every prompt without needing to be invoked.

| Rule | Effect |
|------|--------|
| Artifacts over Chat | Large outputs (test matrices, audit reports) go to `.md` artifacts, not the chat window. |
| Terse Communication | No filler text. Only the final summary or Consensus Table. |
| Surgical Edits | Use `multi_replace_file_content` instead of rewriting entire files. |
| No Regurgitation | Never re-summarize a plan or repeat visible context. |

---

## Section 3: Persistent Persona Protocol

| Trigger | Behavior |
|---------|----------|
| User types a slash command (e.g., `/qa`) | Agent adopts that persona for the entire conversation. |
| User types a *different* slash command | Agent switches to the new persona. |
| User types `/clear` | Agent returns to default behavior. |

**Effect:** The user never needs to retype the slash command. The agent remembers.

---

## Section 4: SDLC Personas

Lists all available skills organized by phase:

| Phase | Skills |
|-------|--------|
| Master Orchestrator | `/e2e` |
| A: Planning & Strategy | `/autoplan`, `/office-hours` |
| B: Implementation & Auditing | `/investigate`, `/deep-critique`, `/cso`, `/browser` |
| C: Review & Release | `/review`, `/ship` |
| D: Operational & Memory | `/skillify`, `/retro` |
| E: Documentation & Knowledge | `/document-release`, `/document-generate` |
| F: Advanced Live QA & Mobile | `/qa`, `/canary`, `/mobile-qa` |
| G: State & Context Management | `/context-save`, `/context-restore` |

---

## Section 5: Output Format

At the end of any `/autoplan` or general coding response, the agent outputs a GStack Auto-Review Consensus Table:

```text
## 📋 GStack Auto-Review Consensus
| Phase | Focus | Status | Key Finding / Fix Applied |
|-------|-------|--------|---------------------------|
| CEO   | Scope | ✅ Pass | <finding or reason>       |
| Eng   | Arch  | ⚠️ Warn | <finding or fix>          |
```

Include Design/DX rows if applicable.
