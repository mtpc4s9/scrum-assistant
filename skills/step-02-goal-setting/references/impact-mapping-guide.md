# Impact Mapping Reference Guide

This guide outlines the mechanics and application of **Impact Mapping** to transition from a high-level Product Vision to a concrete, measurable Product Goal and initial Product Backlog items. 

By keeping this guide separate from the main `SKILL.md` orchestrator, the assistant maintains a low token footprint and only accesses these instructions when explicitly required.

---

## 1. Core Mechanics of Impact Mapping

Impact Mapping is a strategic planning technique that prevents organizations from building useless features. It links deliverables directly to business outcomes by answering four questions:

```
  🎯 WHY (Product Goal)
        │
        └── 👥 WHO (Actors / Stakeholders)
              │
              └── 🔄 HOW (Behavioral Impacts)
                    │
                    └── 📦 WHAT (Deliverables / Epics)
```

1.  **WHY (Goal):** Why are we doing this? This is the core Product Goal. It must be measurable, SMART, and aligned with the Product Vision.
2.  **WHO (Actors):** Whose behavior do we want to change? Who can produce the desired effect? Who can obstruct it? (e.g., Casual Players, KYC Auditors, Payment Gateway Vendors).
3.  **HOW (Impacts):** How should the actors' behavior change? How can they help us achieve the goal? How can they obstruct us? (Focus on behavioral actions, not software features).
4.  **WHAT (Deliverables):** What can we do, as a Scrum Team, to support or trigger these behavioral changes? These become the initial Epics or Features in the Product Backlog.

---

## 2. iGaming Application Example

To help write realistic backlogs, use this iGaming-focused reference model during mapping:

### 🎯 Goal (WHY)
*   **Goal:** "Reduce player withdrawal churn by 25% by Q4 while maintaining 100% AML compliance."

### 👥 Actors (WHO) -> 🔄 Impacts (HOW) -> 📦 Deliverables (WHAT)

*   **Actor: VIP Player**
    *   *Impact (HOW):* Expects instant payouts for winnings over $1,000 to build platform trust.
    *   *Deliverable (WHAT):* Automated balance verification engine for VIP tiers; Instant payout API integrations with local banks.
*   **Actor: Risk & Compliance Officer**
    *   *Impact (HOW):* Needs to audit large withdrawals without manually reviewing every minor transaction.
    *   *Deliverable (WHAT):* Real-time automated transaction monitoring dashboard; Automated flagging rules for suspicious wagering behavior.
*   **Actor: Customer Support Agent**
    *   *Impact (HOW):* Needs to answer transaction status queries immediately without querying DB developers.
    *   *Deliverable (WHAT):* Internal Admin Panel Wallet lookup tool with transaction status trace.

---

## 3. Guiding Rules for the Agent

When collaborating with the Product Owner (Chủ nhân) on an Impact Map:
*   **Never start with the "WHAT":** If the user requests a feature (e.g., "We need ZaloPay integration"), immediately trace back: *Who uses it? What behavior does it change? How does that support the overarching Product Goal?*
*   **Eliminate Orphan Deliverables:** If a proposed feature (WHAT) does not directly connect to a behavioral impact (HOW) of an identified actor (WHO), it is waste. Advise the user to discard it.
*   **Formulate Hypotheses:** Every branch of the map is a hypothesis. Write the final map summary using the template:
    > "We believe that building **[WHAT]** will encourage **[WHO]** to **[HOW]**, which will help us achieve our goal of **[WHY]**."
