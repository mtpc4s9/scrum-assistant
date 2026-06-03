---
artifact_name: WSJF (Weighted Shortest Job First) Reference Guide
purpose: Provide the AI Agent with a mathematical prioritization model to optimize overall lifecycle profits when both Cost of Delay and implementation size vary across candidate goals.
---

### WSJF (Weighted Shortest Job First) Reference Guide
When multiple Product Goals compete for the Scrum Team's capacity, and both the Cost of Delay and the Size/Duration of those goals vary, WSJF is the economically optimal scheduling strategy [2, 3]. 

--------------------------------------------------------------------------------

#### 1. The WSJF Formula
**WSJF = Cost of Delay / Size (Duration)**

*   **Cost of Delay (CoD):** Represents the financial value, risk mitigation, or opportunity enablement lost per unit of time (e.g., $50K/month). Alternatively, it can be a relative Fibonacci number representing business urgency.
*   **Size (Duration):** The estimated effort required to complete the Product Goal. To avoid wasting the Developers' time, this must be a rough estimate, ideally T-Shirt sizing (S, M, L, XL) converted to a numeric value (e.g., S=1, M=2, L=3, XL=5) or macro-level story points [5].

**Core Principle:** A goal that delivers high value (High CoD) and takes very little time to build (Small Size) will have the highest WSJF score and must be prioritized first.

--------------------------------------------------------------------------------

#### 2. Agent Directives & Execution Logic
*   **Trigger:** If the user presents candidate goals that have similar Cost of Delay profiles, the Agent MUST invoke WSJF to break the tie.
*   **Socratic Prompting:** If the user wants to use WSJF but has not provided Size estimates, the Agent MUST pause and state: *"To calculate WSJF, we need a rough Size estimate for these goals. Please consult the Developers for a quick T-Shirt size estimate (S, M, L, XL). Do not force them into detailed precision."* [5, 10]
*   **Calculation & Ranking:** Divide the CoD value by the Size value. Rank the candidate goals in descending order of their WSJF score.
*   **Alignment:** Remind the Product Owner that while WSJF is powerful, Empiricism dictates that it is a guide, not a rigid law. Dependencies and technical risks must also be considered before finalizing the 1st Product Goal.
