---
artifact_name: Input Readiness Checklist — Step 06
purpose: Act as a quality gate to ensure all organizational, technical, and team-specific constraints are captured before generating drafts for the Definition of Ready, Definition of Done, and Team Norms.
---

# Input Readiness Checklist — Step 06: Standards Setup

The Scrum Assistant uses this checklist as a quality gate before drafting foundational Scrum Team standards. All 4 criteria below must be marked as **MET** before proceeding to artifact generation. 

If any criterion is missing, the assistant will suspend execution and prompt the user to supply the necessary context to avoid generating unrealistic or misaligned standards.

| ID | Input Criterion | Verification Question | Status |
| :--- | :--- | :--- | :--- |
| **C1** | **Team Composition & Capabilities** | Are the composition, size, and cross-functional skills (e.g., QA, Backend, UX, DB) of the Developers clearly identified? | [ ] MET <br> [ ] NOT MET |
| **C2** | **Operational Environment** | Is the working environment defined (e.g., colocated vs. distributed, time zones, core overlapping hours)? | [ ] MET <br> [ ] NOT MET |
| **C3** | **Technical & Automation Readiness** | Are the available engineering practices and tooling constraints (e.g., CI/CD pipeline status, automated testing capabilities) clearly stated? | [ ] MET <br> [ ] NOT MET |
| **C4** | **Regulatory & Domain Quality Baselines** | Are mandatory iGaming compliance checks (e.g., RTP calculation audits, KYC validation steps) identified for inclusion in the overall quality standard? | [ ] MET <br> [ ] NOT MET |

---

## Decision Logic & Rules

*   **IF any criterion is [ ] NOT MET:**
    *   **Action:** Suspend draft generation. Prompt the user to provide the missing organizational, technical, or team-level context. 
    *   *Prompt Example:* "To ensure the Definition of Done and Team Norms are realistic and applicable, please provide the missing information regarding [Criterion Name]. Generating standards without this context violates Empirical Process Control."
*   **IF all criteria are [x] MET:**
    *   **Action:** Proceed to the artifact generation phase. Draft the requested standards (Definition of Done, Definition of Ready, Team Norms) and prominently display a disclaimer that these are baseline drafts requiring collaborative refinement and consensus from the entire Scrum Team.
