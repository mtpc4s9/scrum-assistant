---
name: step-12-sprint-retrospective
description: Orchestrates Step 12 - Sprint Retrospective. Facilitates prework, generates slide decks, audits retrospective raw data for patterns, and semi-automatically triages action items into the Sprint Backlog or Insight Backlog for the user to manually input into their PM tool.
---

### Step 12: Sprint Retrospective (Orchestrator & Audit Engine)
This skill serves as the central cognitive router and auditor for the **Sprint** Retrospective. It enforces pre-meeting data collection, provides facilitation frameworks during the event, and acts as a strict auditor post-event to ensure insights are translated into actionable, tracked items rather than just venting.

--------------------------------------------------------------------------------

#### 0. Backbone & Phase Context
*   **Backbone Step:** Step 12 — Sprint Retrospective
*   **Scrum Flow Phase:** Phase 1 — Sprint Loop
*   **Primary Owner:** Scrum Master (facilitates); entire Scrum Team participates.
*   **Core Objective:** Inspect how the last Sprint went and Adapt by identifying actionable improvements for the next Sprint.
*   **Architectural Role:** Orchestrator & Auditor. Operates in a **Semi-Auto** mode (outputs physical markdown for the user to manually create PM tool tickets).

--------------------------------------------------------------------------------

#### 1. Intent Detection & Routing Logic
The Agent MUST detect intent and route to the appropriate execution mode:

*   **Mode A (Prework & Slide Generation - Pre-Meeting):** 
    *   *Keywords:* "prepare retro", "create retro slides", "chuẩn bị retro", "tạo slide".
    *   *Action:* Silently load `checklists/retrospective-prework-checklist.md`. Conduct the mandatory AI-to-User interview. Only generate `templates/sprint-retrospective-slide-deck.md` when answers are provided.

*   **Mode B (Audit, Pattern Recognition & Triage - Post-Meeting):** 
    *   *Keywords:* "audit retro", "process retro notes", "tổng hợp retro", "xử lý kết quả".
    *   *Action:* Silently load `references/retrospective-facilitation-guide.md` and `templates/insight-backlog.md`. Process the user's raw notes using the **Embedded Audit Protocol** below.

--------------------------------------------------------------------------------

#### 2. Embedded Audit & Pattern Protocol (For Mode B)
When processing raw retrospective notes, the Agent MUST execute the following steps:

1.  **Parse & Structure:** Categorize the raw input into standard buckets: *Went well, To improve, Action items, Questions/Kudos*.
2.  **Identify Patterns (Theme Clusters):** Analyze the "To improve" items and group them into themes such as:
    *   *Process:* Sprint ceremonies, planning quality.
    *   *Technical:* Build stability, tech debt, testing.
    *   *Communication:* Intra-team, with stakeholders.
    *   *Tooling:* PM tools, CI/CD, environments.
    *   *Clarity:* Story quality, Sprint Goal focus.
3.  **Volume Signals:** Note if there are significantly more "To improve" items than "Went well" (indicating team strain), or very few items overall (indicating low psychological safety or participation).
4.  **Action Item Audit:** Evaluate every proposed action item. Does it describe a concrete change? Warn the user if an action item is vague (e.g., "communicate better") and propose a concrete alternative (e.g., "Establish a Slack channel for deployment alerts").
5.  **Triage (Task vs. PBI vs. Deferred):** Apply the triage logic from `insight-backlog.md` to classify actions as Type A (Sprint Backlog Task), Type B (Product Backlog PBI), or Type C (Deferred to Insight Backlog).

--------------------------------------------------------------------------------

#### 3. Semi-Auto Execution Guardrails
*   **No API Automation:** The Agent MUST NOT attempt to connect to Jira, ADO, or any external API to create tickets automatically.
*   **Markdown Handoff:** The Agent MUST output the finalized, audited action items as beautifully formatted Markdown blocks (Title, Description, Acceptance Criteria) and explicitly instruct the user: *"Please copy these formatted items and manually create them in your Jira/ADO boards to ensure proper tracking."*
*   **Don't Separate, Integrate:** Remind the user to place Type A tasks directly into the upcoming **Sprint Backlog** during tomorrow's Sprint Planning.
