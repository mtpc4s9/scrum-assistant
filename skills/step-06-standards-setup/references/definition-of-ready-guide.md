---
artifact_name: Definition of Ready (DoR) Reference Guide
purpose: Provide the AI Agent with the theoretical boundaries, empirical standards, and execution directives required to draft and validate a practical Definition of Ready for a Scrum Team — preventing it from becoming a rigid Waterfall phase-gate.
---

### Definition of Ready (DoR) Reference Guide

This document serves as the hidden cognitive framework for the Scrum Assistant during **Step 6 — Standards Setup**. It ensures the generated DoR acts as a shared understanding tool and a collaborative readiness mindset, never as a bureaucratic contract.

---

#### 1. Core Principles of "Ready" (The SG2020 Standard)

*   **The Readiness Mindset — Not a Contract:** The Definition of Ready is a shared understanding between the Product Owner and the Developers about the minimum clarity needed for a Product Backlog Item (PBI) to be confidently pulled into a Sprint. It is guidance, not a gate.
*   **The Danger of Rigid DoR:** A DoR applied as a mandatory checklist that blocks all "imperfect" items from entering a Sprint creates a Waterfall gate in disguise ("Mini Waterfall"). Developers and the Product Owner must retain the judgement to pull in items when mutual understanding exists, even if not every criterion is formally ticked.
*   **Agile Manifesto Alignment:** Customer collaboration and responding to change take priority over following a checklist. The DoR must enable agility, not restrict it.

---

#### 2. The Four Minimum Needs of "Ready" (Practitioner Baseline)

When drafting a DoR, the Agent must verify coverage of these four foundational needs:

1.  **Small Enough to Complete in One Sprint:** The item must be decomposable enough that the Developers can deliver it within a single Sprint timebox. If not, Story Splitting is required before it can be considered "Ready". *(Ref: `../shared/story-splitting/SKILL.md`)*
2.  **Sized / Estimated:** The Developers who will do the work must have estimated the item using an agreed method (e.g., Story Points, T-shirt sizing, or right-sizing). Estimates made by others (e.g., management) are not valid.
3.  **Just Enough Detail / Acceptance Criteria Present:** The item must have clear, testable Acceptance Criteria, written at a level that tells the Developers exactly when the item is "done enough" for the Product Owner to verify.
4.  **Understood by the Developers:** At least the core Developers understand the business context ("Why"), the technical approach ("How"), and the expected behaviour ("What"). Any blocking open questions must be resolved before sprint pull-in.

---

#### 3. DoR vs. Definition of Done (Agent Logic — Prevent Conflation)

The Agent must clearly distinguish these two artefacts when advising the Scrum Team:

| Dimension | Definition of Ready (DoR) | Definition of Done (DoD) |
| :--- | :--- | :--- |
| **Scope** | Applied to individual Product Backlog Items | Applied to the entire Increment |
| **Owned By** | Product Owner (maintains) + Developers (verify) | Developers (commit to) + Scrum Team (agrees) |
| **Question Answered** | "Is this item clear enough to start?" | "Is this Increment complete enough to release?" |
| **When Applied** | During Sprint Planning (pull-in decision) | During Sprint (continuous) and Sprint Review (gate) |
| **Risk of Misuse** | Becomes a Waterfall phase-gate | Becomes a "Done-Done" trap or ignored entirely |

---

#### 4. iGaming Domain Overlay (Compliance Pre-Conditions)

For iGaming Product Backlog Items, the Agent MUST consider injecting the following readiness conditions where relevant:

*   **Regulatory Pre-Clearance:** For features touching transaction limits (e.g., PAGCOR caps, Decree 06 deposit/withdrawal rules), the Legal/Compliance team must have assessed impact *before* the item is pulled into Sprint.
*   **Third-Party API Contracts Confirmed:** For items dependent on external integrations (e.g., Kambi Sportsbook API, Pragmatic Play RTP specs, MoMo payment gateway), the API contract, sandbox credentials, and connectivity must be confirmed *before* the Sprint starts.
*   **Mathematical Model Pre-Validated:** For lottery or casino game features, the underlying mathematical model (prize tiers, RTP calculation, payout logic) must be reviewed and approved by the Product Owner or a domain expert *before* Developers begin implementation.

---

#### 5. Agent Execution Directives

*   **Format:** Output a clean, docx-friendly checklist using standard Markdown checkboxes (`- [ ]`). Avoid complex nested tables in the final output.
*   **Grouping:** Organise DoR items into logical sections: Value & Clarity, Acceptance Criteria, Size & Estimation, Dependencies & Risks, Team Capabilities.
*   **Domain Injection:** If `input-readiness.md` (C4) reveals iGaming regulatory dependencies, inject 1-2 domain-specific checkpoints under a "Regulatory & Integration Pre-Conditions" section.
*   **Anti-Contract Warning:** Explicitly include a disclaimer that the DoR is a collaborative guideline, not an inflexible contract. Customer collaboration over contract negotiation always applies.
*   **Socratic Closing Prompt:** After generating the DoR, append: *"This is a baseline Definition of Ready. Which of these criteria do your Developers feel are truly essential for confident sprint commitment, and are there any domain-specific pre-conditions we have missed?"*
