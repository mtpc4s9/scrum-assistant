---
artifact_name: Definition of Done (DoD) Reference Guide
purpose: Provide the AI Agent with the theoretical boundaries, empirical standards, and execution directives required to draft and refine a robust Definition of Done for a Scrum Team, particularly in the highly regulated iGaming domain.
---

### Definition of Done (DoD) Reference Guide
This document serves as the hidden cognitive framework for the Scrum Assistant during **Step 6 - Standards Setup**. It ensures the generated DoD acts as a rigorous commitment to quality and transparency, rather than a superficial checklist.

--------------------------------------------------------------------------------

#### 1. Core Principles of "Done" (The SG2020 Standard)
*   **The Birth of an Increment:** The Definition of Done is a formal description of the state of the Increment when it meets the quality measures required for the product. The moment a Product Backlog item meets the DoD, an Increment is born.
*   **Commitment, Not a Guideline:** The Developers are required to conform to the Definition of Done. It creates transparency by providing everyone with a shared understanding of what work was completed.
*   **No "Done-Done" Trap:** The Agent MUST reject concepts like "Done-Done" or "Partially Done". In Scrum, if an item does not meet the DoD, it cannot be released or even presented at the Sprint Review. It returns to the Product Backlog.

--------------------------------------------------------------------------------

#### 2. DoD vs. Acceptance Criteria (Agent Logic)
The Agent must clearly separate these two concepts when advising the Scrum Team:
*   **Definition of Done (Global):** Applies to the entire Increment. These are universal quality standards (e.g., "Code is peer-reviewed," "Automated regression tests pass," "iGaming compliance checklist validated").
*   **Acceptance Criteria (Local):** Item-specific conditions of satisfaction provided by the Product Owner (e.g., "The user can deposit via MoMo wallet," "The system accepts Visa cards"). 
*   **Rule:** A Product Backlog item is only complete when it meets BOTH its specific Acceptance Criteria AND the global Definition of Done.

--------------------------------------------------------------------------------

#### 3. The Evolution of Done (Empiricism)
*   **Starting Point:** For newly formed teams or legacy systems lacking automation, the initial DoD might be a "bare-minimum" state (e.g., manual regression testing) to ensure the team can actually deliver an Increment in the first Sprint.
*   **Expanding Stringency:** As the Scrum Team matures, their DoD must expand to include more stringent criteria for higher quality (e.g., introducing CI/CD pipelines, automated security scanning). 
*   **The Avoidance of "Scrummerfall":** The Agent must strongly discourage DoDs that push testing or integration to a "future Sprint" or "Hardening phase." All work required to make the Increment potentially shippable must happen inside the Sprint.

--------------------------------------------------------------------------------

#### 4. iGaming Domain Overlay (Quality & Compliance)
When drafting the DoD, the Agent MUST inject dual-layer quality checks for the iGaming context:
1.  **Technical Quality:** Code coverage, no known Sev-1/Sev-2 defects, load-tested for concurrency (PAM/Ledger interactions).
2.  **Domain/Regulatory Quality:** RNG algorithms certified, RTP (Return to Player) mathematical accuracy validated, and KYC/AML checks functional as per local decree boundaries (e.g., PAGCOR or Decree 06 compliance).

--------------------------------------------------------------------------------

#### 5. Agent Execution Directives
*   **Drafting:** Generate the DoD checklist by categorizing items into: Code/Engineering, Testing/Quality, Deployment/Integration, and Compliance/Documentation.
*   **Socratic Validation:** If the user inputs an unrealistic team capability (e.g., "We have no QA automation" but wants "100% automated testing" in the DoD), the Agent MUST pause and use Socratic questioning: *"I notice your team currently lacks automation tools. Setting 100% automation in the initial DoD might prevent the team from delivering a 'Done' Increment in Sprint 1. Should we start with a manual testing baseline and plan an improvement backlog to evolve this later?"*
*   **Disclaimer:** Always prepend the generated DoD with a warning that it is a baseline draft. The entire Scrum Team must collaboratively agree upon and commit to the final version.
