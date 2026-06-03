---
artifact_name: Release Plan
purpose: Provide a strategic, empirical forecast for the upcoming release, balancing the constraints of scope, date, and budget while clearly defining the Minimum Releasable Features (MRFs).
---

### 🤖 AGENT DIRECTIVE (HIDDEN FROM FINAL OUTPUT)
When generating this Release Plan, the Agent MUST execute the following logic based on the 7 elements from 'Essential Scrum':
1. **Release Goal & Constraints:** Identify if the user's primary constraint is Fixed-Date or Fixed-Scope.
2. **Identify MRFs:** Extract the "Must-have" features that form the viable core of the release.
3. **Calculate Forecasting (The Range):**
   - *If Fixed-Date:* Multiply the team's Velocity Range (Low-High) by the fixed number of Sprints. Count down the Product Backlog to establish the **Scope Range** ("Will have", "Might have", "Won't have").
   - *If Fixed-Scope:* Divide the total size of the MRFs/Scope by the team's Velocity Range (High-Low) to establish the **Sprint Range** (e.g., "7 to 9 Sprints").
4. **Calculate Budget Estimate:** Multiply the number of Sprints (or the Sprint Range) by the estimated run-rate cost per Sprint.
5. **Sprint Mapping (Slotting):** Map ONLY the features for the first 1-2 Sprints. Leave the rest unmapped to respect the Last Responsible Moment.
6. **Output Generation:** Output ONLY the "RELEASE PLAN" section below.

---

### 🚀 PRODUCT RELEASE PLAN: *[Agent: Insert Release Name/Version]*

**⚠️ EMPIRICAL DISCLAIMER:** 
*This Release Plan is an empirical forecast, not a fixed-date or fixed-scope contract. As the Scrum Team creates each Increment and gathers validated learning, this plan will adapt to maximize value.*

#### 1. RELEASE GOAL
> *[Agent: Insert a 1-2 sentence statement communicating the business purpose and desired outcome of this release.]*

#### 2. RELEASE CONSTRAINTS & FORECAST
*   **Primary Constraint:** *[Agent: State either "Fixed-Date" or "Fixed-Scope"]*
*   **Expected Budget Estimate:** *[Agent: Calculate and state the cost. E.g., "$100,000 - $120,000 based on a 5-6 Sprint duration at $20,000/Sprint."]*

*[Agent: Use ONLY ONE of the following two blocks based on the Primary Constraint]*

**(A) FOR FIXED-DATE RELEASES (Flexible Scope):**
*   **Target Release Date:** *[Agent: Insert Date]* (Total Sprints: *[Agent: Insert Number]*)
*   **Scope Range Forecast:** 
    *   **Will Have (MRFs):** *[Agent: List the items that fit within the 'low velocity' calculation]*
    *   **Might Have:** *[Agent: List the items that fall between the 'low' and 'high' velocity calculations]*
    *   **Won't Have:** *[Agent: List items falling outside the capacity for this date]*

**(B) FOR FIXED-SCOPE RELEASES (Flexible Date):**
*   **Target Scope (MRFs):** *[Agent: State the total story points of the fixed scope]*
*   **Sprint/Date Range Forecast:** *[Agent: E.g., "Based on our velocity of 18-22 points/Sprint, delivering this 150-point scope will require 7 to 9 Sprints."]*

#### 3. MINIMUM RELEASABLE FEATURES (MRFs)
*The absolute minimum set of features that must be present for this release to be viable and deliver customer value.*
*   *[Agent: Insert Epic/Feature 1]* - *[Brief Reason]*
*   *[Agent: Insert Epic/Feature 2]* - *[Brief Reason]*

#### 4. SPRINT MAPPING (PBI SLOTTING)
*Forward-looking mapping is limited to near-term Sprints to minimize planning waste. Final selection occurs during Sprint Planning.*
*   **Sprint 1:** *[Agent: List 2-3 highest priority features/PBIs]*
*   **Sprint 2:** *[Agent: List next logical features/PBIs based on dependencies]*
*   **Sprint 3+:** To be determined empirically based on previous Increments.

#### 5. COMMUNICATION & TRACKING
*   **Tracking Tool:** We will use a *[Agent: State either "Release Burndown Chart" or "Release Burnup Chart"]* updated at the end of each Sprint.
*   **Review Cadence:** The Product Owner and Stakeholders will inspect progress against this plan during every **Sprint Review**.