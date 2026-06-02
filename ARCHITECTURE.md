# Scrum Assistant - System Architecture & Directory Layout

This document outlines the file layout, directory organization, and cross-reference architecture of the `scrum-assistant` toolkit. It serves as a physical map for developers and AI agents to locate reference materials, active sub-skills, and templates, aligning directly with the **Scrum Flow Backbone** ([scrum-flow-backbone.md](file:///C:/Users/TruongPhan/.gemini/antigravity/scratch/scrum-assistant/reference/scrum-flow-backbone.md)).

---

## 1. Directory Tree Map

The structure maps directly to the 12-step Scrum Flow, accountabilities (Product Owner, Business Analyst, Scrum Master), and reference domains.

```text
scrum-assistant/
│
├── SKILL.md                        # Root Router (Entry point for Antigravity discovery)
├── ARCHITECTURE.md                 # This file (System layout & mapping guide)
│
├── reference/                      # [PACKAGED - GIT TRACKED] Domain & Process references
│   ├── scrum-flow-backbone.md          # Master 12-step flow guide (Backbone)
│   ├── igaming-context.md              # Domain terminology, RNG, PAM, regulatory context
│   ├── game-rules-math-sheet.md        # Reference template: RTP, prize tier, lottery rules
│   ├── third-party-integration-matrix.md # Reference template: connectivity matrix (MoMo, Kambi, etc.)
│   └── jd-guidelines.md                # Standard role description context mapping
│
└── skills/                         # Executable guidelines & sub-skills
    │
    ├── step-01-visioning/
    │   ├── SKILL.md                # Visioning (Backbone Step 1)
    │   ├── checklists/
    │   │   └── input-readiness.md  # Quality gate checklist
    │   └── templates/
    │       ├── elevator-pitch.md
    │       ├── initial-stakeholder-map.md
    │       └── product-vision-board.md
    ├── step-02-goal-setting/
    │   └── SKILL.md                # Goal Setting (Backbone Step 2)
    ├── step-03-goal-prioritization/
    │   └── SKILL.md                # Goal Prioritization (Backbone Step 3)
    ├── step-04-backlog-creation/
    │   ├── SKILL.md                # Backlog Creation & Story Writing (Backbone Step 4)
    │   ├── checklists/
    │   │   └── quality-checklist.md
    │   ├── references/
    │   │   ├── examples.md
    │   │   └── invest-criteria.md
    │   └── templates/
    │       ├── ac-template.md
    │       └── user-story-specification.md
    ├── step-05-release-planning/
    │   └── SKILL.md                # Release Planning (Backbone Step 5)
    ├── step-06-standards-setup/
    │   └── SKILL.md                # Standards Setup (DoR/DoD/Norms) (Backbone Step 6)
    ├── step-07-sprint-planning/
    │   └── SKILL.md                # Sprint Planning (Backbone Step 7)
    ├── step-08-daily-scrum/
    │   └── SKILL.md                # Daily Scrum (Backbone Step 8)
    ├── step-09-sprint-execution/
    │   └── SKILL.md                # Sprint Execution & Impediment Management (Backbone Step 9)
    ├── step-10-refinement/
    │   └── SKILL.md                # Backlog Refinement (Backbone Step 10)
    ├── step-11-sprint-review/
    │   └── SKILL.md                # Sprint Review (Backbone Step 11)
    ├── step-12-sprint-retrospective/
    │   └── SKILL.md                # Sprint Retrospective (Backbone Step 12)
    │
    ├── audit-user-story/
    │   └── SKILL.md                # INVEST quality checks & story audits
    ├── audit-sprint-health/
    │   └── SKILL.md                # Sprint hygiene, WIP limits, & metric checks
    ├── audit-backlog/
    │   └── SKILL.md                # Backlog readiness & prioritization audits
    │
    ├── shared
    │    ├── product-discovery/
    │
    │    ├── user-story-writing/
    │
    └── templates/                  # Shared document & canvas templates
        ├── agile_a4_sprint_report.md  # A4 print-ready summary report
        ├── impact_mapping_canvas.md   # Product goal to feature breakdown canvas
        ├── sprint_planning_deck.md    # Ceremony presentation layout
        └── story_mapping_board.md     # Visual story mapping structure
```

---

## 2. Backbone Mapping

The sub-skills directory structure corresponds directly to the step sequence defined in `reference/scrum-flow-backbone.md`:

| Backbone Phase | Step | Action / Ceremony | Sub-Skill Path |
| :--- | :--- | :--- | :--- |
| **PHASE 0: Initiative** | Step 1 | Visioning | `skills/step-01-visioning/` |
| | Step 2 | Goal Setting | `skills/step-02-goal-setting/` |
| | Step 3 | Goal Prioritization | `skills/step-03-goal-prioritization/` |
| | Step 4 | Product Backlog Creation | `skills/step-04-backlog-creation/` |
| | Step 5 | Release Planning | `skills/step-05-release-planning/` |
| | Step 6 | Standards Setup (DoR/DoD/Norms) | `skills/step-06-standards-setup/` |
| **PHASE 1: Sprint Loop** | Step 7 | Sprint Planning | `skills/step-07-sprint-planning/` |
| | Step 8 | Daily Scrum | `skills/step-08-daily-scrum/` |
| | Step 9 | Sprint Execution / Impediments | `skills/step-09-sprint-execution/` |
| | Step 10 | Backlog Refinement | `skills/step-10-refinement/` |
| | Step 11 | Sprint Review | `skills/step-11-sprint-review/` |
| | Step 12 | Sprint Retrospective | `skills/step-12-sprint-retrospective/` |

---

## 3. Directory Layer Design & Rules

To ensure portability and searchability across different user setups, follow these structural rules:

### 3.1 Relative Linking Rule
*   **Do not use absolute paths** (e.g., `C:\Users\...`) inside any file.
*   Always use relative Markdown links (e.g., `../../reference/igaming-context.md`) to allow the bundle to remain portable and error-free when cloned.

### 3.2 Sub-Skill Router Standard
*   Every sub-skill directory must have a file named exactly `SKILL.md` (capitalized).
*   The `SKILL.md` file must contain a YAML frontmatter block with `name` and `description` to support Antigravity's discovery mechanism.

### 3.3 Reference vs Refs Rule
*   `reference/` contains shared, git-tracked domain knowledge templates (`igaming-context.md`, `scrum-flow-backbone.md`).
*   `refs/` is strictly for personal developer logs, drafts, and raw context notes. It is included in `.gitignore` to prevent committing proprietary workspace items.

### 3.4 Language and Tone Rule
*   All file names and system documentation must be in **English**.
*   Sub-skills (`SKILL.md` and related markdown files) must use professional English and remain free of personal pronouns or conversational exchanges.

### 3.5 Folder Naming Convention Rule
*   All step folders must follow the format `step-{NN}-{slug}`, where `{NN}` is a zero-padded two-digit number (e.g., `01`, `02`, `12`) and `{slug}` is the lowercase, hyphenated representation of the step name (e.g., `step-02-goal-setting`).
*   When the user makes requests using natural language names (e.g., "Goal Setting"), the AI agent matches the request to the matching folder (e.g., `step-02-goal-setting`).
