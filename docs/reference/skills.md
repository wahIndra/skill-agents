# Skills Reference

Technical reference for every skill in the library. Each entry documents the skill's frontmatter, internal sections, and expected output format.

---

## Master Orchestrator

### `/e2e`
| Property | Value |
|----------|-------|
| **File** | `.agents/skills/e2e/SKILL.md` |
| **Description** | End-to-End Feature Delivery Orchestrator |
| **Sections** | Git Target Verification → Strategy & Plan → Implementation → The Gauntlet → Documentation → Ship It → Context Snapshot |
| **Output** | "End-to-End Delivery Log" |
| **Dependencies** | `/office-hours`, `/autoplan`, `/qa`, `/cso`, `/review`, `/document-release`, `/context-save` |

---

## Planning & Strategy

### `/autoplan`
| Property | Value |
|----------|-------|
| **File** | `.agents/skills/autoplan/SKILL.md` |
| **Description** | Auto-review pipeline with sequential CEO → Design → Eng → DX reviews |
| **Sections** | 6 Decision Principles → CEO Review → Design Review → Eng Review → DX Review |
| **Output** | Consensus Table |
| **Dependencies** | `/plan-ceo-review`, `/plan-design-review`, `/plan-eng-review`, `/plan-devex-review` |

### `/office-hours`
| Property | Value |
|----------|-------|
| **File** | `.agents/skills/office-hours/SKILL.md` |
| **Description** | YC-style PM brainstorm and MVP scoping |
| **Sections** | MVP Scalpel → Reframing the Problem → Product Market Fit |
| **Output** | "PM Scope Document" |

### `/plan-ceo-review`
| Property | Value |
|----------|-------|
| **File** | `.agents/skills/plan-ceo-review/SKILL.md` |
| **Description** | Strategy and Scope gatekeeper |
| **Sections** | Premise Evaluation → Alternatives & Regret → Scope Definition |
| **Output** | "NOT in scope" section with deferred items |

### `/plan-design-review`
| Property | Value |
|----------|-------|
| **File** | `.agents/skills/plan-design-review/SKILL.md` |
| **Description** | UX/UI and Product Design specialist |
| **Sections** | Information Hierarchy → Missing States → User Journey → Accessibility |
| **Output** | UX/UI state map |

### `/plan-eng-review`
| Property | Value |
|----------|-------|
| **File** | `.agents/skills/plan-eng-review/SKILL.md` |
| **Description** | Architecture and edge case reviewer |
| **Sections** | Architecture & Coupling → Edge Cases → Test Coverage → Security & Performance |
| **Output** | "Failure Modes Registry" |

### `/plan-devex-review`
| Property | Value |
|----------|-------|
| **File** | `.agents/skills/plan-devex-review/SKILL.md` |
| **Description** | Developer Experience auditor |
| **Sections** | Time to Hello World → Error Messages → API/CLI Ergonomics → Documentation |
| **Output** | "DX Scorecard" |

---

## Implementation & Auditing

### `/investigate`
| Property | Value |
|----------|-------|
| **File** | `.agents/skills/investigate/SKILL.md` |
| **Description** | Systematic root-cause debugging |
| **Sections** | Reproduce → Root Cause Analysis → Formulate Fix |
| **Output** | "Investigation Log" (Symptom, Root Cause, Proposed Fix) |

### `/deep-critique`
| Property | Value |
|----------|-------|
| **File** | `.agents/skills/deep-critique/SKILL.md` |
| **Description** | Multi-persona L8+ Principal Engineer critique |
| **Sections** | System Design → Security & Compliance → Performance & Scale → Maintainability → Actionable Refactoring |
| **Output** | "Deep Critique Report" |

### `/cso`
| Property | Value |
|----------|-------|
| **File** | `.agents/skills/cso/SKILL.md` |
| **Description** | Adversarial OWASP security audit |
| **Sections** | Auth Boundaries (A01) → Injection (A03) → Crypto (A02) → Data Leaks (A04) → Misconfiguration (A05) → Rate Limiting (A07) → Dependencies (A06) |
| **Output** | "OWASP Security Audit Report" |
| **Evidence** | Required (screenshots or log snippets) |

