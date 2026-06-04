---
artifact_name: Input Readiness Checklist — Step 07
purpose: Act as a strict quality gate before initiating Sprint Planning calculations and artifact generation. Ensures empirical process control by verifying that the Scrum Team has all necessary inputs (Ready PBIs, Capacity, Velocity, and an Initial Sprint Goal).
---

# Input Readiness Checklist — Step 07: Sprint Planning

The Scrum Assistant MUST use this checklist as a quality gate before generating any Sprint Planning artifacts (`sprint-planning.md` or presentation decks). All 4 criteria below MUST be marked as **MET** before proceeding. 

If any criterion is missing, the Assistant MUST suspend execution and prompt the user to supply the necessary context to prevent "Garbage In, Garbage Out" planning.

| ID | Input Criterion | Verification Question | Status |
| :--- | :--- | :--- | :--- |
| **C1** | **Refined Product Backlog (DoR Met)** | Are the topmost Product Backlog Items (PBIs) refined, sized (estimated), and do they meet the agreed-upon Definition of Ready (DoR)? | [ ] MET <br> [ ] NOT MET |
| **C2** | **Team Capacity & Capabilities** | Is the specific availability (e.g., public holidays, personal time off, training days) of the Developers for this exact Sprint clearly defined? | [ ] MET <br> [ ] NOT MET |
| **C3** | **Historical or Forecasted Velocity** | Is the Scrum Team's historical velocity (or a capacity-based forecasted velocity for new teams) provided to establish a realistic baseline? | [ ] MET <br> [ ] NOT MET |
| **C4** | **Initial Sprint Goal** | Has the Product Owner proposed an initial business objective (the "WHY") for the upcoming Sprint to guide PBI selection? | [ ] MET <br> [ ] NOT MET |

---

## Decision Logic & Rules

*   **IF any criterion is [ ] NOT MET:**
    *   **Action:** Suspend Sprint Planning calculations immediately. 
    *   **Prompt:** Ask the user to provide the missing data. 
    *   *Example:* "To proceed with Empirical Sprint Planning, the system requires [Missing Criterion, e.g., the team's historical velocity and expected time-off for this Sprint]. Planning without this data violates Empirical Process Control and leads to unrealistic commitments."
*   **IF all criteria are [x] MET:**
    *   **Action:** Proceed to the mathematical engine (One-Part Planning). Utilize the provided inputs to calculate Available Effort-Hours and facilitate the creation of the Sprint Backlog and finalized Sprint Goal.
