---
name: step-09-sprint-execution
description: Execute Step 9 - Sprint Execution by managing workflow (Flow & Swarming), enforcing the Definition of Done for the Increment, and guiding the Scrum Master through deep impediment resolution, pattern analysis, and escalation.
---

# Step 09: Sprint Execution & Impediment Management

This skill controls the continuous execution of the Sprint. It empowers Developers to manage their flow, apply swarming techniques, and validate quality. Concurrently, it equips the Scrum Master with deep-dive tools to analyze, resolve, and escalate systemic impediments surfaced during the Daily Scrum.

---

## 0. Backbone & Phase Context
*   **Backbone Step:** Step 9 — Sprint Execution
*   **Scrum Flow Phase:** Phase 1 — Sprint Loop
*   **Primary Owner:** Developers (Increment delivery) & Scrum Master (Impediment resolution).
*   **Core Objective:** Deliver a usable, potentially releasable Increment that meets the Sprint Goal by optimizing flow, validating quality, and removing systemic blockers.
*   **Handoff Boundary (Daily Scrum vs. Sprint Execution):**
    *   **Step 08 (Daily Scrum):** A strict 15-minute timeboxed event focused ONLY on capturing blockers, tracking daily updates, and logging impediments in the Impediment Log. The Agent must NOT attempt to resolve, analyze root causes, or design action plans during Step 08.
    *   **Step 09 (Sprint Execution):** The continuous execution phase. This is where out-of-meeting actions occur: deep impediment investigation (5 Whys), escalation, action plan formulation, Lean workflow tracking, swarming on bottlenecks, and strict Definition of Done (DoD) verification before marking any item as "Done".

---

## 1. Intent Detection & Routing Logic
The Agent MUST detect intent and route to the appropriate execution mode:

| Mode | Target Role | Keywords / Intent (English & Vietnamese) | Action / Guide | Output / Template |
| :--- | :--- | :--- | :--- | :--- |
| **Mode C: Impediment Resolution** | Scrum Master | "resolve impediment", "analyze blocker", "escalate blocker", "lên kế hoạch giải quyết", "xử lý rào cản", "giải quyết blocker", "gỡ vướng mắc", "phân tích rào cản" | `references/impediment-resolution-guide.md` | `templates/impediment-action-plan.md` & update `../step-08-daily-scrum/templates/impediment-log.md` |
| **Mode D: Flow & Swarming** | Developers | "track sprint progress", "sprint status", "check work in progress", "prevent waterfall", "tiến độ sprint", "trạng thái sprint", "xem flow", "tiến độ công việc", "tắc nghẽn" | `references/flow-and-swarming-guide.md` | `templates/sprint-progress-radiator.md` |
| **Mode E: DoD Quality Gate** | Developers | "mark as done", "finish task", "complete ticket", "chuyển sang done", "hoàn thành thẻ", "đạt DoD", "xác nhận hoàn thành" | `checklists/increment-dod-gate.md` | Block or update ticket status |

---

## 2. Mode C: Impediment Resolution & Escalation (Scrum Master)
**Agent Directive:**
1.  **Locate Log:** Read the active log from `../step-08-daily-scrum/templates/impediment-log.md`.
2.  **AI-to-User Interview:** Do not just close the blocker immediately. Engage the Scrum Master using the interview protocol from `references/impediment-resolution-guide.md` (e.g., Five Whys, Ishikawa analysis) to capture:
    *   What exactly was done to resolve the blocker?
    *   Who verified the fix?
    *   What is the date of resolution?
3.  **Calculate Total Days Open:** Compute the final duration using:
    $$\text{Days Open} = \text{Date Resolved} - \text{Date Raised}$$
4.  **Enforce Resolution Note Guardrail:** Write a comprehensive note to the log. NEVER set an impediment to `Resolved` with a blank or trivial note (e.g., "done" or "fixed"). Doing so violates transparency.
5.  **Generate Action Plan & Escalation:** If resolved tactilely, write the detailed note. If escalation is required, load and populate `templates/impediment-action-plan.md` to define cross-departmental actions, escalation email drafts, and Developer contingency plans.