### `/browser`
| Property | Value |
|----------|-------|
| **File** | `.agents/skills/browser/SKILL.md` |
| **Description** | Headless browser automation and visual verification |
| **Sections** | Browser Subagent Usage → Visual Evidence → E2E Flow Testing |
| **Output** | "E2E Automation Report" |

---

## Quality Assurance

### `/qa`
| Property | Value |
|----------|-------|
| **File** | `.agents/skills/qa/SKILL.md` |
| **Description** | Omni-QA/QC Engineer (platform agnostic) |
| **Methodologies** | Whitebox, Greybox, Blackbox, Functional, Regression, A/B Testing |
| **Platforms** | Web (browser_subagent), API (curl), CLI (bash) |
| **Output** | "Omni-QA Test Matrix" |
| **Evidence** | Required (screenshots or terminal logs) |

### `/mobile-qa`
| Property | Value |
|----------|-------|
| **File** | `.agents/skills/mobile-qa/SKILL.md` |
| **Description** | Mobile viewport and responsive layout tester |
| **Sections** | Viewport Simulation → Mobile-Specific Auditing |
| **Output** | "Mobile QA Audit" |

### `/canary`
| Property | Value |
|----------|-------|
| **File** | `.agents/skills/canary/SKILL.md` |
| **Description** | Post-deploy live environment monitor |
| **Sections** | Post-Deploy Verification → Continuous Monitoring Loop |
| **Output** | "Canary Health Check Report" or "Sev-1 Incident Report" |

---

## Review & Release

### `/review`
| Property | Value |
|----------|-------|
| **File** | `.agents/skills/review/SKILL.md` |
| **Description** | Pre-landing PR code review |
| **Sections** | Logic & Race Conditions → Blast Radius → Rollback Safety → Dependency Audit → Test Coverage |
| **Output** | "Pre-Landing Code Review" (Blockers / Warnings / Nits) |

### `/ship`
| Property | Value |
|----------|-------|
| **File** | `.agents/skills/ship/SKILL.md` |
| **Description** | Release engineer for safe deployments |
| **Sections** | Verification → Clean Up → Shipping |
| **Output** | "Release Status Report" |

---

## Documentation & Knowledge

### `/document-release`
| Property | Value |
|----------|-------|
| **File** | `.agents/skills/document-release/SKILL.md` |
| **Description** | Syncs docs with newly shipped code |
| **Sections** | Context Gathering → Documentation Update → Strict Synchronization |
| **Output** | "Documentation Sync Report" |

### `/document-generate`
| Property | Value |
|----------|-------|
| **File** | `.agents/skills/document-generate/SKILL.md` |
| **Description** | Generates Diátaxis documentation from code |
| **Framework** | Tutorials, How-To Guides, Reference, Explanation |
| **Output** | "Diátaxis Generation Log" |

---

## Operational & Memory

### `/skillify`
| Property | Value |
|----------|-------|
| **File** | `.agents/skills/skillify/SKILL.md` |
| **Description** | Self-replicating skill generator |
| **Sections** | Workflow Analysis → Generate SKILL.md → Self-Registration |
| **Output** | "Skillify Generation Report" |

### `/retro`
| Property | Value |
|----------|-------|
| **File** | `.agents/skills/retro/SKILL.md` |
| **Description** | Weekly sprint retrospective |
| **Sections** | Data Gathering (git log) → Velocity & Health Metrics → Formatting |
| **Output** | `weekly_retro.md` artifact |

### `/context-save`
| Property | Value |
|----------|-------|
| **File** | `.agents/skills/context-save/SKILL.md` |
| **Description** | Saves active persona and working state |
| **Output** | `saved_context_<timestamp>.md` artifact |

### `/context-restore`
| Property | Value |
|----------|-------|
| **File** | `.agents/skills/context-restore/SKILL.md` |
| **Description** | Restores a previously saved working state |
| **Output** | "Context Restored" message |

---

## Utilities

### `/prompt-diet`
| Property | Value |
|----------|-------|
| **File** | `.agents/skills/prompt-diet/SKILL.md` |
| **Description** | Token optimization auditor |
| **Sections** | Context Purge → Artifact Delegation → Communication Minification |
| **Output** | "Prompt Diet executed" |
| **Note** | Runs automatically on every skill via global `AGENTS.md` rules |
