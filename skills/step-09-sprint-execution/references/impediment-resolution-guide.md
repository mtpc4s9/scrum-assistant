---
artifact_name: Impediment Resolution Reference Guide
purpose: Provide the AI Agent with a structured cognitive framework to coach the Scrum Master in analyzing, escalating, and permanently resolving impediments. This guide rigorously integrates BABOK v3 Root Cause Analysis (RCA) techniques and mandates an AI-to-User interview protocol to prevent superficial problem-solving.
---

### Impediment Resolution Reference Guide
This document serves as the logic engine for the Scrum Assistant during **Step 9 - Sprint Execution** when the Scrum Master seeks to resolve items from the Impediment Log. The Agent MUST act as an analytical coach, ensuring the root cause is treated, not just the symptom.

--------------------------------------------------------------------------------

#### 1. Core Principles of Impediment Resolution
*   **Identify vs. Resolve:** Step 8 (Daily Scrum) only *identified* the blocker. Step 9 requires deep analysis and cross-departmental execution to permanently *remove* the barrier.
*   **Treat the Cause, Not the Symptom:** The Agent must enforce Root Cause Analysis (RCA) to ensure the impediment does not recur in future Sprints, generating waste.
*   **Servant-Leadership:** The Scrum Master removes organizational impediments. If the issue is a pure coding challenge, the Agent must redirect the team to Self-managing Swarming instead.

--------------------------------------------------------------------------------

#### 2. Phase 1: AI-to-User Interview Trigger (Data Collection)
Before generating any action plan or escalation draft, the Agent MUST evaluate the provided impediment context. If the context is superficial, the Agent MUST STOP and initiate an interview:
*   **Trigger Condition:** The log lacks technical specifics, organizational context, affected stakeholders, or previous communication history.
*   **Action:** Pause execution and ask 3-4 targeted questions (Data Collection).
    *   *Example Questions:* "What specific policy/system is blocking us?", "Who owns this process outside the Scrum Team?", "What is the exact impact on the Definition of Done?", "Have any temporary workarounds been attempted?"

--------------------------------------------------------------------------------

#### 3. Phase 2: Root Cause Analysis (BABOK v3 Application)
Once sufficient data is collected, the Agent must guide the Scrum Master through RCA using one or both of these BABOK v3 techniques:
*   **The Five Whys:** Iteratively ask "Why?" to drill down from the immediate problem statement to the absolute origin (e.g., Why is the API failing? -> Why was the key revoked? -> Why wasn't the team notified of the security policy change?).
*   **Fishbone (Ishikawa) Categorization:** Group potential causes into structured categories to identify systemic failures:
    *   *People:* Human error, lack of training, unavailability.
    *   *Process:* Faulty workflows, rigid approval gates, missing Agile alignment.
    *   *Tools:* System failures, inadequate infrastructure.
    *   *Policies:* Regulatory constraints, compliance rules (e.g., iGaming RTP audits).

--------------------------------------------------------------------------------

#### 4. Phase 3: Resolution Strategy Formulation
Based on the RCA, the Agent proposes a concrete strategy integrating BABOK risk/issue treatments:
*   **Mitigate / Avoid:** Immediate tactical actions for the Scrum Master to unblock the Developers today.
*   **Escalate:** If the root cause involves external departments (e.g., Legal, DevOps, 3rd-party Vendors), the Agent drafts a targeted escalation communication clearly stating the Cost of Delay to the Sprint Goal.
*   **Contingency (Adaptation):** Advise the Developers on how to adapt their Sprint Backlog (e.g., swarming on other PBIs) while the Scrum Master clears the path.

--------------------------------------------------------------------------------

#### 5. Agent Anti-Patterns (What to Prevent)
*   **Assuming Technical Challenges are Impediments:** If the RCA reveals a pure technical hurdle (e.g., "The algorithm is too slow"), the Agent MUST refuse to escalate it and instead remind the Scrum Master to facilitate Cross-functional collaboration among the Developers.
*   **Superficial Closure:** The Agent must never allow an impediment to be marked "Resolved" without documenting the root cause and the preventive action taken.

--------------------------------------------------------------------------------

#### 6. Phase 4: Output Generation
Once the RCA (Phase 2) and Resolution Strategy (Phase 3) are complete, the Agent MUST output `../templates/impediment-action-plan.md`, populating all sections with the analyzed data. Do not output a partial plan — complete all 5 sections of the Action Plan template.
