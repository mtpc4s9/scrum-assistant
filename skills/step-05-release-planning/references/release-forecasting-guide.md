---
artifact_name: Release Forecasting Reference Guide
purpose: Provide the AI Agent with the mathematical logic and empirical principles required to forecast release dates or scope ranges without falling into the "Illusion of Certainty".
---

### Release Forecasting Reference Guide
This document serves as the hidden cognitive and mathematical framework for the Scrum Assistant during **Step 5 - Release Planning**. The Agent MUST use these formulas to calculate forecasts before populating the `release-plan.md` template.

--------------------------------------------------------------------------------

#### 1. Core Empirical Principles
*   **Cone of Uncertainty:** Early in product development, uncertainty is at its highest. Predictions must be expressed as ranges, never as exact, single-point numbers.
*   **Velocity as a Range:** The Agent MUST NEVER use a single average velocity for forecasting. It must always establish a Low Velocity and a High Velocity (e.g., 18 - 22 story points per Sprint).
*   **Empiricism over Prediction:** Remind the user that the forecast is based on current knowledge. As the Scrum Team creates each Increment, the velocity will be updated, and the plan must adapt.

--------------------------------------------------------------------------------

#### 2. Forecasting Mathematics (Agent Logic)

**Scenario A: Fixed-Date Release Planning**
*Context:* The release date is fixed (e.g., a regulatory deadline or a marketing event). The Scope must remain flexible.
*   **Step 1:** Calculate the exact number of Sprints available before the deadline.
*   **Step 2:** Calculate the Scope Range.
    *   *Low Bound:* Number of Sprints × Low Velocity = Minimum points delivered.
    *   *High Bound:* Number of Sprints × High Velocity = Maximum points delivered.
*   **Step 3:** Map the Product Backlog items against this range:
    *   **Will Have (MRFs):** Items that fit within the Low Bound total.
    *   **Might Have:** Items that fall between the Low Bound and High Bound totals.
    *   **Won't Have:** Items whose cumulative size exceeds the High Bound.

**Scenario B: Fixed-Scope Release Planning**
*Context:* A specific set of Minimum Releasable Features (MRFs) is absolutely mandatory for the release to be viable. The Date (Sprint count) must remain flexible.
*   **Step 1:** Calculate the total size (story points) of the mandatory MRFs.
*   **Step 2:** Calculate the Sprint Range.
    *   *Fastest Delivery:* Total Size ÷ High Velocity (Round UP to the next whole Sprint).
    *   *Slowest Delivery:* Total Size ÷ Low Velocity (Round UP to the next whole Sprint).
*   **Step 3:** Present the forecast as a range (e.g., "This scope will require 7 to 9 Sprints to complete").

--------------------------------------------------------------------------------

#### 3. Agent Execution Directives
*   **Identify the Constraint:** Always ask the Product Owner whether Date or Scope is the primary constraint. 
*   **Reject "Fixed Everything":** If the user demands a Fixed-Scope AND Fixed-Date plan without flexible budget/resources, the Agent MUST warn them using Socratic questioning about the risk of accruing severe Technical Debt or burning out the Developers.
*   **Sprint Slotting (Last Responsible Moment):** Do not map specific items to specific Sprints beyond Sprint 1 and Sprint 2. Leave subsequent Sprints as "To be determined empirically".
