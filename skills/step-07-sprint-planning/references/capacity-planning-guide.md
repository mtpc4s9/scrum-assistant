---
artifact_name: Sprint Capacity Planning Reference Guide
purpose: Provide the mathematical engine and guardrails for calculating team capacity (Effort-Hours and Story Points) for the upcoming Sprint.
---

# Sprint Capacity Planning Reference Guide

This reference guide provides the step-by-step mathematical model and policies for establishing a realistic team capacity before making Sprint commitments.

---

## 1. Capacity Calculation Engine

To calculate the net capacity available for Sprint backlog execution:

### Step A: Individual Gross Availability
Determine the gross working days for each developer:
$$\text{Days Available} = \text{Working Days in Sprint} - \text{Planned PTO} - \text{Public Holidays}$$

### Step B: Individual Focus Hours
Apply the Focus Factor (default: **70%** or **0.70**) to determine the baseline hours spent on active development work:
$$\text{Focus Hours} = \text{Days Available} \times 8 \text{ hours/day} \times \text{Focus Factor}$$
*Note: Focus Factor accounts for daily interruptions, email, minor administrative tasks, and non-Scrum meetings.*

### Step C: Ceremony Overhead Deduction
Subtract the collective overhead for standard Scrum ceremonies to calculate the **Net Available Effort-Hours**:
$$\text{Net Available Effort-Hours} = \text{Focus Hours} - \text{Ceremony Hours}$$

Use the typical Scrum ceremony duration matrix below to calculate ceremony hours:

| Ceremony | Typical Duration | Sprint Duration Metric |
| :--- | :--- | :--- |
| **Sprint Planning** | 2–4 hours | Per Sprint |
| **Daily Scrums** | 15 minutes (0.25 hrs) | Per Working Day (excluding planning day) |
| **Sprint Review** | 1–2 hours | Per Sprint |
| **Retrospective** | 1–2 hours | Per Sprint |
| **Product Backlog Refinement** | 1–2 hours | Per Sprint |

### Step D: Team Aggregate Capacity
Sum the net development hours across all Developers and normalize back to developer-days:
$$\text{Total Team Net Effort-Hours} = \sum (\text{Individual Net Available Effort-Hours})$$
$$\text{Total Team Developer-Days} = \frac{\text{Total Team Net Effort-Hours}}{8 \text{ hours/day}}$$

---

## 2. Deriving Story Point Commitment Range

If historical velocity data is available (from the last 3+ Sprints), convert Net Capacity into a forecasted story point range:

1. **Calculate Point Productivity:**
   $$\text{Points per Dev-Day} = \frac{\text{Reference Velocity (Avg points completed)}}{\text{Reference Capacity (Avg dev-days available in those Sprints)}}$$

2. **Forecast Commitment Ceiling:**
   $$\text{Recommended Commitment (Points)} = \text{Total Team Developer-Days} \times \text{Points per Dev-Day}$$

3. **Establish Commitment Range:**
   *   **Conservative Commitment (Floor):** $\text{Recommended Commitment} \times 0.85$
   *   **Maximum Commitment (Ceiling):** $\text{Recommended Commitment} \times 1.00$

> [!IMPORTANT]
> If the team has fewer than 3 Sprints of history, skip point conversion and plan using developer-days / effort-hours capacity only. Do not perform point-based conversion.

---

## 3. Flags and Guardrails

### ⚠ Capacity Flags
*   **Availability Alert:** If any team member's availability drops below **50%** due to PTO or shared allocation, flag this to the Scrum Team.
*   **PO Awareness Flag:** If a single team member has **> 40% of the Sprint** as days off, flag it immediately to the Product Owner as it indicates potential bottleneck/delivery risks.
*   **Sprint Length Deviation:** Flag any Sprint with a duration shorter than normal (due to public holidays or office closures).

### 🛡️ Guardrails
*   **The 100% Utilization Trap:** Never plan for 100% utilization. Humans are not machines. Always keep focus factors at $\le 70\%$ unless empirical history proves otherwise.
*   **No Capacity Comparison:** Never compare capacity or developer-days productivity across different teams.
*   **Goals Over Capacity:** Capacity is a boundary limit, not the goal. The team commits to the Sprint Goal; capacity only indicates if the forecast is realistic.
