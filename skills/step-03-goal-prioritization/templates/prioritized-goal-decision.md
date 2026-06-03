---
artifact_name: Prioritized Goal Decision
purpose: Formally document the selection of the single 1st Product Goal from multiple candidates, providing transparent economic and regulatory rationale to the Scrum Team and Stakeholders.
---

### 🤖 AGENT DIRECTIVE (HIDDEN FROM FINAL OUTPUT)
When the user requests the Prioritized Goal Decision document, execute the following synthesis steps:
1.  **Enforce the Rule of One:** Ensure only ONE candidate goal is selected as the active Product Goal. All other candidates MUST be categorized as Deferred.
2.  **Synthesize the Rationale:** Summarize the findings from the `cost-of-delay-guide.md`, `wsjf-guide.md`, and `igaming-context.md` evaluations. State explicitly WHY the winning goal was chosen (e.g., "High Cost of Delay due to upcoming AML compliance deadline" or "Highest WSJF score maximizing early revenue").
3.  **Output Generation:** Output ONLY the "PRIORITIZED GOAL DECISION" section below in a clean, professional Markdown format.

---

### 🏆 PRIORITIZED GOAL DECISION

**📅 Date of Decision:** *[Agent: Insert Current Date]*
**👤 Decision Maker:** Product Owner

#### 1. THE SELECTED 1st PRODUCT GOAL
*[Agent: State the single winning Product Goal clearly and concisely. This becomes the immediate commitment for the Product Backlog.]*

#### 2. STRATEGIC & ECONOMIC RATIONALE
*This goal was selected to maximize lifecycle profits and mitigate critical risks based on the following analysis:*

*   **Primary Driver:** *[Agent: State whether it was Cost of Delay, WSJF, Regulatory Compliance, or a Vendor Dependency]*
*   **Cost of Delay Profile:** *[Agent: Identify the CoD profile, e.g., Fixed Date, Must Do Now, Linear]*
*   **Analysis Summary:**
    *[Agent: Provide a 2-3 sentence explanation. Example: "With the MGA regulatory deadline approaching on Oct 1st, failing to integrate the KYC provider carries a 'Fixed Date' Cost of Delay that threatens our entire operating license. This extreme risk supersedes the linear revenue gains of other candidate goals."]*

#### 3. DEFERRED GOALS (ADDED TO PORTFOLIO / VISION BACKLOG)
*In adherence to the Scrum framework, a Scrum Team focuses on one Product Goal at a time. The following candidate goals are valid and valuable, but are formally deferred until the 1st Product Goal is fulfilled or abandoned.*

| Deferred Goal | Estimated WSJF / CoD Impact | Deferral Reason |
| :--- | :--- | :--- |
| *[Agent: Insert Candidate Goal B]* | *[Agent: E.g., Linear CoD, Lower WSJF]* | *[Agent: E.g., Revenue impact is strong but less critical than license suspension.]* |
| *[Agent: Insert Candidate Goal C]* | *[Agent: E.g., Intangible CoD]* | *[Agent: E.g., High technical risk, needs vendor SDK to mature first.]* |

#### 4. NEXT STEP
Proceed to **Step 4: Product Backlog Creation** to decompose this active Product Goal into smaller, actionable Product Backlog Items (Epics/Features) through Story Mapping.
