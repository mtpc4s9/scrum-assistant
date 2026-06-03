---
artifact_name: DEEP Quality Gate Checklist
purpose: Act as a final audit mechanism to ensure the generated High-Level Product Backlog adheres to the DEEP criteria before finalizing Step 04.
---

# Output Quality Gate — DEEP Standard Audit

Before presenting the generated `high-level-product-backlog.md` to the user, the Scrum Assistant MUST silently audit the artifact against the DEEP criteria (coined by Roman Pichler & Mike Cohn). 

If any criterion fails, the Assistant must pause, explain the failure using Socratic questioning, and ask the user for additional input to fix the Product Backlog.

| Letter | Criterion | Verification Rule for AI Agent | Status |
| :---: | :--- | :--- | :--- |
| **D** | **Detailed appropriately** | Are the items at the top of the backlog (Release 1.0) broken down into smaller Epics/Features compared to the items at the bottom? | [ ] PASS <br> [ ] FAIL |
| **E** | **Emergent** | Is there a disclaimer indicating this backlog is a living artifact and will evolve through Empiricism? | [ ] PASS <br> [ ] FAIL |
| **E** | **Estimated** | Does every Epic/Feature have a relative size estimate (e.g., T-Shirt sizing: S, M, L, XL)? | [ ] PASS <br> [ ] FAIL |
| **P** | **Prioritized** | Is the list strictly ordered top-to-bottom based on the economic formula (Value + Risk / Size) and dependencies? | [ ] PASS <br> [ ] FAIL |

---

## Agent Remediation Directives

*   **If D fails:** "I noticed the Epics at the top are still very large and vague. To ensure the Developers can understand them, should we use the Story Splitting technique to break the top 2 items down further?"
*   **If E (Estimated) fails:** "The backlog lacks size estimates. Without estimates, the Product Owner cannot forecast the release. Could you provide a rough T-shirt size (S, M, L, XL) for the top 5 items?"
*   **If P fails:** "The items seem to be randomly listed. Based on our Impact Map and iGaming regulatory risks, which of these items delivers the most critical value to the Product Goal to be placed at rank #1?"
