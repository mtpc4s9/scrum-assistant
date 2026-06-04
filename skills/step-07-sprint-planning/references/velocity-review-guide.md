---
artifact_name: Sprint Velocity Review Reference Guide
purpose: Provide the Scrum Master with analytical metrics and coaching observations to evaluate historical team velocity and guide commitments.
---

# Sprint Velocity Review Reference Guide

This reference guide outlines the metrics, patterns, and coaching observations used to analyze historical team velocity to ensure predictable planning.

---

## 1. Velocity Analysis Metrics

Velocity is an empirical forecasting tool, not a measure of team productivity. To evaluate planning health:

### Average Velocity
The baseline point capability of the team:
$$\text{Average Velocity} = \frac{\sum \text{Completed Story Points across Reviewed Sprints}}{\text{Number of Reviewed Sprints}}$$
*Note: Only count completed Sprints. Never include the current active Sprint.*

### Predictability Rate (Commitment Accuracy)
Measures how reliably the team delivers their forecast:
$$\text{Predictability Rate} = \frac{\text{Completed Story Points}}{\text{Committed Story Points at Sprint Start}} \times 100\%$$

*   **Healthy Range:** **80% – 100%**. The team regularly delivers what they plan.
*   **Chronic Overcommitment:** **< 70%**. The team consistently fails to deliver their commitment. Indicates estimation optimism or mid-Sprint interruptions.
*   **Undercommitment / Scope Expansion:** **> 110%**. The team regularly exceeds their initial commitment. May indicate conservative estimating or pulling in unestimated work mid-Sprint.

### Velocity Trend
Compare the average of the first half of the review window to the second half:
*   **Improving:** The latter Sprints average significantly higher than earlier ones.
*   **Declining:** The latter Sprints average lower.
*   **Stable:** The average of the second half is within **±15%** of the first half.

### Variability (Standard Deviation)
Evaluates consistency of story delivery:
*   **High Variability:** Standard deviation $> 25\%$ of the mean velocity. Planning is highly unpredictable.
*   **Low Variability:** Standard deviation $< 15\%$ of the mean velocity. Planning is highly consistent.

---

## 2. Coaching Observations & Patterns

Use these patterns to coach the team during Retrospectives or Sprint Planning:

| Pattern | Observation | Actions / Recommendations |
| :--- | :--- | :--- |
| **Consistent Overcommitment** | Predictability $< 70\%$ for multiple Sprints. | Coach the team to reduce their initial forecast by $15-20\%$ or enforce stricter task sizing ($\le 8$ hours). |
| **High Variability** | Std dev $> 25\%$ of mean with no obvious holidays. | Relative estimation calibration exercise. Ensure stories are sliced smaller. |
| **Declining Trend** | Velocity dropping steadily. | Investigate increasing technical debt, high support load, or team morale issues. |
| **Stable & Healthy** | Predictability $80-100\%$, variability $< 15\%$. | Excellent foundation. Maintain current estimation practices and use for long-range planning. |
| **Undercommitment** | Predictability $> 110\%$ consistently. | Ensure mid-sprint scope changes are explicitly tracked. Encourage the team to take on slightly more stretch goals. |

---

## 3. Guardrails

*   **The Velocity Rule of Three:** If the team has fewer than **3 completed Sprints** of data, skip story point conversion. Plan the Sprint using developer-days and task hours only.
*   **Not a Performance Metric (KPI):** Never present velocity as a productivity metric to management or compare velocities between teams. Different teams use different scales and contexts.
*   **No Cross-Team Comparison:** Direct comparison of velocity between teams is meaningless and leads to point inflation.
*   **Carryover Impact:** Acknowledge that carryover stories inflate the velocity of the Sprint they finish in, and deflate the velocity of the Sprint they started in. Analyze the trend, not a single outlier Sprint.
