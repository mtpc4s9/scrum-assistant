---
artifact_name: Cost of Delay (CoD) Reference Guide
purpose: Provide the AI Agent with an economic framework to evaluate the financial or risk impact of delaying a Product Goal.
---

### Cost of Delay (CoD) Reference Guide
In empirical product development, time is a critical economic variable. Cost of Delay quantifies the financial or risk-based cost of *not* doing something or delaying a Product Goal [6]. The AI Agent must use this guide to help the Product Owner evaluate candidate goals qualitatively using CoD Profiles.

--------------------------------------------------------------------------------

#### 1. The 6 Cost of Delay Profiles
When evaluating a candidate Product Goal, the Agent must map its business context to one of these profiles [7-9]:

1.  **Fixed Date:** A goal that must be delivered by a fixed future date (e.g., regulatory compliance, a planned marketing event). It has zero cost of delay until the fixed date occurs, after which the penalty is severe (e.g., losing a license).
2.  **Must Do Now:** A goal without which the organization incurs immediate lost revenue or cost savings that continue to grow over time.
3.  **Linear:** A goal where the cost of delay increases at a constant, steady rate (e.g., standard revenue-generating features).
4.  **Large Fixed Cost:** A goal that accrues a one-time massive cost if not acted on immediately (e.g., a penalty fee or a missed one-time payout).
5.  **Logarithmic:** A goal that accrues most of its delay cost very early, with increasingly less incremental delay cost thereafter (e.g., capturing early adopters in a fading trend).
6.  **Intangible:** A goal with no apparent immediate cost of delay, but which suddenly accrues a very high delay cost later (e.g., addressing high-interest Technical Debt before it reaches a tipping point).

--------------------------------------------------------------------------------

#### 2. Agent Directives & Execution Logic
*   **Assessment:** Analyze each candidate Product Goal and ask the user (Product Owner) to clarify the business impact if the goal is delayed by 1-3 months.
*   **Mapping:** Assign a CoD Profile to each goal based on the user's input.
*   **Prioritization Rule:** Always prioritize **Fixed Date** (if the deadline is approaching) and **Must Do Now** profiles over Linear or Intangible ones.
*   **Integration:** Output the CoD rationale when presenting the final prioritized Product Goal decision.
