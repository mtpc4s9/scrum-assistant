---
artifact_name: Impact Map
purpose: Visually and logically map the Product Goal to the stakeholders, their desired behavior changes, and the specific deliverables required, ensuring all features are value-driven.
---

### 🤖 AGENT DIRECTIVE (HIDDEN FROM FINAL OUTPUT)
When the user requests an Impact Map, execute the following reasoning steps based on Chapter 7 of 'The Professional Product Owner':
1. **WHY (The Goal):** Use the established Product Goal.
2. **WHO (The Actors):** Identify the key Stakeholders (users, decision-makers, or even systems) whose behavior needs to change to achieve the goal.
3. **HOW (The Impacts):** Determine how the actors' behavior needs to change (e.g., "Invite friends to play," "Complete KYC faster," "Trust the payout system").
4. **WHAT (The Deliverables):** Brainstorm high-level features or epics that will enable these behavior changes.
5. **iGaming Context Overlay:** Ensure deliverables account for regulatory and technical risks (e.g., RNG transparency, anti-money laundering).
6. **Output Generation:** Output ONLY the "IMPACT MAP" section below using a structured markdown representation (lists or tables).

---

### 🗺️ IMPACT MAP

**🎯 WHY (PRODUCT GOAL)**
> *[Agent: Insert the overarching Product Goal here]*

| 👤 WHO (Actor / Stakeholder) | 🔄 HOW (Behavior Change / Impact) | 📦 WHAT (Deliverable / Epic) |
| :--- | :--- | :--- |
| *[Agent: E.g., Casual Player]* | *[Agent: E.g., Wants to share the cost of a lottery ticket with friends]* | **Epic 1:** *[E.g., Syndicate Ticket Purchasing Engine]* <br> **Epic 2:** *[E.g., Social Media Invitation Link]* |
| *[Agent: E.g., Compliance Officer]* | *[Agent: E.g., Needs to verify user identity seamlessly without dropping conversion]* | **Epic 3:** *[E.g., Automated KYC API Integration]* |
| *[Agent: E.g., VIP Player]* | *[Agent: E.g., Wants instant, verifiable payouts to build trust]* | **Epic 4:** *[E.g., Smart-Contract based Crypto Withdrawal]* |

**🔍 HYPOTHESIS TO TEST:**
*[Agent: Write a concluding statement. Example: "We believe that by building [WHAT], we will create [HOW] for [WHO], which will ultimately achieve our goal of [WHY]. We will validate this by inspecting the Increment in upcoming Sprints."]*
