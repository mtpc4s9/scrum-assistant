# Input Readiness Checklist — Step 02: Goal Setting

The Scrum Assistant uses this checklist as a quality gate before applying Impact Mapping logic (Phase 2) and generating output artifacts (Phase 3).

All 4 criteria below must be marked as **MET** before proceeding. If any criterion is missing or focused purely on features (WHAT) instead of outcomes (WHY), the assistant will trigger the `shared/product-discovery` workflow.

| ID | Input Criterion | Verification Question | Status |
| :--- | :--- | :--- | :--- |
| **C1** | **Product Vision Alignment** | Is there a valid Product Vision Statement (from Step 01) acting as the North Star for this new goal? | [ ] MET <br> [ ] NOT MET |
| **C2** | **The WHY (Business Problem/Opportunity)** | Has the core business problem or opportunity been clearly articulated, rather than just a list of requested features? | [ ] MET <br> [ ] NOT MET |
| **C3** | **The WHO (Target Stakeholders)** | Are the key Stakeholders (users, customers, regulators) whose behaviors need to change identified? | [ ] MET <br> [ ] NOT MET |
| **C4** | **Measurability & EBM (Success Criteria)** | Are there quantifiable metrics or Evidence-Based Management (EBM) indicators (e.g., Usage Index, Innovation Rate, Time to Market) proposed to validate success? | [ ] MET <br> [ ] NOT MET |

---

## Decision Logic & Rules

*   **IF the user inputs features (The WHAT) instead of objectives (The WHY):**
    *   **Action:** Mark C2 as [ ] NOT MET. Use Socratic questioning to redirect the user: *"You mentioned building [Feature]. What is the ultimate business objective (WHY) we are trying to achieve with this feature?"*
*   **IF any criterion is [ ] NOT MET:**
    *   **Action:** Suspend generation of the Product Goal and Impact Map. Call the [shared/product-discovery](../../shared/product-discovery/SKILL.md) skill to interview the user and gather missing details.
    *   **Rule:** Repeat the discovery cycle until all 4 checklist items are verified as MET.
*   **IF all criteria are [x] MET:**
    *   **Action:** Proceed directly to Phase 2 (Domain Context Overlay & Output Generation).
