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
├── README.md                       # Repository homepage (GitHub optimized)
├── .gitignore                      # Git exemptions (hides private scratchpads like refs/)
│
├── reference/                      # [PACKAGED - GIT TRACKED] Domain & Process references
│   ├── scrum-flow-backbone.md          # Master 12-step flow guide (Backbone)
│   ├── igaming-context.md              # Domain terminology, RNG, PAM, regulatory context
│   ├── game-rules-math-sheet.md        # Reference template: RTP, prize tier, lottery rules
│   ├── third-party-integration-matrix.md # Reference template: connectivity matrix (MoMo, Kambi, etc.)
│   └── jd-guidelines.md                # Standard role description context mapping
│
├── refs/                           # [PRIVATE - GIT IGNORED] Developer personal scratchpad
│   └── (Private notes, raw draft logs, unformatted text files)
│
└── skills/                         # Executable guidelines & sub-skills
    │
    ├── po-ba/                      # [PO/BA Accountabilities] - Initiative & Requirements
    │   ├── product-vision/
    │   │   └── SKILL.md            # Visioning & Goal Setting (Backbone Steps 1–3)
    │   ├── ba-user-stories/
    │   │   └── SKILL.md            # Backlog Creation & Story Writing (Backbone Step 4)
    │   ├── release-planning/
    │   │   └── SKILL.md            # Release mapping & velocity forecast (Backbone Step 5)
    │   ├── ba-requirements-elicitation/
    │   │   └── SKILL.md            # Elicitation workshops, user research, stakeholder maps
    │   └── ba-impact-analysis/
    │       └── SKILL.md            # Change Request impact & regulatory gating
    │
    ├── sm-ops/                     # [SM Operations] - Infrastructure & Performance
    │   ├── working-agreements/
    │   │   └── SKILL.md            # Team norms, DoR, and DoD setup (Backbone Step 6)
    │   ├── impediment-management/
    │   │   └── SKILL.md            # Blocker tracking & escalation logs (Backbone Step 9)
    │   ├── sm-capacity-planning/
    │   │   └── SKILL.md            # Sprint capacity calculations & ranges
    │   ├── sm-velocity-review/
    │   │   └── SKILL.md            # Sprint predictability & historical velocity analysis
    │   └── sm-stakeholder-update/
    │       └── SKILL.md            # Progress communication & stakeholder sync drafts
    │
    ├── ceremonies/                 # [Sprint Events & Artifacts] - Sprint Loop
    │   ├── sprint-planning/
    │   │   └── SKILL.md            # Sprint planning ritual & task breakdown (Backbone Step 7)
    │   ├── daily-scrum/
    │   │   └── SKILL.md            # 15-minute Daily sync & walk-the-board (Backbone Step 8)
    │   ├── refinement/
    │   │   └── SKILL.md            # Ongoing backlog grooming & story splitting (Backbone Step 10)
    │   ├── sprint-review/
    │   │   └── SKILL.md            # Live demo feedback & DoD inspection (Backbone Step 11)
    │   └── sprint-retrospective/
    │       └── SKILL.md            # Actionable continuous improvement (Backbone Step 12)
    │
    ├── audit-user-story/
    │   └── SKILL.md                # INVEST quality checks & story audits
    ├── audit-sprint-health/
    │   └── SKILL.md                # Sprint hygiene, WIP limits, & metric checks
    ├── audit-backlog/
    │   └── SKILL.md                # Backlog readiness & prioritization audits
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
| **PHASE 0: Initiative** | Step 1 | Visioning | `skills/po-ba/product-vision/` |
| | Step 2 | Goal Setting | `skills/po-ba/product-vision/` |
| | Step 3 | Goal Prioritization | `skills/po-ba/product-vision/` |
| | Step 4 | Product Backlog Creation | `skills/po-ba/ba-user-stories/` |
| | Step 5 | Release Planning | `skills/po-ba/release-planning/` |
| | Step 6 | Standards Setup (DoR/DoD/Norms) | `skills/sm-ops/working-agreements/` |
| **PHASE 1: Sprint Loop** | Step 7 | Sprint Planning | `skills/ceremonies/sprint-planning/` |
| | Step 8 | Daily Scrum | `skills/ceremonies/daily-scrum/` |
| | Step 9 | Sprint Execution / Impediments | `skills/sm-ops/impediment-management/` |
| | Step 10 | Backlog Refinement | `skills/ceremonies/refinement/` |
| | Step 11 | Sprint Review | `skills/ceremonies/sprint-review/` |
| | Step 12 | Sprint Retrospective | `skills/ceremonies/sprint-retrospective/` |

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
