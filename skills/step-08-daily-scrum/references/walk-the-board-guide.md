---
artifact_name: Walk the Board Reference Guide
purpose: Provide the AI Agent with the cognitive framework to facilitate the Daily Scrum using the flow-based "Walk the Board" technique. This ensures the event focuses on inspecting progress toward the Sprint Goal and adapting the Sprint Backlog, completely eliminating the "status report" anti-pattern.
---

### Walk the Board Reference Guide
This document serves as the hidden logic engine for the Scrum Assistant during **Step 8 - Daily Scrum**. It directs the Agent to guide the Developers away from individual status updates ("What I did") and toward a collective, flow-based inspection of the work ("How do we get this item to Done?").

--------------------------------------------------------------------------------

#### 1. Core Principles of "Walk the Board"
*   **Flow over Utilization:** Traditional Daily Scrums focus on making sure everyone is busy (100% utilization). "Walk the Board" focuses on making sure the work is flowing smoothly through the system toward the Definition of Done.
*   **Stop Starting, Start Finishing (Lean Thinking):** The focus is always on the items closest to completion. Bringing an in-progress item to "Done" is always prioritized over pulling a new item from the "To Do" column.
*   **Team Ownership over Individual Tasks:** The board is reviewed by Product Backlog Item (PBI), not by person. If a PBI is blocked or moving slowly, the entire team of Developers must collaborate (Swarm) to move it forward.

--------------------------------------------------------------------------------

#### 2. The Execution Loop (Agent Algorithm)
When facilitating the Daily Scrum, the Agent MUST guide the Developers to read the Sprint Backlog from **Right to Left** (closest to completion to newest). 

For each active Product Backlog Item (PBI) on the board, the Agent prompts the team with the following flow:
1.  **Inspect the Item:** Look at the PBI closest to the "Done" column.
2.  **Ask the Flow Questions:** 
    *   *"What do we need to do collectively today to move this specific item to 'Done'?"*
    *   *"Is this item progressing toward the **Sprint Goal**?"*
    *   *"Are there any hidden tasks or impediments slowing this down?"*
3.  **Trigger Swarming:** If an item is stuck or complex, ask: *"Who has available capacity to pair up or swarm on this item today so we can finish it?"*
4.  **Repeat:** Move to the next PBI to the left. Stop when the 15-minute timebox is up or all active items are reviewed.

Once all active items are reviewed, the Agent MUST execute the final wrapping step:
5.  **Sprint Goal Confidence Poll:** Conduct a quick poll asking the team:
    > *"On a scale of 1-5, how confident are we that we will achieve the Sprint Goal by the end of the Sprint?"*
    *   **If Confidence >= 3:** Log the score and conclude the event.
    *   **If Confidence < 3:** Do NOT wait for the next day. Trigger an immediate post-Daily huddle (After-Party) with the relevant developers to replan, adjust scope, or escalate blockers.

--------------------------------------------------------------------------------

#### 3. Handling Blockers & Agent Synergy
*   **Identify Impediments:** If a Developer states an item cannot move forward due to external dependencies (e.g., waiting for API keys, environments down), the Agent MUST recognize this as an impediment.
*   **Do Not Problem-Solve:** The Agent must strictly enforce the 15-minute timebox. If technical problem-solving begins, the Agent interrupts: *"Let's take this technical discussion offline right after the Daily Scrum. I will log this blocker now."*
*   **Silent Handoff:** The Agent must log the blocker in `templates/impediment-log.md` (Step 08 Mode B1) and direct the Scrum Master to drive the resolution workflow in [Step 09 - Sprint Execution](../step-09-sprint-execution/SKILL.md).

--------------------------------------------------------------------------------

#### 4. Agent Anti-Patterns (What to Prevent)
*   **The "Status Report" Trap:** If the Developers start facing the Product Owner or Scrum Master to report their hours or individual tasks, the Agent MUST redirect: *"Let's redirect our attention back to the Sprint Backlog board and focus on what needs to be done to achieve the Sprint Goal."*
*   **Ignoring the Sprint Goal:** The Agent MUST conclude the Daily Scrum by running the Confidence Poll step. Never let the meeting end without a clear reading on the Sprint Goal's feasibility.

