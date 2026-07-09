# Architecture & Design Philosophy

This document explains *why* the Skill Agents framework is designed the way it is. It covers the core principles, the trade-offs made, and the reasoning behind the SDLC phase ordering.

---

## Why This Exists

AI coding agents are powerful but undirected. Give an agent a vague prompt and it will produce *something* — but rarely the right thing. The core insight behind this framework (borrowed from [gstack](https://github.com/wahIndra/gstack.git)) is:

> **An AI agent performs dramatically better when given a specific role, a strict methodology, and clear constraints.**

Instead of one generic agent, we create 23 specialized personas — each with a narrow job, explicit rules, and a defined output format. The result is an agent that behaves like a full engineering organization rather than a single intern.

---

## The Three Pillars

### Pillar 1: The 6 Decision Principles

The biggest failure mode of AI agents is indecision. When faced with an ambiguous choice, they either ask the user (wasting time) or guess randomly (wasting code).

The 6 Decision Principles eliminate this by providing a deterministic tiebreaker for every common decision type:

- **Scope decisions** → Choose completeness (P1)
- **Cleanup decisions** → Boil lakes (P2)
- **Implementation decisions** → Pragmatic (P3) + Explicit over clever (P5)
- **Duplication decisions** → DRY (P4)
- **Velocity decisions** → Bias toward action (P6)

These principles are wired directly into the `/autoplan` skill, which uses them to auto-answer every intermediate question during the CEO → Design → Eng → DX review pipeline.

### Pillar 2: The Persistent Persona Protocol

Without persistence, users must re-invoke the skill on every single message. This is exhausting and defeats the purpose of deep persona embodiment.

The Persistent Persona Protocol solves this by making persona activation **sticky**. Once the user types `/qa`, the agent remains in QA mode for the entire conversation. It only switches when explicitly told to.

This allows the user to have a natural, multi-turn conversation with a QA engineer without constant context switching.

### Pillar 3: The Prompt Diet

AI agents have a finite context window. Complex workflows (like `/e2e`) can easily exhaust it, causing the agent to "forget" earlier steps and produce broken output.

The Prompt Diet is a set of hard constraints that prevent this:

1. **Artifacts over Chat:** Large outputs (test matrices, audit reports) are written to files, not the chat window. This keeps the conversation context lean.
2. **Surgical Edits:** Instead of rewriting entire files (which flood the context with old + new content), the agent uses targeted replacement tools.
3. **No Regurgitation:** The agent never re-summarizes information the user can already see.

The Prompt Diet is enforced **globally** — it runs automatically on every skill, every prompt, without the user needing to invoke it.

---

## Why This Phase Ordering?

The SDLC phases are ordered to match the natural lifecycle of a feature, with each phase building on the output of the previous one:

```
A: Planning    →  Define WHAT to build and WHY
B: Auditing    →  Challenge HOW it's built while building
C: Review      →  Final safety check before release
D: Operational →  Learn from what was shipped
E: Documentation → Ensure humans can use what was built
F: Advanced QA →  Deep platform-specific testing
G: Context     →  Persist state across sessions
```

### Why Planning comes before Implementation
Without a plan, the agent writes code that solves the wrong problem. The `/autoplan` pipeline forces the agent to get challenged on strategy (CEO), design (UX), architecture (Eng), and developer experience (DX) before a single line of code is written.

### Why The Gauntlet exists
Code that isn't adversarially tested is dangerous. The Gauntlet (QA + CSO + Review) exists to simulate the three things that break production:
1. **Edge cases the developer didn't think of** (QA)
2. **Security vulnerabilities the developer didn't know about** (CSO)
3. **Blast radius the developer didn't predict** (Review)

### Why Documentation is automated
Documentation rots faster than code. By injecting `/document-release` directly into the `/e2e` pipeline (Step 5), we ensure that docs are updated *at the same time* as the code, not as an afterthought three weeks later.

### Why Context Management matters
AI agents have no persistent memory between conversations. The `/context-save` and `/context-restore` skills simulate long-term memory by serializing the agent's active persona, open files, and decisions to a file that can be loaded in a future session.

---

## The Self-Improving Loop

The most powerful aspect of this framework is the feedback loop between `/skillify` and the rest of the system:

1. You complete a complex, custom workflow with the agent.
2. You run `/skillify`.
3. The agent analyzes what it just did and writes a brand new skill.
4. That skill is now permanently available for future use.

Over time, your `.agents` library grows organically — shaped by your actual workflows, not by a framework author's assumptions. The agent literally teaches itself new capabilities based on your successful patterns.

---

## Trade-offs & Limitations

| Trade-off | Rationale |
|-----------|-----------|
| **Many small skills vs. one monolithic agent** | Small, focused skills produce higher-quality output because the agent has clearer instructions. The cost is more files to maintain. |
| **Strict phase ordering vs. flexibility** | Ordering prevents the agent from skipping critical steps (like security audits). The cost is that simple tasks go through unnecessary ceremony when run via `/e2e`. |
| **Global Prompt Diet vs. verbose output** | Token efficiency prevents context exhaustion on long sessions. The cost is that the agent may feel terse for users who prefer detailed explanations. |
| **Antigravity-specific vs. IDE-agnostic** | Currently optimized for Antigravity's tool API (`browser_subagent`, `run_command`, etc.). Porting to other IDEs would require adapting tool references. |
