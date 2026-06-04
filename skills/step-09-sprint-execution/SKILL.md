---
name: step-09-sprint-execution
description: Track development progress, manage technical delivery, execute impediment resolution/escalation, and perform recurring blocker pattern analysis to improve team velocity.
---

# Step 09 — Sprint Execution & Impediment Management

This skill controls the execution, tracking, and resolution of Sprint delivery. The Scrum Master and Developer roles leverage this step to drive work items to completion, manage escalations, resolve blockers, and analyze systemic impediment trends.

---

## 0. Backbone & Phase Context
*   **Backbone Step:** Step 9 — Sprint Execution & Impediment Management
*   **Scrum Flow Phase:** Phase 1 — Sprint Loop
*   **Primary Owner:** Developers (Increment delivery) & Scrum Master (Impediment resolution).
*   **Core Objective:** Deliver a usable, potentially releasable Increment that meets the Sprint Goal by resolving impediments, managing dependencies, and ensuring technical quality.
*   **Handoff Boundary:**
    *   **Step 08 (Daily Scrum):** Captures and triages blockers within a strict 15-minute timebox.
    *   **Step 09 (Sprint Execution):** Takes ownership of resolving, escalating, documenting, and analyzing patterns of those blockers outside the standup.

---

## 1. Intent Detection & Routing Logic
The assistant triggers this skill when:
*   **English Triggers:** "track sprint progress", "sprint status", "resolve impediment", "close blocker", "impediment resolution", "analyze blocker patterns", "systemic blockers", "delivery status"
*   **Vietnamese Triggers:** "theo dõi tiến độ sprint", "trạng thái sprint", "giải quyết blocker", "đóng rào cản", "xử lý vướng mắc", "phân tích blocker lặp lại", "tìm lỗi hệ thống", "tiến độ hàng ngày"

---

## 2. Mode C: Impediment Resolution & Escalation Management
**Agent Directive (Execution):**
1.  **Locate Log:** Load the active log from `../step-08-daily-scrum/templates/impediment-log.md`.
2.  **Collect Resolution Details:** Ask the Scrum Master for the target Impediment ID and the details of the resolution:
    *   What exactly was done to resolve the blocker?
    *   Who verified the fix?
    *   What is the date of resolution?
3.  **Calculate Total Days Open:** Compute the final duration:
    $$\text{Days Open} = \text{Date Resolved} - \text{Date Raised}$$
4.  **Enforce Resolution Note Guardrail:** Write a comprehensive note to the log. NEVER set an impediment to `Resolved` with a blank or trivial note (e.g., "done" or "fixed"). Doing so violates transparency (Scrum Guide Transparency).
5.  **Escalation Execution:** If the impediment is marked as `Escalated` (Yes):
    *   Document the escalation path (e.g., Escalated to CTO, Escalated to Vendor Management).
    *   Prepare a formal, professional communication draft for the Scrum Master to send to the escalation authority.

---

## 3. Step: Recurring Impediment Pattern Detection
To prevent the team from resolving the same issues repeatedly, the Agent MUST analyze active and resolved impediments across the current and previous Sprints for systemic trends:
1.  **Frequency Analysis:** Check if similar types of blockers (e.g., "waiting for database credentials", "third-party sandbox API downtime", "missing copy translations") have occurred more than twice in the current or prior Sprint.
2.  **Source Identification:** Identify if a specific department, external vendor, or team outside the Scrum Team is a consistent bottleneck.
3.  **Generate Retro Warning:** If a pattern is detected, surface it clearly to the Scrum Master:
    > *"⚠️ **Systemic Impediment Alert:** This is the [N]th time the team has been blocked by [Dependency/Vendor] for [Issue Type]. This indicates a systemic process constraint. I recommend adding this to the upcoming Sprint Retrospective [Step 12](../step-12-sprint-retrospective/SKILL.md) agenda for root-cause analysis rather than treating it as an isolated incident."*

---

## 4. Shared Stakeholder Communication Sub-Skill
During Sprint Execution, stakeholders often request status updates.
*   **Action:** When a progress report, weekly status update, or stakeholder dashboard is requested, the assistant **MUST** invoke the shared stakeholder update skill at [../shared/stakeholder-update/SKILL.md](../shared/stakeholder-update/SKILL.md).
*   **Execution rule:** Follow the steps defined in the shared update skill to assess Sprint health, read the current status, and draft the update in plain business language (e.g., translate technical jargon like "database wallet deadlock mitigation" into "payment system stability adjustments").

---

## 5. Readiness Self-Audit
Before concluding, the Agent MUST verify:
*   [ ] Are all resolutions documented with detailed notes in `../step-08-daily-scrum/templates/impediment-log.md`?
*   [ ] Does the resolution flow compute and lock the final `Days Open` count?
*   [ ] Did I analyze blocker patterns and provide a Retrospective recommendation?
*   [ ] Are all file paths referenced relatively?
