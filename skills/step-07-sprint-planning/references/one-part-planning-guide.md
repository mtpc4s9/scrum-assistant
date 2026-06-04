---
artifact_name: One-Part Sprint Planning Reference Guide
purpose: Provide the AI Agent with the cognitive framework and empirical execution loop for facilitating One-Part Sprint Planning, ensuring the team interleaves PBI selection (WHAT) with task planning (HOW) to acquire confidence and avoid over-commitment.
---

### One-Part Sprint Planning Reference Guide
This document serves as the hidden logic engine for the Scrum Assistant during **Step 7 - Sprint Planning**. The Agent MUST use the One-Part Planning approach, interleaving "What" and "How" iteratively, to ensure the Developers make a realistic, mathematically sound commitment.

--------------------------------------------------------------------------------

#### 1. Core Principles of One-Part Planning
*   **Interleaved Logic (What + How):** Unlike Two-Part Planning (where all PBIs are selected first, then all tasks are planned), One-Part Planning requires the team to select a single Product Backlog Item (PBI), break it down into actionable tasks immediately, and deduct the estimated task hours from the team's available capacity before selecting the next PBI.
*   **Acquiring Confidence:** The purpose of task breakdown during Sprint Planning is NOT to create a micro-managed Gantt chart. It is a just-in-time design activity allowing the Developers to acquire confidence that the work actually fits within the Sprint constraints.
*   **Start Only What You Can Finish:** The Agent must enforce the rule: Do not start a PBI if the task-hour breakdown exceeds the remaining Sprint capacity. Incomplete items at the end of a Sprint violate empiricism and generate waste.

--------------------------------------------------------------------------------

#### 2. The One-Part Execution Loop (Agent Algorithm)
When guiding the Scrum Team through Sprint Planning, the Agent MUST execute the following sequence:

*   **Step 1: Calculate Net Capacity:** Determine the Total Available Effort-Hours using the `Table 19.2` logic (Gross Capacity minus PTO, Scrum Events, buffers, and non-Sprint maintenance).
*   **Step 2: Establish the WHY:** Facilitate the creation of a unified **Sprint Goal** proposed by the Product Owner and negotiated with the Developers.
*   **Step 3: The Interleaved Selection Loop:**
    1.  **Select:** Pull the highest priority PBI from the Product Backlog that aligns with the Sprint Goal.
    2.  **Breakdown (HOW):** Decompose the PBI into technical and testing tasks. (Rule: No single task should exceed 8 effort-hours).
    3.  **Validate against DoD:** Ensure tasks include all work required to meet the **Definition of Done** (e.g., automated testing, code review, iGaming compliance checks).
    4.  **Deduct:** Subtract the sum of these task hours from the Total Available Effort-Hours.
    5.  **Evaluate:** 
        *   *IF Remaining Capacity > 0:* Repeat Step 3 for the next PBI.
        *   *IF Remaining Capacity ≤ 0:* STOP selection. The commitment is full.
*   **Step 4: Finalize Commitment:** Present the final Sprint Backlog to the Product Owner for agreement.

--------------------------------------------------------------------------------

#### 3. Agent Execution Directives & Anti-Patterns
*   **Reject Top-Down Task Assignment:** The Agent MUST NOT assign specific Developers to specific tasks during Sprint Planning. Remind the team that Developers are a self-managing unit who will pull tasks opportunistically during Sprint Execution.
*   **Prevent Waterfall in the Sprint:** The Agent MUST warn the team if they create tasks that look like a mini-waterfall (e.g., "Analyze all PBIs", then "Code all PBIs"). Emphasize cross-functional swarming and finishing one PBI at a time.
*   **Protect the Sprint Goal:** If a PBI does not align with the Sprint Goal but the Product Owner insists on adding it, the Agent should permit it ONLY IF capacity allows, but note that it is secondary to the core commitment.

--------------------------------------------------------------------------------

#### 4. Mathematical Engine & Formulas (Table 19.2 Reference)
To calculate Net Available Effort-Hours per developer, the Agent must enforce the following equations:

$$\text{Gross Focus Hours} = (\text{Days Available} - \text{PTO Days} - \text{Holiday Days}) \times \text{Net Hours/Day} \times \text{Focus Factor (default 70\%)}$$
$$\text{Net Available Effort-Hours} = \text{Gross Focus Hours} - \text{Ceremony Hours}$$

Where:
*   **Days Available:** Total working days in the Sprint (e.g., 10 days for a 2-week Sprint).
*   **PTO Days:** Personal Time Off (vacation/sick).
*   **Holiday Days:** Public holidays.
*   **Net Hours/Day:** Standard daily hours (default 8 hours/day).
*   **Focus Factor:** Empirical focus percentage (default 70% or 0.70) to account for daily non-Sprint interruptions.
*   **Ceremony Hours:** Total overhead for Scrum events.

$$\text{Total Team Net Capacity} = \sum (\text{Individual Net Available Effort-Hours})$$

##### Scrum Ceremony Overhead Reference Table
| Ceremony | Duration / Frequency |
| :--- | :--- |
| **Sprint Planning** | 2–4 hours per Sprint |
| **Daily Scrums** | 15 minutes (0.25 hrs) per working day |
| **Sprint Review** | 1–2 hours per Sprint |
| **Retrospective** | 1–2 hours per Sprint |
| **Backlog Refinement** | 1–2 hours per Sprint |

--------------------------------------------------------------------------------

#### 5. Capacity Allocation Categories (Figure 19.5 Reference)
Capacity should be distributed into five distinct buckets representing realistic team availability, avoiding the 100% utilization trap:
1.  **Capacity for PBIs (Sprint Execution):** Time reserved exclusively for developing and testing committed backlog items.
2.  **Personal Time Off (PTO):** Planned holidays or personal leave.
3.  **Other Scrum Activities:** Timebox overhead for Scrum Events and Product Backlog Refinement.
4.  **Non-Sprint Commitments:** Time spent on cross-team meetings, organization-wide initiatives, or production support.
5.  **Sprint Buffer:** Protection against unknown unknowns or unexpected technical complexity (typically 5-10% of total capacity).

