# Getting Started with Skill Agents

This tutorial walks you through setting up the Skill Agents library in your project and running your first end-to-end feature delivery. By the end, you will have a fully autonomous AI engineering team embedded in your IDE.

**Time required:** ~5 minutes

---

## Prerequisites

- [Google Antigravity IDE](https://developers.google.com/) installed
- Git installed on your machine
- A project repository (new or existing)

---

## Step 1: Add the Library to Your Project

Open a terminal in the root of your project and run:

```bash
git submodule add -b antigravity https://github.com/wahIndra/skill-agents.git .agents
```

This creates an `.agents` folder containing all 23 skills. Antigravity automatically detects this folder — no additional configuration is needed.

> **Already cloning a project that uses this library?**
> ```bash
> git clone --recurse-submodules <your-project-url>
> ```

---

## Step 2: Verify the Skills Are Loaded

Open Antigravity and start a new chat. Type any slash command to confirm the skills are active:

```text
/office-hours hello
```

The agent should respond as a YC-style Product Manager. If it does, the library is working.

---

## Step 3: Run Your First `/e2e` Delivery

Now let's use the "Magic Button" — the `/e2e` command. This triggers the full SDLC pipeline:

```text
/e2e build a contact form with email validation
```

Here is what happens automatically behind the scenes:

| Step | What Happens |
|------|-------------|
| **1. Git Target** | The agent asks you for your Git URL to push to. |
| **2. Strategy** | It scopes the feature down to a true MVP (`/office-hours` + `/autoplan`). |
| **3. Implementation** | It writes the code based on the approved plan. |
| **4. The Gauntlet** | It runs QA testing (`/qa`), security audit (`/cso`), and code review (`/review`). |
| **5. Documentation** | It updates your README and docs to match the new feature (`/document-release`). |
| **6. Ship** | It commits and pushes to your Git URL. |
| **7. Context Save** | It optionally saves your working state for later. |

You just shipped a fully tested, reviewed, and documented feature with one command.

---

## Step 4: Understand the Persistent Persona

You may have noticed: after typing `/e2e`, the agent stayed in that persona. This is the **Persistent Persona Protocol**.

- Once you trigger a skill, it stays active for the entire conversation.
- You do NOT need to retype the slash command.
- To switch personas, just type a new slash command (e.g., `/qa`).
- To reset to default, type `/clear`.

---

## Step 5: Save and Resume Your Work

If you need to take a break mid-session:

```text
/context-save
```

The agent saves its current persona, open files, and decisions to a file. When you come back:

```text
/context-restore
```

It picks up exactly where you left off.

---

## What's Next?

- **Explore individual skills:** See the [How-To Guide](how-to/use-each-skill.md) for recipes on every skill.
- **Understand the architecture:** Read the [Architecture Explanation](explanation/architecture.md) to learn *why* the framework works this way.
- **Check the reference:** See the [Skills Reference](reference/skills.md) for exact inputs and outputs of each skill.
