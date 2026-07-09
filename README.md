# Skill Agents for Antigravity

This repository contains a collection of specialized `.agents` skills designed for the **Google Antigravity** IDE. These skills transform the AI agent into an end-to-end software development organization, capable of handling everything from Product Management to QA Testing and Release Engineering.

> **Note:** This project is heavily inspired by the incredible work done on [gstack](https://github.com/wahIndra/gstack.git). We have adapted its rigorous, multi-phase adversarial review architecture specifically for Antigravity. Currently, this library is built for Antigravity, but we may expand support for other IDEs and AI providers in the future.

## Available Personas

- `/e2e` - The Master Orchestrator (End-to-End Delivery)
- `/autoplan` - Core Auto-Review Pipeline (CEO, Design, Eng, DX)
- `/office-hours` - YC-style PM brainstorm and MVP scoping
- `/qa` - Systematic QA testing and visual bug hunting
- `/cso` - Adversarial security audit (OWASP)
- `/browser` - E2E UI automation via headless browser
- `/investigate` - Root-cause debugging specialist
- `/review` - Pre-landing PR and Code Review
- `/ship` - Release engineer for safe deployments
- `/plan-ceo-review` - Strategy and scope gatekeeper
- `/plan-design-review` - UX/UI and Product Design specialist
- `/plan-eng-review` - Architecture and Edge Case reviewer
- `/plan-devex-review` - Developer Experience (DX) auditor
- `/prompt-diet` - Token optimization and context manager
- `/skillify` - The Self-Replicator (Codify workflows into skills)
- `/retro` - Agile Scrum Master (Weekly git and artifact retrospectives)

## Setup (Include as a Library)

This repository is designed to be included as a library in any of your projects. The best way to use it is to add it as a **Git Submodule** to your target project's `.agents` directory.

Run this command in the root of your project:
```bash
git submodule add https://github.com/wahIndra/skill-agents.git .agents
```

This will link the skills directly into your workspace. Antigravity will automatically detect the `.agents` folder and empower your agent with these specialized personas.

## Quick Start Tutorial

Once the `.agents` folder is in your project, simply chat with the Antigravity agent and trigger the personas using their slash commands.

**1. The "Magic Button"**
To have the agent plan, build, review, and deploy a feature completely autonomously:
```text
/e2e build a login page with email validation
```

**2. The Safe Reviewer**
If you have written some code and want a strict Staff Engineer to review it before you commit:
```text
/review check my recent changes for race conditions
```

**3. The MVP Scoper**
If you have a massive idea and want a YC-style Product Manager to cut the scope down:
```text
/office-hours I want to build a social network for dogs
```

**4. The Auto-Planner**
If you want the agent to thoroughly design the architecture and challenge the premises without actually writing code yet:
```text
/autoplan create an architecture document for a real-time chat app
```
