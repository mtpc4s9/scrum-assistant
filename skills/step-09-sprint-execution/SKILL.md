---
name: step-09-sprint-execution
description: Track development progress, ensure technical excellence, and log/resolve impediments.
---

# Step 09 — Sprint Execution

This skill controls the execution and tracking of the Sprint delivery. The Scrum Master and Developer roles leverage this step to track progress, raise impediments, and maintain transparency.

---

## 0. Backbone & Phase Context
*   **Backbone Step:** Step 9 — Sprint Execution & Impediment Management
*   **Scrum Flow Phase:** Phase 1 — Sprint Loop
*   **Primary Owner:** Developers (Increment delivery) & Scrum Master (Impediment resolution).
*   **Core Objective:** Deliver a usable, potentially releasable Increment that meets the Sprint Goal while continuously tracking velocity, managing blockers, and communicating progress.

---

## 1. Step Guidelines

### 1.1 Trigger Conditions & Keywords
The assistant triggers this skill when:
*   **English Triggers:** "track sprint progress", "sprint status", "log blocker", "impediment", "daily progress", "delivery status"
*   **Vietnamese Triggers (Trữ nguyên trạng):** "theo dõi tiến độ sprint", "trạng thái sprint", "ghi nhận blocker", "vướng mắc", "tiến độ hàng ngày", "tình hình bàn giao"

### 1.2 Impediment and Blocker Management
*   Help the Scrum Master list active blocks and determine path-to-resolution:
    *   *Technical Blocks:* e.g., third-party API downtime (Kambi, Pragmatic Play).
    *   *Business Blocks:* e.g., missing business rules for local payment methods (MoMo transaction cap limits).
*   Formulate mitigation plans and assign owners.

---

## 2. Shared Stakeholder Communication Sub-Skill

During Sprint Execution, stakeholders or steering committees often request ad-hoc updates, weekly reports, or sprint dashboards. 

*   **Action:** When a progress report, weekly status update, or stakeholder notification is requested, the assistant **MUST** invoke the shared stakeholder update skill at [../shared/stakeholder-update/SKILL.md](../shared/stakeholder-update/SKILL.md).
*   **Execution rule:** Follow the steps defined in the shared update skill to assess Sprint health, read the current status, and draft the update in plain business language (translating technical iGaming terminology such as "database wallet deadlock mitigation" into "payment processing system safety adjustments").