---

## 3. Mode D: Flow Management & Swarming (Developers)
**Agent Directive:**
1.  **Analyze WIP:** Scan the active Sprint Backlog. Identify any columns (e.g., "In QA" or "To Verify") where Product Backlog Items (PBIs) are accumulating.
2.  **Prevent Scrummerfall:** Warn the team if they are exhibiting Waterfall behaviors inside the Sprint (e.g., pulling new items instead of finishing testing on active items), following the principles in `references/flow-and-swarming-guide.md`.
3.  **Generate Digest:** Output `templates/sprint-progress-radiator.md` providing actionable nudges to Swarm (work as a cross-functional unit) on stuck items.

---

## 4. Mode E: Increment Quality Gate (Definition of Done)
**Agent Directive:**
1.  **Intercept "Done" Requests:** When a Developer attempts to mark a feature/PBI as "Done" or "Complete".
2.  **Verify Constraints:** Run `checklists/increment-dod-gate.md`. Ensure strict iGaming constraints (e.g., RTP validation, Security/Fraud checks) are met.
3.  **Block & Coach:** If criteria are missing, politely REFUSE to mark it done. Prompt the Developer: *"To protect the Increment, we need [Missing Test/Audit/Validation]. Who can you Swarm with today to complete this?"*

---

## 5. Recurring Impediment Pattern Detection
To prevent the team from resolving the same issues repeatedly, the Agent MUST analyze active and resolved impediments across the current and previous Sprints for systemic trends:
1.  **Frequency Analysis:** Check if similar types of blockers (e.g., "waiting for database credentials", "third-party sandbox API downtime", "missing copy translations") have occurred more than twice in the current or prior Sprints.
2.  **Source Identification:** Identify if a specific department, external vendor, or team outside the Scrum Team is a consistent bottleneck.
3.  **Generate Retro Warning:** If a pattern is detected, surface it clearly to the Scrum Master:
    *   *"⚠️ **Systemic Impediment Alert:** This is the [N]th time the team has been blocked by [Dependency/Vendor] for [Issue Type]. This indicates a systemic process constraint. I recommend adding this to the upcoming Sprint Retrospective [Step 12](../step-12-sprint-retrospective/SKILL.md) agenda for root-cause analysis rather than treating it as an isolated incident."*

---

## 6. Shared Stakeholder Communication Sub-Skill
During Sprint Execution, stakeholders often request status updates.
*   **Action:** When a progress report, weekly status update, or stakeholder dashboard is requested, the assistant **MUST** invoke the shared stakeholder update skill at [../shared/stakeholder-update/SKILL.md](../shared/stakeholder-update/SKILL.md).
*   **Execution rule:** Follow the steps defined in the shared update skill to assess Sprint health, read the current status, and draft the update in plain business language (e.g., translate technical jargon like "database wallet deadlock mitigation" into "payment system stability adjustments").

---

## 7. Readiness Self-Audit
Before concluding, the Agent MUST verify:
*   **Mode C (Impediment Resolution):**
    *   [ ] Are all resolutions documented with detailed notes in `../step-08-daily-scrum/templates/impediment-log.md`?
    *   [ ] Does the resolution flow compute and lock the final `Days Open` count?
    *   [ ] If Escalated, was `templates/impediment-action-plan.md` outputted?
*   **Mode D (Flow & Swarming):**
    *   [ ] Was WIP limit analyzed and "Scrummerfall" behavior flagged if found?
    *   [ ] Did I output `templates/sprint-progress-radiator.md` with action items to swarm on stuck tasks?
*   **Mode E (DoD Quality Gate):**
    *   [ ] Did I cross-check the PBI against `checklists/increment-dod-gate.md` before approving "Done" status?
    *   [ ] Did I refuse "Done" status and prompt for swarming if any DoD items are missing?
*   **System Integrity:**
    *   [ ] Did I analyze blocker patterns and provide a Retrospective recommendation?
    *   [ ] Are all file paths referenced relatively?
