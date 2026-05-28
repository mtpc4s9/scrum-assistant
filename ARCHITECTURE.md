# Scrum Assistant - System Architecture & Directory Structure

This document outlines the file layout and directory organization of the `scrum-assistant` skill bundle. It serves as a physical map for developers and AI agents to locate reference materials, active sub-skills, and templates.

---

## 1. Physical Directory Tree

```text
scrum-assistant/
│
├── SKILL.md                    # Root Router (Entry point for Antigravity)
├── ARCHITECTURE.md             # This file (System layout map)
│
├── refs/                       # Foundational references & Domain Context
│   ├── jd-senior-ba-sm.md      # Dual BA/SM responsibilities
│   ├── business-analyst.md     # BABOK framework notes
│   ├── scrum-master.md         # Scrum ceremonies guide
│   ├── technical-writer.md     # Documentation style guidelines
│   ├── structure.md            # Generic reference layout
│   ├── techniques.md           # Core Scrum/BA techniques list
│   ├── techniques.xlsx         # Planning spreadsheet
│   └── igaming-context.md      # iGaming & Lottery domain dictionary
│
└── skills/                     # Active sub-skills & templates
    │
    ├── ba-user-story-craft/
    │   └── SKILL.md            # INVEST & BDD Gherkin story creation
    │
    ├── ba-requirements-elicitation/
    │   └── SKILL.md            # Stakeholder mapping & elicitation workshops
    │
    ├── ba-impact-analysis/
    │   └── SKILL.md            # Change Request systems & compliance gating
    │
    └── templates/                  # Document & Modeling templates (Lottery ready)
        ├── user-story-bdd.md       # Standard BDD story structure
        ├── sprint-goal-canvas.md   # Scrum Master planning canvas
        ├── game-rules-math-sheet.md # [NEW] Lottery prize & RTP template
        └── third-party-integration-matrix.md # [NEW] Vendor API integration matrix
```

---

## 2. Directory Layer Mapping

### 2.1 Root Level (`/`)
*   **SKILL.md:** Acts as the primary router. When the AI agent encounters a generic BA/SM request, this file directs the agent to load the precise sub-skill path using `view_file`.
*   **ARCHITECTURE.md:** Provides directory visibility, helping the agent comprehend where templates and supporting context files are located.

### 2.2 Domain References (`/refs/`)
*   Contains long-term, read-only documentation. The agent references these files to match Chàng's specific business parameters (e.g. alignment with the Senior JD or local lottery compliance terminologies in `igaming-context.md`).

### 2.3 Active Sub-Skills (`/skills/`)
*   Functional units containing executable guidelines and specific templates. Every active directory has its own `SKILL.md` with a unique YAML `name` tag contract, facilitating independent dynamic loading by Antigravity.

### 2.4 Shared Templates (`/skills/templates/`)
*   Ready-to-use Markdown templates. Sub-skills draw from this layer to generate copy-paste ready technical content for Jira tickets, compliance sheets, or meeting outputs.
