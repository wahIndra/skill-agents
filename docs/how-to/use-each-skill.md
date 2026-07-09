# How to Use Each Skill

Practical, goal-oriented recipes for every skill in the library. Find what you want to do, copy the command, and go.

---

## Planning & Strategy

### How to scope an idea down to MVP
```text
/office-hours I want to build a marketplace for freelancers
```
The agent will challenge your premises, find the 10x impact, and cut scope to the smallest possible version that delivers 80% of the value.

### How to get a full architecture review
```text
/autoplan design the backend for a real-time notification system
```
Runs four sequential reviews (CEO → Design → Eng → DX) and produces a Consensus Table with findings.

### How to challenge strategic premises
```text
/plan-ceo-review should we build our own auth system or use a third-party provider?
```

### How to audit the UX/UI design
```text
/plan-design-review review the user onboarding flow for missing states
```

### How to check for architectural flaws
```text
/plan-eng-review review the database schema for N+1 queries and edge cases
```

### How to evaluate developer experience
```text
/plan-devex-review how easy is it for a new developer to set up and run this project?
```

---

## Implementation & Debugging

### How to debug a stubborn bug
```text
/investigate the payment webhook is silently failing
```
The agent will reproduce the issue, trace the root cause (not just the symptom), and propose a fix.

### How to get a deep architectural critique
```text
/deep-critique review the caching layer for performance and security
```
A panel of L8+ Principal Engineers critiques your code from four angles: Design, Security, Performance, and Maintainability.

---

## Quality Assurance

### How to run a full QA audit
```text
/qa test the user registration flow
```
The agent picks the right methodologies (Whitebox, Blackbox, Regression, etc.) based on the platform and generates an Omni-QA Test Matrix with immutable evidence.

### How to test mobile responsiveness
```text
/mobile-qa test the dashboard on iPhone 14 Pro dimensions
```
The agent resizes the browser to mobile dimensions and checks touch targets, overflow, and navigation.

### How to run a security audit
```text
/cso audit the API endpoints for OWASP vulnerabilities
```
Covers 7 OWASP categories (Access Control, Injection, Crypto, Insecure Design, Misconfiguration, Vulnerable Dependencies, SSRF). Requires visual evidence.

### How to automate browser testing
```text
/browser test the checkout flow from cart to confirmation
```
Uses the headless `browser_subagent` to physically click through the UI and capture video evidence.

---

## Review & Release

### How to get a pre-merge code review
```text
/review check my recent changes before I merge
```
Catches race conditions, blast radius issues, rollback safety, dependency risks, and test coverage gaps.

### How to ship code safely
```text
/ship push the current changes to the main branch
```
Runs tests, removes debug logs, commits with a conventional message, and pushes.

---

## Documentation

### How to sync docs with code changes
```text
/document-release update the README to match the new API endpoints
```

### How to generate full documentation from scratch
```text
/document-generate create docs for the authentication module
```
Produces Diátaxis-style documentation: Tutorials, How-To Guides, Reference, and Explanation.

---

## Operational & Memory

### How to teach the agent a new skill
```text
/skillify
```
After completing a complex, custom workflow, the agent analyzes what it just did and writes a brand new `.agents/skills/<name>/SKILL.md` file.

### How to run a weekly retrospective
```text
/retro
```
Analyzes your git history and generates a sprint retrospective with shipping velocity, bugs caught, and areas for improvement.

### How to save and restore your work
```text
/context-save
```
Saves the current persona, open files, and decisions. Resume later with:
```text
/context-restore
```

---

## Post-Deploy Monitoring

### How to monitor a live deployment
```text
/canary https://your-app.com
```
Continuously polls the URL and alerts you if it detects a crash (HTTP 500, blank screen, JS errors).

---

## Utilities

### How to reduce token usage
```text
/prompt-diet
```
Aggressively compresses the agent's context window. Forces artifacts over chat, surgical edits, and zero filler text. **Note:** This runs automatically on every skill — you rarely need to invoke it manually.
