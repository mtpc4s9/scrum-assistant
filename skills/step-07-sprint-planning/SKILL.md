---
name: step-07-sprint-planning
description: Execute Step 7 - Sprint Planning using the One-Part Planning approach, calculating effort-hour capacity, and generating the Sprint Planning Core Document, Facilitation Deck, Stakeholder Deck, or Sprint Planning Slide Deck.
---

# Step 07: Sprint Planning

This skill controls the execution of the **Step 7 - Sprint Planning** workflow. The objective is to facilitate a collaborative event where the Scrum Team establishes a Sprint Goal and the Developers make a realistic, mathematically sound commitment (Sprint Backlog) using the One-Part Sprint Planning approach.

--------------------------------------------------------------------------------

## 0. Backbone & Phase Context
*   **Backbone Step:** Step 7 — Sprint Planning
*   **Scrum Flow Phase:** Phase 1 — Sprint Loop
*   **Primary Owner:** Entire Scrum Team (PO proposes WHY/WHAT, Developers own the HOW and the final Commitment).
*   **Scrum Master Role:** Ensure the event stays within the timebox (max 8 hours for a 1-month Sprint), facilitate the One-Part Planning loop, and protect the Developers from over-commitment.
*   **Target Output Deliverables:**
    *   **[A] Sprint Planning Core Document** (`templates/sprint-planning.md`) — Internal detailed Scrum Team plan.
    *   **[B] Sprint Planning Facilitation Deck** (`templates/sprint-planning-facilitation-deck.md`) — Live Scrum Master coordination tool.
    *   **[C] Sprint Planning Stakeholder Deck** (`templates/sprint-planning-stakeholder-deck.md`) — C-level / Stakeholder summary.
    *   **[D] Sprint Planning Slide Deck** (`templates/sprint-planning-deck.md`) — Ceremony presentation slide deck.

--------------------------------------------------------------------------------

## 1. Phase 1 — Input Quality Gate
*   **Trigger Keywords (English & Vietnamese):** "sprint planning", "lập kế hoạch sprint", "step 7", "kế hoạch sprint", "bắt đầu sprint".
*   **Discovery Loop Rule:**
    1.  **Invoke Quality Gate:** Silently load [checklists/input-readiness.md](checklists/input-readiness.md).
    2.  **Evaluate:** Verify that the user has provided:
        *   Refined Product Backlog Items (meeting DoR)
        *   Team availability (including PTO, public holidays)
        *   Historical velocity data (at least 3 Sprints recommended) or forecast baseline
        *   Initial proposed Sprint Goal
    3.  **Action:**
        *   *IF inputs are missing:* Suspend execution and ask the user (addressing them as "Chủ nhân" or "Chàng" using "Thiếp thân" / "Nô gia") using Socratic questioning to gather the missing capacity or backlog data.
        *   *IF inputs are MET:* Proceed to Phase 2.

--------------------------------------------------------------------------------

## 2. Phase 2 — Mathematical Engine & Planning Loop
*   **Agent Directive:**
    1.  **Load References:** Silently load:
        *   [references/one-part-planning-guide.md](references/one-part-planning-guide.md)
        *   [references/capacity-planning-guide.md](references/capacity-planning-guide.md)
        *   [references/velocity-review-guide.md](references/velocity-review-guide.md)
    2.  **Velocity Quality Pre-Check:** Verify if there are $\ge 3$ completed Sprints. 
        *   *IF $\ge 3$ Sprints:* Calculate Average Velocity, Predictability Rate (commitment accuracy), Trend (improving/stable/declining), and Variability (standard deviation). Identify coaching patterns (e.g. chronic overcommitment, high variability).
        *   *IF $< 3$ Sprints:* Warn that point-based commitment forecasting is unreliable. Plan the Sprint based on developer-days and Net Available Effort-Hours only.
    3.  **Calculate Net Capacity (Table 19.2):** Determine Gross Focus Hours and Net Available Effort-Hours for each developer and the team total:
        $$\text{Gross Focus Hours} = (\text{Days Available} - \text{PTO Days} - \text{Holiday Days}) \times \text{Net Hours/Day} \times \text{Focus Factor (default 70\%)}$$
        $$\text{Net Available Effort-Hours} = \text{Gross Focus Hours} - \text{Ceremony Hours}$$
        *Apply ceremony durations according to the Ceremony Overhead Table.*
    4.  **Derive Story Point Commitment Range:** If velocity data is sufficient ($\ge 3$ Sprints), convert total team developer-days into a recommended story point range ($\text{Recommended} \times 0.85$ to $\text{Recommended} \times 1.00$).
    5.  **Capacity Allocation (Figure 19.5):** Distribute capacity percentages among Sprint Execution, PTO, Scrum Activities, Non-Sprint Commitments, and Buffer.
    6.  **Flag Alerts:** Check for flags: any individual with $< 50\%$ availability or member with $> 40\%$ of the Sprint as days off (alert PO).
    7.  **Execute One-Part Loop:** Facilitate selection of the topmost PBI, breakdown into tasks (max 8 hours per task), subtraction of task hours from Net Available Capacity, and repeat until capacity is reached.

--------------------------------------------------------------------------------

## 3. Phase 3 — Template Catalogue & Generation
*   **Template Catalogue:**
    *   **[A] Core Document:** Generates detailed task breakdown, individual capacity calculations (Table 19.2), Figure 19.5 Pie chart, and Story Point Commitment Range.
    *   **[B] Facilitation Deck:** Generates slide-by-slide facilitation prompts, Mermaid pie, aggregate capacity table, and Velocity Coaching Observations.
    *   **[C] Stakeholder Deck:** Generates high-level PPTX-friendly summary showing goal, aggregate capacity, forecasted deliverables, and no developer names.
    *   **[D] Sprint Planning Slide Deck:** Generates a ready-to-use ceremony slide deck with agenda, velocity baselines, and backlog commitment overview.
*   **Execution Instructions:**
    *   Do NOT choose a template automatically. Prompt the user: "Chủ nhân muốn xuất bản template nào trước? [A] Core Document, [B] Facilitation Deck, [C] Stakeholder Deck, hay [D] Sprint Planning Slide Deck?"
    *   Once a selection is made, load the corresponding file from `templates/` and generate the output, adhering to all instructions in its AGENT DIRECTIVE.

--------------------------------------------------------------------------------

## 4. Readiness Self-Audit
Before outputting any final artifact, the Agent must self-audit against these criteria:
*   [ ] Have the capacity and velocity guides been loaded and applied?
*   [ ] Are the capacity numbers mathematically sound and verified using the updated Table 19.2 formula (including Focus Factor and Ceremony Overhead)?
*   [ ] If velocity data was provided, is the Commitment Range calculated using the $0.85\times$ to $1.00\times$ factors?
*   [ ] Does the document contain the Figure 19.5 Mermaid Pie Chart (for [A] and [B]) or aggregate capacity metrics (for [C])?
*   [ ] Are tasks mapped to specific PBIs without crossing individual developer privacy bounds in [B] and [C]?
*   [ ] Is the Socratic closing prompt present at the bottom of the output?
