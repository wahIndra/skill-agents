# Skill Agents for Antigravity

> A portable `.agents` skill library that transforms **Google Antigravity** into a full-stack software development organization — from PM to QA to Release Engineering — powered by a single AI agent.

This project is heavily inspired by the incredible work done on [gstack](https://github.com/wahIndra/gstack.git). We have adapted its rigorous, multi-phase adversarial review architecture specifically for Antigravity. Currently built for Antigravity; we may expand to other IDEs and AI providers later.

---

## Table of Contents

- [Setup](#setup)
- [Quick Start](#quick-start)
- [How It Works](#how-it-works)
- [Available Skills (23 Total)](#available-skills)
- [SDLC Phases](#sdlc-phases)
- [Core Rules](#core-rules)
- [Advanced Usage](#advanced-usage)

---

## Setup

This repository is designed to be included as a **Git Submodule** in any project's `.agents` directory.

```bash
# In the root of your project:
git submodule add https://github.com/wahIndra/skill-agents.git .agents
```

Antigravity will automatically detect the `.agents` folder and load all skills. No configuration required.

**Cloning a project that already uses this library:**
```bash
git clone --recurse-submodules <your-project-url>
# Or, if already cloned:
git submodule update --init --recursive
```

---

## Quick Start

Once the `.agents` folder is in your project, chat with the Antigravity agent and use slash commands to trigger specialized personas.

### The "Magic Button" — Build a Feature End-to-End
```text
/e2e build a login page with email validation
```
The agent will plan, build, test, audit security, update docs, and push to Git — fully autonomously.

### Review Your Code Before Merging
```text
/review check my recent changes for race conditions
```

### Scope an Idea Down to MVP
```text
/office-hours I want to build a social network for dogs
```

### Design an Architecture Without Writing Code
```text
/autoplan create an architecture for a real-time chat app
```

### Run a Full QA Audit (Whitebox + Blackbox + Regression)
```text
/qa test the checkout flow for edge cases
```

### Security Audit (OWASP Top 10)
```text
/cso audit the authentication system
```

### Debug a Stubborn Bug
```text
/investigate why is the API returning 500 on the /users endpoint
```

### Save Your Work and Resume Later
```text
/context-save
```
Then tomorrow:
```text
/context-restore
```

> **Pro Tip:** You only need to type the slash command **once**. The agent remembers your active persona and applies it to every subsequent message until you type a new command or `/clear`.

---

## How It Works

The framework is built on three pillars:

### 1. The 6 Decision Principles
Every skill auto-decides intermediate questions using these rules:
1. **Choose completeness** — Ship the whole thing
2. **Boil lakes** — Fix everything in the blast radius
3. **Pragmatic** — Pick the cleaner option in 5 seconds
4. **DRY** — Reuse what exists
5. **Explicit over clever** — 10-line fix > 200-line abstraction
6. **Bias toward action** — Merge > review cycles > stale deliberation

### 2. The Persistent Persona Protocol
When you invoke a skill (e.g., `/qa`), the agent locks into that persona for the rest of the conversation. You don't need to retype the command. It stays active until you trigger a different skill or type `/clear`.

### 3. The Prompt Diet (Always Active)
Token efficiency is enforced globally. The agent:
- Writes large outputs to artifacts, not chat
- Uses surgical code edits instead of full-file rewrites
- Never re-summarizes context you can already see

---

## Available Skills

### 🎯 The Master Orchestrator
| Command | Description |
|---------|-------------|
| `/e2e` | End-to-End Delivery. Plans, builds, tests, audits, documents, and ships a feature autonomously. |

### 📋 Planning & Strategy
| Command | Description |
|---------|-------------|
| `/autoplan` | Runs CEO → Design → Eng → DX reviews sequentially with auto-decisions. |
| `/office-hours` | YC-style PM brainstorm. Challenges premises, finds 10x impact, cuts scope to MVP. |
| `/plan-ceo-review` | Strategy & Scope gatekeeper. Challenges premises and evaluates alternatives. |
| `/plan-design-review` | UX/UI specialist. Evaluates information hierarchy and shadow states. |
| `/plan-eng-review` | Architecture reviewer. Locks data flow, edge cases, and failure modes. |
| `/plan-devex-review` | DX auditor. Evaluates Time-to-Hello-World and API ergonomics. |

### 🔨 Implementation & Auditing
| Command | Description |
|---------|-------------|
| `/investigate` | Root-cause debugging. No fixes without tracing the structural root cause. |
| `/deep-critique` | Multi-persona L8+ Principal Engineer critique (Design, Security, Perf, Maintainability). |
| `/cso` | Adversarial OWASP security audit (7 categories). Requires visual evidence. |
| `/browser` | Headless browser automation for E2E UI flow testing. |

### 🧪 Quality Assurance
| Command | Description |
|---------|-------------|
| `/qa` | **Omni-QA/QC.** Tests any platform (Web, API, CLI) using Whitebox, Greybox, Blackbox, Functional, Regression, and A/B testing. Requires immutable evidence. |
| `/mobile-qa` | Mobile viewport simulation. Tests responsive layouts and touch targets (Apple HIG). |
| `/canary` | Post-deploy monitoring. Continuously polls live URLs to detect silent production crashes. |

### 🚀 Review & Release
| Command | Description |
|---------|-------------|
| `/review` | Pre-landing PR review. Catches race conditions, blast radius, rollback safety, dependency and perf regressions. |
| `/ship` | Release engineer. Runs tests, cleans up, commits with conventional messages, and pushes. |

### 📖 Documentation & Knowledge
| Command | Description |
|---------|-------------|
| `/document-release` | Syncs README and architecture docs with newly shipped code. |
| `/document-generate` | Generates full Diátaxis documentation (Tutorials, How-Tos, Reference, Explanation). |

### 🧠 Operational & Memory
| Command | Description |
|---------|-------------|
| `/skillify` | The Self-Replicator. Codifies a successful workflow into a new permanent skill. |
| `/retro` | Weekly retrospective. Analyzes git history for velocity, bugs caught, and team health. |
| `/context-save` | Saves current persona, open files, and decisions to an artifact. |
| `/context-restore` | Restores a previously saved working state. |

### ⚡ Utilities
| Command | Description |
|---------|-------------|
| `/prompt-diet` | Token optimization auditor. Aggressively compresses context window usage. |

---

## SDLC Phases

The `/e2e` orchestrator runs these phases in order:

```
Step 1: Git Target Verification
     ↓
Step 2: Strategy & Plan (PM Phase)
     ↓  /office-hours → /autoplan
Step 3: Implementation
     ↓  Write code based on approved MVP
Step 4: The Gauntlet (Challenge Phase)
     ↓  /qa → /cso → /review
Step 5: Documentation
     ↓  /document-release
Step 6: Ship It
     ↓  git commit & push
Step 7: Context Snapshot (Optional)
        /context-save
```

You can also trigger any phase independently by using its slash command directly.

---

## Core Rules

These rules are enforced globally via `AGENTS.md` and apply to every skill:

| Rule | Effect |
|------|--------|
| **6 Decision Principles** | Auto-decides intermediate questions using completeness, DRY, pragmatism. |
| **Prompt Diet (Always Active)** | Forces artifacts over chat, surgical edits, and zero filler text. |
| **Persistent Persona** | Skills stay active until a new one is triggered or `/clear` is typed. |
| **Immutable Evidence** | QA and CSO skills MUST capture screenshots or logs for every finding. |

---

## Advanced Usage

### Teach the Agent New Skills
After completing a complex, custom workflow:
```text
/skillify
```
The agent will analyze what it just did and write a brand new `.agents/skills/<name>/SKILL.md` file, permanently giving itself a new capability.

### Run a Weekly Retro
```text
/retro
```
The agent reads your git log and generates a sprint retrospective with shipping velocity metrics.

### Post-Deploy Monitoring
```text
/canary https://your-app.com
```
The agent will continuously poll your live site and alert you if it detects a crash.

### Generate Full Documentation
```text
/document-generate
```
Produces Diátaxis-style docs (Tutorials, How-Tos, Reference, Explanation) from your codebase.

---

## 📚 Full Documentation

For deeper documentation organized by the Diátaxis framework:

| Type | Document | Purpose |
|------|----------|---------|
| 🎓 Tutorial | [Getting Started](docs/tutorials/getting-started.md) | Step-by-step guide from zero to first `/e2e` delivery |
| 🔧 How-To | [Use Each Skill](docs/how-to/use-each-skill.md) | Practical recipes for all 23 skills |
| 📖 Reference | [Skills Reference](docs/reference/skills.md) | Technical spec of every skill's inputs and outputs |
| 📖 Reference | [AGENTS.md Reference](docs/reference/agents-md.md) | Every global rule and its effect |
| 💡 Explanation | [Architecture](docs/explanation/architecture.md) | Why the framework is designed this way |

---

## License

MIT

---

*Built with ❤️ for the Google Antigravity IDE. Inspired by [gstack](https://github.com/wahIndra/gstack.git).*
