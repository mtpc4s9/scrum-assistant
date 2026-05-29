# Scrum Assistant - System Architecture & Directory Structure

This document outlines the file layout and directory organization of the `scrum-assistant` skill bundle. It serves as a physical map for developers and AI agents to locate reference materials, active sub-skills, and templates.

---

## 1. Physical Directory Tree

```text
scrum-assistant/
│
├── SKILL.md                        # Root Router (Entry point for Antigravity)
├── ARCHITECTURE.md                 # This file (System layout map)
├── README.md                       # Repository homepage (GitHub optimized)
├── .gitignore                      # Git tracking exemptions (hides private refs/)
│
├── reference/                      # [PACKAGED - GIT TRACKED] Tri thức domain (Domain knowledge)
│   ├── igaming-context.md          # iGaming & Lottery domain context & dictionary
│   └── jd-guidelines.md            # Standard JD context mapping
│
└── skills/                         # Active sub-skills & templates
    │
    ├── po-ba/                      # [BA/PO Accountabilities]
    │   ├── ba-user-story-craft/
    │   │   └── SKILL.md            # INVEST & BDD Gherkin story creation
    │   ├── ba-requirements-elicitation/
    │   │   └── SKILL.md            # Stakeholder mapping & elicitation workshops
    │   └── ba-impact-analysis/
    │       └── SKILL.md            # Change Request systems & compliance gating
    │
    ├── sm-ops/                     # [SM Operations & Metrics] (Upcoming)
    │   ├── sm-capacity-planning/
    │   │   └── SKILL.md            # Team capacity calculations & ranges
    │   ├── sm-velocity-review/
    │   │   └── SKILL.md            # Sprint predictability & velocity checks
    │   ├── sm-impediment-log/
    │   │   └── SKILL.md            # Blocker tracking & escalation logs
    │   └── sm-stakeholder-update/
    │       └── SKILL.md            # Stakeholder comms & sync drafts
    │
    ├── ceremonies/                 # [Sprint Events & Outputs] (Upcoming)
    │   ├── sprint-planning/
    │   │   └── SKILL.md            # Sprint goal & backlog commitments (Goal Canvas)
    │   ├── daily-sync/
    │   │   └── SKILL.md            # Daily Standup facilitation & blocker logs
    │   ├── refinement/
    │   │   └── SKILL.md            # Backlog refinement, grooming & estimation
    │   ├── sprint-review/
    │   │   └── SKILL.md            # Product demo, DoD gating & feedback loop
    │   └── retrospective/
    │       └── SKILL.md            # Sprint retro facilitation (4Ls/OODA formats)
    │
    └── templates/                  # Shared Document & Modeling templates
        ├── user-story-bdd.md       # Standard BDD story structure
        ├── sprint-goal-canvas.md   # Scrum Master planning canvas
        ├── game-rules-math-sheet.md # Lottery rules, prize tiers & RTP spec sheet
        └── third-party-integration-matrix.md # API connectivity matrix (Kambi, MoMo, Crypto)
```

---

## 2. Directory Layer Mapping

### 2.1 Root Level (`/`)
*   **SKILL.md:** Acts as the primary router. When the AI agent encounters a generic BA/SM request, this file directs the agent to load the precise sub-skill path using `view_file`.
*   **ARCHITECTURE.md:** Provides directory visibility, helping the agent comprehend where templates and supporting context files are located.

### 2.2 Private References (`/refs/`) vs Public Domain References (`/reference/`)
*   **`/refs/`:** Contains long-term, read-only internal developer notes. Git ignored to protect company privacy.
*   **`/reference/`:** Contains packaged domain context (`igaming-context.md`) to guide the AI agent during live daily work.

### 2.3 Active Sub-Skills (`/skills/`)
*   Functional units containing executable guidelines and specific templates. Grouped logically by:
    *   `po-ba/`: Day-to-day requirements, stories, and change scoping.
    *   `sm-ops/`: Metrics, capacity, blockers, and stakeholder comms.
    *   `ceremonies/`: Event-driven sprint rituals producing tangible output logs.

### 2.4 Shared Templates (`/skills/templates/`)
*   Ready-to-use Markdown templates. Sub-skills draw from this layer to generate copy-paste ready technical content for Jira tickets, compliance sheets, or meeting outputs.
