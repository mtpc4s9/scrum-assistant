---
artifact_name: High-Level Product Backlog
purpose: Provide an emergent, ordered list of Epics and Features needed to achieve the Product Goal, ordered by value, risk, and size, strictly adhering to the DEEP standard.
---

### 🤖 AGENT DIRECTIVE (HIDDEN FROM FINAL OUTPUT)
When the user requests a High-Level Product Backlog, execute the following reasoning steps:
1. **Extract from Tree:** Take the Epics and Must-Have stories generated in the Epic/Feature Tree.
2. **Draft Initial List:** Create a rough, unformatted list of these items internally.
3. **Calculate Order Rank:** Internally estimate a relative Business Value (1-20), Risk (1-10), and Size (1-13 Fibonacci or T-Shirt). Use the formula: `(Business Value + Risk) / Size = Order Rank`.
4. **Apply DEEP Quality Gate (Self-Correction Loop):** BEFORE outputting, silently run your drafted list through `../step-04-deep-quality-gate.md`. 
   - *Detailed appropriately:* Are the top items (Release 1.0) smaller/clearer than the bottom items?
   - *Emergent:* Is the empirical disclaimer included?
   - *Estimated:* Does every item have a size estimate?
   - *Prioritized:* Is the list strictly ordered top-to-bottom by the calculated Order Rank?
   - *Action:* If your draft fails ANY of these DEEP criteria, self-correct and regenerate the internal list until it passes all checks perfectly.
5. **Output Generation:** Output ONLY the "HIGH-LEVEL PRODUCT BACKLOG" section below using the finalized, DEEP-compliant data. Do not show the raw math, the draft, or the audit process.

---

### 📋 HIGH-LEVEL PRODUCT BACKLOG

**🎯 ALIGNMENT: 1st PRODUCT GOAL:** 
*[Agent: Insert the prioritized Product Goal here]*

*Note: This is an emergent artifact. It is the single source of work for the Scrum Team. Order and sizing will be continuously refined by the Product Owner and Developers.*

| Order | Epic / Feature Name | Description (Value Proposition) | Est. Size | Risk Level |
| :---: | :--- | :--- | :---: | :---: |
| 1 | *[Agent: E.g., Core Wallet Integration]* | *[Agent: Brief description of what it does and why]* | *[T-Shirt Size]* | *[High/Med/Low]* |
| 2 | *[Agent: Epic 2]* | *[Agent: Brief description]* | *[Size]* | *[Risk]* |
| 3 | *[Agent: Epic 3]* | *[Agent: Brief description]* | *[Size]* | *[Risk]* |
| 4 | *[Agent: Regulatory/Compliance Epic]* | *[Agent: Brief description]* | *[Size]* | *[Risk]* |

**⚠️ DEPENDENCIES & NOTES:**
*   *[Agent: List 1-2 critical dependencies that the Scrum Team must address, e.g., "Item 1 requires Vendor API credentials before it meets the Definition of Ready."]*
