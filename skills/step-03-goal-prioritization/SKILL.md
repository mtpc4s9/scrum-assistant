---
name: step-03-goal-prioritization
description: Execute Step 3 - Goal Prioritization by evaluating multiple candidate Product Goals using economic filters (Cost of Delay, WSJF, MoSCoW) and iGaming constraints to define the single 1st Product Goal.
---

### Step 03: Goal Prioritization
This skill controls the execution of the **Step 3 - Goal Prioritization** workflow. The objective is to help the Product Owner critically evaluate multiple potential Product Goals and confidently select the single most valuable goal to pursue first, ensuring alignment with agile economics and domain constraints.

--------------------------------------------------------------------------------

#### 0. Backbone & Phase Context
*   **Backbone Step:** Step 3 — Goal Prioritization
*   **Scrum Flow Phase:** Phase 0 — Initiative
*   **Primary Owner:** Product Owner (PO)
*   **Scrum Master Role:** Facilitate the decision-making process; protect Empiricism by ensuring only ONE Product Goal is selected as the commitment for the Product Backlog.
*   **Target Output Deliverables:**
    *   [A] Prioritized Goal Decision Document

--------------------------------------------------------------------------------

#### 1. Phase 1 — Input Quality Gate & Discovery
**Trigger Keywords:** "prioritize goals", "chọn goal", "ưu tiên mục tiêu", "đánh giá product goal", "step 3 prioritization".

**Agent Directive (Verification):**
Before prioritizing, the Agent MUST verify that the user has provided:
1. **At least two candidate Product Goals** (from Step 02). If only one goal exists, prioritization is unnecessary—route directly to Step 4 (Backlog Creation).
2. **High-level value or risk context** for each goal.

*   **IF inputs are missing:** 
    *   **ACTION:** Suspend execution. Use Socratic questioning to ask the user to provide the candidate goals and their associated business impacts.
*   **IF inputs are MET:** Proceed to Phase 2.

--------------------------------------------------------------------------------

#### 2. Phase 2 — Domain Context & Economic Overlay (Optional Domain Scan)
**Agent Directive (Contextualization & Analysis):**
The Agent MUST check if the project is in the iGaming or Online Lottery domain. Ask the user: *"Is this project in the iGaming or Online Lottery domain? (yes/no)"* (or detect from project context).

*   **Filter 1: Domain Constraints (reference/igaming-context.md - Applied only if domain is iGaming/Lottery):**
    *   Check for strict regulatory compliance deadlines (e.g., AML laws, PAGCOR mandates). *Rule:* Compliance deadlines often carry a massive Cost of Delay (fixed-date impact) and usually trump new revenue features.
    *   Check for 3rd-party vendor integration readiness (e.g., Kambi, Pragmatic Play).
*   **Filter 2: Economic Prioritization (references/cost-of-delay-guide.md and references/wsjf-guide.md - Applied for all domains):**
    *   Apply *Cost of Delay (CoD)*: Ask internally, "What is the financial or legal cost per month of NOT doing this goal?"
    *   Apply *Weighted Shortest Job First (WSJF)*: If sizes are known via T-shirt sizing, rank by CoD / Duration.

--------------------------------------------------------------------------------

#### 3. Phase 3 — Output Generation
**Agent Directive (Execution):**
Once the internal analysis is complete, present the findings to the user and generate the final output.

*   **Rule of One:** The Agent MUST firmly state that according to the 2020 Scrum Guide, a Scrum Team can only commit to ONE Product Goal at a time. The team must fulfill (or abandon) this objective before taking on the next.
*   **Action:** Load `templates/prioritized-goal-decision.md`. Populate the template with the single winning 1st Product Goal, explicitly detailing the rationale (e.g., higher Cost of Delay, regulatory mandate) and documenting the deferred goals.