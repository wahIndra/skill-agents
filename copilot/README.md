# Skill Agents for VS Code Copilot

> The same powerful SDLC framework as the Antigravity version, ported to **VS Code GitHub Copilot** using `.prompt.md` files and `copilot-instructions.md`.

This project is heavily inspired by [gstack](https://github.com/wahIndra/gstack.git).

---

## Setup

Run this command in the **root** of your project to pull the Copilot-specific files:

```bash
git submodule add -b copilot https://github.com/wahIndra/skill-agents.git .github
```

VS Code Copilot will automatically detect:
- `.github/copilot-instructions.md` → Global rules (always active)
- `.github/prompts/*.prompt.md` → Slash commands (invoked via `/name`)

---

## Quick Start

Open VS Code Copilot Chat and type `/` to see all available prompts.

### Build a feature end-to-end
```text
/e2e build a login page with email validation
```

### Run a security audit
```text
/cso audit the authentication system
```

### Get a code review
```text
/review check my recent changes
```

### Full QA audit
```text
/qa test the checkout flow
```

---

## Available Prompts (23 Total)

| Command | Mode | Description |
|---------|------|-------------|
| `/e2e` | agent | End-to-End Delivery Orchestrator |
| `/autoplan` | agent | CEO → Design → Eng → DX review pipeline |
| `/office-hours` | ask | YC-style MVP scoping |
| `/qa` | agent | Omni-QA (Whitebox, Blackbox, Regression) |
| `/cso` | agent | OWASP security audit |
| `/browser` | agent | E2E UI automation via puppeteer/playwright |
| `/investigate` | agent | Root-cause debugging |
| `/review` | ask | Pre-landing code review |
| `/ship` | agent | Release engineer |
| `/deep-critique` | ask | L8+ Principal Engineer critique |
| `/plan-ceo-review` | ask | Strategy & scope gatekeeper |
| `/plan-design-review` | ask | UX/UI specialist |
| `/plan-eng-review` | ask | Architecture reviewer |
| `/plan-devex-review` | ask | DX auditor |
| `/prompt-diet` | ask | Token optimization |
| `/skillify` | agent | Self-replicating prompt generator |
| `/retro` | agent | Weekly git retrospective |
| `/document-release` | agent | Sync docs with code |
| `/document-generate` | agent | Diátaxis documentation generator |
| `/canary` | agent | Post-deploy monitoring |
| `/mobile-qa` | agent | Mobile viewport testing |
| `/context-save` | agent | Save working state |
| `/context-restore` | agent | Restore working state |

### Agent Modes
- **`agent`**: Copilot runs autonomously — reads files, proposes edits, runs terminal commands.
- **`ask`**: Copilot provides analysis and recommendations without making changes.

---

## Key Differences from Antigravity Version

| Feature | Antigravity | VS Code Copilot |
|---------|-------------|-----------------|
| Global rules | `.agents/AGENTS.md` | `.github/copilot-instructions.md` |
| Skill files | `.agents/skills/<name>/SKILL.md` | `.github/prompts/<name>.prompt.md` |
| Browser automation | Built-in `browser_subagent` | Terminal-based puppeteer/playwright |
| Agent mode | Always autonomous | Requires `agent: agent` in frontmatter |

---

*Built with ❤️ for VS Code GitHub Copilot. Inspired by [gstack](https://github.com/wahIndra/gstack.git).*
