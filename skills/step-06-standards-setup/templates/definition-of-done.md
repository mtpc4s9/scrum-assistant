---
artifact_name: Definition of Done (DoD) Checklist
purpose: Define the global quality standards that every Increment must meet to be considered potentially releasable, ensuring transparency and preventing the accrual of Technical Debt.
---

### 🤖 AGENT DIRECTIVE (HIDDEN FROM FINAL OUTPUT)
When generating the Definition of Done (DoD), the AI Agent MUST adhere to these rules:
1.  **Reference First:** Load and apply [references/definition-of-done-guide.md](references/definition-of-done-guide.md) before populating this template.
2.  **Format:** Output a clean, docx-friendly checklist using standard Markdown checkboxes (`- [ ]`).
3.  **Global vs. Local:** Ensure the DoD contains ONLY global quality metrics that apply to the entire Increment. Do not include item-specific Acceptance Criteria.
4.  **Anti-Scrummerfall Warning:** Explicitly reject the concept of "Done-Done" or "Hardening Sprints." Work is either "Done" and releasable, or "Not Done" and returned to the Product Backlog.
5.  **Domain Injection (iGaming):** Always include a "Regulatory & Compliance" section. If the context involves iGaming, inject checks for RNG certification, RTP validation, and KYC/AML guidelines.
6.  **Socratic Closing Prompt:** Append the closing facilitation question after the checklist body.
7.  **Output Generation:** Output ONLY the section below this line.

---

# ☑️ DEFINITION OF DONE (DoD) - TEAM COMMITMENT

**⚠️ THE "EVOLUTION OF DONE" & ANTI-COMPROMISE PLEDGE:**
*This Definition of Done is a formal commitment by the **Developers**. It applies to the entire **Increment**. There is no such thing as "Done-Done" or "Partially Done". If a Product Backlog item does not meet EVERY checked item below, it cannot be presented at the **Sprint Review** and must return to the **Product Backlog**.*
*Note: As the Scrum Team matures and automation improves, this DoD will evolve to include more stringent criteria.*

### 1. 🛠️ TECHNICAL & ENGINEERING QUALITY
- [ ] Code is written according to the agreed-upon team coding standards and style guides.
- [ ] Code has been peer-reviewed (or Pair Programmed) by at least one other Developer.
- [ ] Unit tests are written and pass (maintaining a minimum agreed test coverage threshold, e.g., >80%).
- [ ] Code is successfully integrated into the main branch (Continuous Integration build is GREEN).
- [ ] No known Severity 1 or Severity 2 (Critical/High) defects exist in the newly integrated code.

### 2. 🧪 TESTING & VALIDATION
- [ ] Item-specific Acceptance Criteria (Local quality) have been fully met and verified by the **Product Owner**.
- [ ] **Product Owner Verification:** The Product Owner has reviewed and verified the completed work item prior to the Sprint Review.
- [ ] Automated regression tests have been executed and passed without breaking existing functionality.
- [ ] Manual exploratory testing has been conducted for the primary user flows.
- [ ] The feature performs within acceptable response time limits (Performance/Load testing baseline met).
- [ ] The user interface (UI) is responsive and renders correctly on all supported platforms/browsers.

### 3. ⚖️ DOMAIN & REGULATORY COMPLIANCE (iGaming Focus)
- [ ] Mathematical models (e.g., Return to Player - RTP, Payout tables) are validated and mathematically accurate.
- [ ] Random Number Generator (RNG) logic passes automated probability and fairness checks.
- [ ] Transaction boundaries (e.g., KYC validation, AML limits, PAGCOR/Decree 06 caps) are strictly enforced and logged.
- [ ] Security checks (e.g., API endpoint authentication, wallet pessimistic locking) are verified.

### 4. 🚀 DEPLOYMENT & DOCUMENTATION
- [ ] The code is successfully deployed to the Staging/Pre-Production environment.
- [ ] Release notes and changelogs have been updated for stakeholders.
- [ ] Internal support guides, API documentation, or technical Wiki pages have been updated to reflect the changes.
- [ ] The **Increment** is in a usable state, such that the **Product Owner** could choose to release it to production immediately.

---

*> **Socratic Closing Prompt (Agent Appends This):** "This is a baseline Definition of Done calibrated to your team's current engineering maturity and the iGaming domain context. Which criteria do your Developers feel are achievable from Sprint 1? Are there any criteria that should be deferred to an Improvement Backlog item as the team's automation capabilities grow?"*
