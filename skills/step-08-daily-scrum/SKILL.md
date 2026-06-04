---
name: step-08-daily-scrum
description: Execute Step 8 - Daily Scrum by providing multi-modal support. It assists Developers in preparing Sprint-Goal-focused updates, supports Scrum Masters with pre-meeting preparation, and facilitates the capture/triage of blockers while delegating resolution and pattern analysis to Step 9 (Sprint Execution).
---

### Step 08: Daily Scrum

This skill acts as the central router for the **Daily Scrum** event. It enforces empirical process control by shifting the focus away from traditional status reporting and toward inspecting progress toward the Sprint Goal, planning next-step adjustments, and capturing blockers.

--------------------------------------------------------------------------------

#### 0. Backbone & Phase Context
*   **Backbone Step:** Step 8 — Daily Scrum
*   **Scrum Flow Phase:** Phase 1 — Sprint Loop
*   **Primary Owner:** Developers (The event belongs to them).
*   **Scrum Master Role:** Ensure the event happens, keep it within the 15-minute timebox, and facilitate.
*   **Target Output Deliverables:**
    *   [A] Developer Sync Update (`daily-sync-update.md`)
    *   [B] Scrum Master Impediment Log (`impediment-log.md`) - *Capture phase only*

--------------------------------------------------------------------------------

#### 1. Intent Detection & Routing Logic
When the user triggers this skill, the Agent MUST detect the user's intent based on the prompt keywords and route to the appropriate Mode.

*   **Trigger Keywords for Mode A (Developer Sync Prep):**
    *   *English:* "prepare my standup", "daily sync update", "what did I work on", "prepare standup", "sync update"
    *   *Vietnamese:* "chuẩn bị báo cáo daily", "chuan bi standup", "báo cáo daily", "chuẩn bị standup", "daily report"
*   **Trigger Keywords for Mode B (Impediment Tracking & Blocker Triage):**
    *   *English:* "log an impediment", "track this blocker", "update impediment", "log blocker", "raise impediment"
    *   *Vietnamese:* "ghi nhận blocker", "lưu rào cản", "ghi nhận rào cản", "đánh giá rào cản", "xem blockers hôm nay"
*   **Trigger Keywords for Health Check & Facilitation:**
    *   *English:* "evaluate our daily", "is our daily scrum good", "walk the board", "facilitate daily"
    *   *Vietnamese:* "đánh giá buổi daily", "đánh giá daily scrum", "facilitate buổi daily", "walk the board daily"

*(If Health Check is triggered, silently load `checklists/daily-scrum-health-check.md`)*
*(If Facilitation is triggered, silently load `references/walk-the-board-guide.md`)*

--------------------------------------------------------------------------------

#### 2. Phase 0: Scrum Master Pre-Meeting Prep
Before the Daily Scrum starts, if the Scrum Master requests prep support (or triggers Mode B), the Agent MUST guide the SM through a quick **5-minute preparation routine**:
1.  **Impediment Check:** Read the current `templates/impediment-log.md`. Identify all currently "Open" items. Note which ones are approaching their Target Resolution Date or are already overdue.
2.  **Board Verification:** Remind the SM to verify that the Sprint Backlog board reflects yesterday's resolved items, preventing stale cards from wasting meeting time.
3.  **Agenda Lock:** Prepare to guide the Developers to "Walk the Board" from Right (closest to Done) to Left.

--------------------------------------------------------------------------------

#### 3. Mode A: Developer Sync Preparation
**Agent Directive (Execution):**
1.  **Identify Sprint Goal:** Identify or ask the Developer for the current **Sprint Goal**.
2.  **Collect and Categorize:** Ask the Developer for their raw work updates and sort them into:
    *   *Done since last sync:* Accomplishments that directly contribute to or impact the Sprint Goal.
    *   *Focus for today:* Concrete next actions (avoid vague phrases like "continue working on X").
    *   *Blockers:* Active blockers or risks to completing their commitments.
3.  **Git Integration (Optional):** If a local git repository is present, search git logs to help the developer recover recent commits:
    ```bash
    git log --oneline --since="yesterday 00:00" --author="[Developer Name]"
    ```
4.  **Draft Update:** Load `templates/daily-sync-update.md`. Populate the template using a professional, peer-to-peer tone.
5.  **Guardrail:** Prohibit management status reporting. Strip out arbitrary hour counts or percentages (e.g., "I am 80% done"). If items are unrelated to the Sprint Goal, group them under a separate "Non-Goal Scope" section.
6.  **Review & Confirm Flow:** Before presenting the final output, the Agent MUST ask:
    > *"Does this reflect what you want to share with the team? Say 'looks good' to finalize, or tell me what to adjust."*
    Apply adjustments iteratively. Output the finalized update in a clean copy-pasteable block once confirmed.

--------------------------------------------------------------------------------

#### 4. Mode B: Daily Blocker Logging & Triage (Timeboxed)
To preserve the 15-minute Daily Scrum timebox, impediment management is strictly divided between **Step 08 (Capture & Quick Triage)** and **Step 09 (Resolution & Escalation)**.
*   *Note: Deep troubleshooting, escalation execution, and recurring pattern analysis belong to [Step 09 - Sprint Execution](../step-09-sprint-execution/SKILL.md). Do not perform them during the Daily Scrum.*

##### Mode B1: Log New Impediment (Capture)
1.  **Verification:** Verify if the issue is a true impediment (outside the team's direct control) or a development challenge (which should trigger internal Swarming).
2.  **Collect Fields:** Gather the following details to write to `templates/impediment-log.md`:
    *   `Title`: Clear description of the block.
    *   `Affects`: Story ID / Team member blocked.
    *   `Impact on Sprint Goal`: What happens to the Sprint Goal if this is unresolved.
    *   `Date Raised`: Current date (e.g., `YYYY-MM-DD`).
    *   `Owner`: The person assigned to drive resolution (often the SM).
    *   `Target Date`: Required target resolution date.
    *   `Escalation Required`: Yes/No.
    *   `Days Open`: Initialize to `0`.
3.  **Update Log:** Append the new entry to `templates/impediment-log.md` maintaining the flat, Excel-friendly table.

##### Mode B2: Quick Status Review (Triage)
1.  **List Open Blockers:** Present a summary of currently active impediments.
2.  **Days Open Calculation:** For each open impediment, compute the elapsed days:
    $$\text{Days Open} = \text{Current Date} - \text{Date Raised}$$
3.  **Overdue & Age Flags:** Highlight any impediment where:
    *   `Days Open` exceeds the Sprint length (flags abandoned issues).
    *   `Current Date` is past the `Target Date` (flags overdue issues).
4.  **Handoff to Step 09:** For any blocker requiring resolution, escalation management, or structural change, direct the SM to execute the resolution workflow in [Step 09 - Sprint Execution](../step-09-sprint-execution/SKILL.md).

--------------------------------------------------------------------------------

#### 5. Readiness Self-Audit
Before ending the turn, the Agent MUST perform a self-audit against these criteria:
*   [ ] Did I avoid adding resolution notes or performing pattern analysis in Step 08? (Ensure those are deferred to Step 09).
*   [ ] Did I enforce the "Review & Confirm" flow for the Developer standup update?
*   [ ] Did I exclude percentages and hour estimates from all updates?
*   [ ] Did I calculate and display the `Days Open` count for open blockers during triage?
*   [ ] Are all file references in the output relative paths?
