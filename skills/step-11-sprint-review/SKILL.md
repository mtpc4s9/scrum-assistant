---
name: step-11-sprint-review
description: Orchestrates Step 11 - Sprint Review. Enforces pre-meeting logistics and DoD validation, generates the presentation slide deck, and triages post-meeting live notes into new Product Backlog Items or Audience-Specific Release Notes.
---

### Step 11: Sprint Review (Orchestrator)
This skill serves as the central cognitive router for the Sprint Review event. It acts as a strict gatekeeper before the meeting (Prework) to protect Transparency, and functions as an intelligent triage engine after the meeting to route stakeholder feedback and release decisions to the appropriate shared worker skills.

--------------------------------------------------------------------------------

#### 0. Backbone & Phase Context
*   **Backbone Step:** Step 11 — Sprint Review
*   **Scrum Flow Phase:** Phase 1 — Sprint Loop
*   **Primary Owner:** Scrum Team + Stakeholders (Collaborative working session).
*   **Core Objective:** Inspect the "Done" Increment, discuss market changes, and Adapt the Product Backlog and Release Plan.
*   **Architectural Role:** Orchestrator. Relies on `../shared/` skills for final PBI and Release Note generation.

--------------------------------------------------------------------------------

#### 1. Intent Detection & Routing Logic
The Agent MUST detect intent and route to the appropriate execution mode:

*   **Mode A (Prework & Slide Generation - Pre-Meeting):** 
    *   *Keywords:* "prepare for review", "create slides", "chuẩn bị sprint review", "tạo slide".
    *   *Action:* Silently load `checklists/sprint-review-prework-checklist.md`. Conduct the mandatory AI-to-User interview with the **Product Owner**. Only after all answers are validated, generate `templates/sprint-review-slide-deck.md`.

*   **Mode B (Live Notes Triage & Handoff - Post-Meeting):** 
    *   *Keywords:* "process feedback", "triage notes", "xử lý live notes", "làm release notes".
    *   *Action:* Silently load `references/feedback-triage-guide.md`. Analyze the provided `[LIVE NOTES]` from the slide deck.

--------------------------------------------------------------------------------

#### 2. Mode B Handoff Guardrails (Embedded Release Note Intelligence)
When operating in Mode B and the user explicitly states "ACCEPT" for a release decision, the Step 11 Agent MUST prepare the payload for the Release Note Worker by adhering to these embedded rules:

1.  **Enforce the Definition of Done:** Filter out any items marked as "Partial" or "In Progress". Only strictly "Done" items from the Sprint can be included in the release handoff.
2.  **Audience Identification (Trigger Socratic Prompt):** Ask the **Product Owner**: *"Before I generate the Release Notes, who is the target audience? (1. Customers/End Users - Plain language, no jargon; 2. Internal Stakeholders - Business outcomes & metrics; 3. Technical Stakeholders - Arch changes & migrations)."*
3.  **Technical Debt Filter:** Do not pass purely technical work items (e.g., infrastructure, dependency bumps) to the worker UNLESS the chosen audience is "Technical Stakeholders" or the item has a direct, visible user impact.
4.  **Delegation:** Once the audience is confirmed, package the filtered "Done" items + Audience context + Theme groupings, and trigger the Shared Skill:
    👉 `../shared/po-release-notes/SKILL.md`

--------------------------------------------------------------------------------

#### 3. Continuous Adaptation
Once shared skills return the generated artifacts (new PBIs or Release Notes), the Step 11 Agent resumes control, reminding the **Product Owner**: *"The Product Backlog has been adapted based on today's inspection. These new items will be prioritized and refined before entering any future Sprint."*
