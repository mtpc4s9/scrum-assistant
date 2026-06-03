---
artifact_name: Definition of Ready (DoR) Checklist
purpose: Provide a highly visible, printable checklist to ensure Product Backlog Items have just enough detail, size, and clarity for the Developers to confidently pull them into a Sprint — without transforming this guideline into a rigid Waterfall phase-gate.
---

### 🤖 AGENT DIRECTIVE (HIDDEN FROM FINAL OUTPUT)
When generating the Definition of Ready, the AI Agent MUST adhere to these rules:
1.  **Reference First:** Load and apply [references/definition-of-ready-guide.md](references/definition-of-ready-guide.md) before populating this template.
2.  **Format:** Output a clean, docx-friendly checklist using standard Markdown checkboxes (`- [ ]`). Avoid complex nested tables.
3.  **Core Criteria:** Base the checklist on the 4 minimum needs of "Ready" (Small enough, Sized/Estimated, Just enough detail with Acceptance Criteria, Understood by Developers).
4.  **Domain Injection:** If `input-readiness.md` reveals iGaming or specific tech constraints (e.g., Kambi API, RNG logic, Decree 06 limits), inject 1-2 domain-specific checkpoints under the "Regulatory & Integration Pre-Conditions" section.
5.  **Anti-Contract Warning:** Explicitly include a disclaimer that the DoR is a collaborative guideline, not an inflexible Waterfall gate.
6.  **Socratic Closing Prompt:** Append the closing facilitation question after the checklist.
7.  **Output Generation:** Output ONLY the section below this line.

---

# ☑️ DEFINITION OF READY (DoR) — TEAM CHECKLIST

**⚠️ THE "READINESS MINDSET" DISCLAIMER:**
*This checklist is a collaborative tool to help the team plan with confidence. The Definition of Ready is a **mindset**, not a rigid contract or a Waterfall phase-gate. If a Product Backlog Item is not perfectly complete on every criterion, but the **Developers** and **Product Owner** share a clear mutual understanding and the team is confident it can be delivered within the Sprint, the item MAY still be pulled into the Sprint. Customer collaboration always takes precedence over adherence to a checklist.*

---

### 1. 🎯 VALUE & CLARITY
- [ ] The item is expressed in a clear format (e.g., a User Story: *As a [role], I want [capability], so that [benefit]*).
- [ ] The business value or purpose of the item has been explicitly articulated by the **Product Owner**.
- [ ] The **Developers** understand *why* this item is needed and how it contributes to the **Product Goal**.

### 2. 📋 ACCEPTANCE CRITERIA
- [ ] Specific, clear, and testable Acceptance Criteria exist for this item.
- [ ] (Recommended) Acceptance Criteria are written in BDD/Gherkin format (*Given… When… Then…*) for clarity.
- [ ] The team has discussed and knows exactly how to demonstrate this item at the **Sprint Review**.

### 3. 📏 SIZE & ESTIMATION
- [ ] The item has been estimated by the **Developers** who will perform the work (not by management or external parties).
- [ ] The item is small enough to be comfortably completed within a single **Sprint**. If oversized (Epic-level), it has already been split. *(Ref: `../shared/story-splitting/SKILL.md`)*

### 4. 🔗 DEPENDENCIES & RISKS
- [ ] All dependencies on other teams, external systems, or third-party services (e.g., awaiting Vendor API keys, pending Legal approval) have been identified.
- [ ] Identified dependencies are either resolved, or a concrete coordination plan is in place to prevent them from blocking the team mid-Sprint.
- [ ] No critical open questions remain unanswered regarding business logic or technical architecture.

### 5. 🛠️ TEAM CAPABILITIES
- [ ] The cross-functional **Developers** team has the required skills, tools, and access needed to turn this item into a **Done** Increment.

### 6. ⚖️ REGULATORY & INTEGRATION PRE-CONDITIONS *(iGaming — Inject if applicable)*
- [ ] *(If applicable)* Regulatory impact (e.g., PAGCOR caps, Decree 06 transaction limits) has been assessed and pre-cleared by the Legal/Compliance team.
- [ ] *(If applicable)* Third-party API contracts (e.g., Kambi sandbox access, Pragmatic Play RTP specs, MoMo gateway credentials) are confirmed and available.
- [ ] *(If applicable)* The underlying mathematical model (RTP, prize tiers, payout logic) has been reviewed and approved before Developers begin implementation.

---

*> **Socratic Closing Prompt (Agent Appends This):** "This is a baseline Definition of Ready. Which of these criteria do your Developers feel are truly essential for confident Sprint commitment? Are there any domain-specific pre-conditions we have not yet captured?"*
