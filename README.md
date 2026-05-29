# 🎰 Scrum Assistant (iGaming & Online Lottery Edition) 🚀

Welcome to the **Scrum Assistant** repository! This is a highly specialized **Personal Skill Bundle** engineered for the **Google Antigravity IDE** powered by **Gemini**. 

It is tailored specifically for the dual role of a **Senior Business Analyst & Scrum Master** working in high-throughput, transaction-heavy, and strictly regulated **iGaming and Online Lottery** environments.

---

## 🎯 Core Value Proposition

In the high-stakes world of iGaming, standard agile coaching and generic business analysis fall short. This skill bundle bridges the gap:

*   **Dual-Role Synergy:** Bridges the gap between requirements elicitation (**BA**) and delivery execution (**SM**). It guides you to structure features with testing scenarios, mathematical parameters (RTP/math sheets), and clear Definitions of Ready (DoR) and Done (DoD).
*   **iGaming Core Awareness:** Every template and sub-skill natively understands the technical complexities of **Single Wallet ledger locks, RNG GLI-19 compliance, Geofencing checks, Responsible Gaming (RG) gating, and payment gateway callback protocols (MoMo, Crypto).**
*   **Compliance-First Mindset:** Ensures non-negotiable regulatory boundaries are locked down before creative design or engineering sprints begin.
*   **Security & Privacy Decoupled:** Operates as a manual-only flow. No external webhooks or integrations with Jira/ADO MCPs are required—keeping company credentials and internal code repositories completely secure. Outputs copy-paste ready Markdown formats.

---

## 📁 Repository Directory Structure

```text
scrum-assistant/
│
├── SKILL.md                        # Primary Router & Entrypoint for Antigravity
├── ARCHITECTURE.md                 # Folder layout guide & system boundary map
├── README.md                       # This repository homepage
├── .gitignore                      # Git tracking exemptions (hides private refs/)
│
├── refs/                           # [PRIVATE - GIT IGNORED] Private developer scratchpad
│   ├── jd-senior-ba-sm.md          # Dual BA/SM responsibilities
│   ├── business-analyst.md         # BABOK framework notes
│   └── scrum-master.md             # Scrum ceremonies guide
│
├── reference/                      # [PACKAGED - GIT TRACKED] Tri thức domain (Domain knowledge)
│   ├── igaming-context.md          # iGaming & Lottery domain context & dictionary
│   └── jd-guidelines.md            # Standard JD context mapping
│
└── skills/                         # Active sub-skills & technical templates
    │
    ├── po-ba/                      # [BA/PO Accountabilities]
    │   ├── ba-user-stories/
    │   │   └── SKILL.md            # INVEST & BDD Gherkin story creation
    │   ├── ba-requirements-elicitation/
    │   │   └── SKILL.md            # Stakeholder interviews & JAD workshops
    │   └── ba-impact-analysis/
    │       └── SKILL.md            # Change Request (CR) systems impact assessment
    │
    ├── sm-ops/                     # [SM Operations & Metrics] (Upcoming)
    │   ├── sm-capacity-planning/
    │   ├── sm-velocity-review/
    │   ├── sm-impediment-log/
    │   └── sm-stakeholder-update/
    │
    ├── ceremonies/                 # [Sprint Events & Outputs] (Upcoming)
    │   ├── sprint-planning/
    │   ├── daily-sync/
    │   ├── refinement/
    │   ├── sprint-review/
    │   └── retrospective/
    │
    └── templates/                  # Shared Document & Modeling templates
        ├── user-story-bdd.md       # Standard BDD story structure
        ├── sprint-goal-canvas.md   # Scrum Master planning canvas
        ├── game-rules-math-sheet.md # Lottery rules, prize tiers & RTP spec sheet
        └── third-party-integration-matrix.md # API connectivity matrix (Kambi, MoMo, Crypto)
```

---

## 🛠️ Sub-Skills Routing Matrix

| Sub-Skill Area | Purpose | Key Trigger Keywords |
|:---|:---|:---|
| 📝 **[ba-user-stories](skills/po-ba/ba-user-stories/SKILL.md)** | Crafting INVEST stories & Gherkin BDD AC | `user story`, `Gherkin`, `BDD`, `acceptance criteria` |
| 🗣️ **[ba-requirements-elicitation](skills/po-ba/ba-requirements-elicitation/SKILL.md)** | Elicitation checklists for Compliance & Tech Leads | `elicitation`, `interview`, `JAD`, `workshop` |
| 🛡️ **[ba-impact-analysis](skills/po-ba/ba-impact-analysis/SKILL.md)** | Change Request systems & compliance audits | `impact assessment`, `change request`, `CR`, `compliance` |

---

## 🚀 How to Install & Use inside Antigravity

### 1. Registration
Place this bundle directory under your active Antigravity skills search path (e.g., local project `.agent/skills/` or global `~/.gemini/skills/`).

### 2. Auto-Discovery
The Antigravity IDE will scan the directory and read the root `SKILL.md` frontmatter trigger:
```yaml
Use when executing Scrum Master ceremonies, writing business requirements, drafting User Stories, running impact analysis, planning team capacity, or auditing backlog health in the iGaming or online Lottery domain.
```

### 3. Prompting the Agent
Simply speak naturally or mention the specific task. The agent will dynamically load the corresponding sub-skill:
*   *"Help me write a user story for a transfer wallet bet logic."* $\rightarrow$ Triggers `ba-user-story-craft`.
*   *"Prepare an elicitation questionnaire for launching in Pennsylvania."* $\rightarrow$ Triggers `ba-requirements-elicitation`.
*   *"Compliance wants to add instant tax calculations mid-sprint, draft an impact check."* $\rightarrow$ Triggers `ba-impact-analysis`.
