---
artifact_name: Story Splitting Cognitive Guide
purpose: Instruct the Step 10 Refinement Agent on how to detect oversized Product Backlog Items (PBIs) and intelligently hand off the actual splitting execution to the dedicated Shared Skill (../shared/story-splitting/SKILL.md).
---

### 🤖 AGENT DIRECTIVE (COGNITIVE ROUTING LOGIC)

This document is the routing engine for dealing with oversized items during **Product Backlog** Refinement. The Step 10 Agent MUST NOT attempt to split stories without structure. Instead, it must prepare the context and invoke the Shared Skill.

#### 1. Identification of Oversized PBIs (The Trigger)
During Refinement, the Agent must actively monitor the size and complexity of the PBI. A PBI is deemed "Too Large" (violating the Definition of Ready) if:
*   The **Developers** estimate it will take more than a full **Sprint** to complete.
*   The item contains the word "Epic" or "Feature".
*   The Acceptance Criteria list contains multiple distinct workflows, user personas, or both Happy/Unhappy paths merged into one card.

#### 2. The Socratic Handoff (Agent-to-User Protocol)
When an oversized PBI is detected, the Agent MUST pause Refinement and propose invoking the specialized Splitting Skill. 
*   **Prompt Formula:** *"This PBI [ID/Title] appears too large to fit comfortably into a single Sprint, which introduces risk and violates our DoR. I recommend we apply one of our 9 Agile Splitting Patterns (e.g., splitting by workflow, data variation, or business rules). Shall I invoke the Story Splitting Agent to analyze and generate the smaller slice options for you?"*

#### 3. Delegation to Shared Skill
Once the user confirms, the Step 10 Agent MUST invoke the core skill located at:
👉 `../shared/story-splitting/SKILL.md`

Pass the following context to the Shared Skill:
*   The PBI ID or pasted content.
*   The suspected reason it is too big (e.g., "Contains 3 different user roles").

#### 4. Post-Split Verification (The Return Loop)
After the Shared Skill has successfully generated the new, smaller PBIs, the Step 10 Agent resumes control.
*   **Action:** Take the newly generated PBIs and immediately run them through `checklists/dor-readiness-check.md` to ensure the new slices now meet the Definition of Ready for upcoming Sprints.
*   **Guardrail Check:** Ensure no newly split PBI is a "Technical Layer" story (e.g., a "Database only" story). Every split item must represent a vertical slice of end-to-end value that can form a valid **Increment**.
