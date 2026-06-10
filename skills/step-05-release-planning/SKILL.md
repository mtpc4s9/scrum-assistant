---
name: step-05-release-planning
description: Execute Step 5 - Release Planning by orchestrating empirical forecasting (Fixed-Date or Fixed-Scope) based on Team Velocity, MRFs, and generating a dynamic Release Plan.
---

# Step 05: Release Planning

This skill controls the execution of the **Step 5 — Release Planning** workflow. The goal is to transition from a High-Level Product Backlog into an empirical forecast (Release Plan) balancing scope, dates, and run-rates using Velocity ranges, avoiding predictive Waterfall traps.

---

## 0. Backbone & Phase Context
*   **Backbone Step:** Step 5 — Release Planning
*   **Scrum Flow Phase:** Phase 0 — Initiative (Upstream Scrum Preparation)
*   **Primary Owner:** Product Owner (PO)
*   **Scrum Master Role:** Ensure the Release Plan is positioned as an empirical forecast, protect Developers from impossible commitments ("Fixed Everything"), and coach the team on velocity variance.
*   **Target Output Deliverables:**
    *   [A] Release Plan

---

## 1. Phase 1 — Input Quality Gate

### 1.1 Trigger Conditions & Keywords
The Scrum Assistant activates this skill when the user initiates a release planning session, requests velocity calculations, or seeks to forecast delivery dates:
*   **English Triggers:** "release plan", "step 5", "release planning", "forecast release", "velocity calculator"
*   **Vietnamese Triggers (Trữ nguyên trạng):** "lập kế hoạch phát hành", "release plan", "tính toán release", "dự báo phát hành", "lập kế hoạch release"

### 1.2 Quality Gate Verification
Upon activation, the assistant must load the input quality gate checklist from [input-readiness.md](checklists/input-readiness.md) and evaluate the user's request against the 4 core criteria:
1.  **High-Level Product Backlog Sized** (Do we have an ordered list of Epics/Features with relative size estimates from Step 4?)
2.  **Estimated Velocity Range** (Has the team defined expected Low and High velocity bounds per Sprint?)
3.  **Clear Primary Constraint** (Is the release prioritized by Fixed-Date or Fixed-Scope?)
4.  **iGaming Vendor & Regulatory Timelines** (Are third-party vendor launch windows and compliance deadlines identified?)

### 1.3 Discovery Loop Rule
*   **IF the user demands a "Fixed Everything" plan (Fixed Scope, Fixed Date, AND Fixed Cost):**
    *   The assistant **MUST** halt and warn the user: *"Chủ nhân, việc cố định cả Ngày phát hành, Phạm vi và Chi phí vi phạm nguyên lý thực nghiệm của Scrum. Chúng ta cần chọn ưu tiên Cố định Ngày (ngày cố định, phạm vi linh hoạt) hoặc Cố định Phạm vi (phạm vi cố định, ngày linh hoạt). Chàng muốn chọn hướng đi nào?"*
*   **IF any of the 4 criteria are NOT MET:**
    *   The assistant **MUST** suspend the forecasting calculations.
    *   Ask clarifying questions to obtain the missing inputs, or call [../shared/product-discovery/SKILL.md](../shared/product-discovery/SKILL.md) to gather context.
*   **IF all 4 criteria are MET:**
    *   Proceed directly to Phase 2 (Mathematical Engine & Domain Overlay).

---

## 2. Phase 2 — Mathematical Engine & Domain Overlay (Optional Domain Scan)

Once the quality gate is cleared, the assistant performs the forecasting calculations and overlays domain constraints.

### 2.1 Domain Scan (Optional)
Check if the project is in the iGaming or Online Lottery domain. Ask the user: *"Is this project in the iGaming or Online Lottery domain? (yes/no)"* (or detect from project context).

*   **IF domain is NOT iGaming/Lottery:** Skip the domain scan and proceed directly to 2.2 Mathematical Forecasting Loop.
*   **IF domain IS iGaming/Lottery:**
    1.  **Extract Keywords:** Identify key domain terms from the backlog inputs (e.g., `Kambi`, `Pragmatic Play`, `Momo`, `USDT`, `Decree 06`, `Vietlott`).
    2.  **Scan iGaming Context:** Open [igaming-context.md](../../reference/igaming-context.md) and scan **only** the sections with headings matching the extracted keywords.
    3.  **Identify Regulatory Constraints:** Note compliance timelines (e.g., MoMo transaction limits or Decree 06 daily caps) that might affect release staging or require early sub-releases.

### 2.2 Mathematical Forecasting Loop
The assistant **MUST** calculate the forecast based on the constraint type:
*   **Fixed-Date (Flexible Scope):**
    *   `Sprints Available × Low Velocity` = Minimum points delivered (Will Have / MRFs).
    *   `Sprints Available × High Velocity` = Maximum points delivered (Might Have / Won't Have boundary).
*   **Fixed-Scope (Flexible Date):**
    *   `Total MRF Size ÷ High Velocity` = Fastest delivery (Sprints).
    *   `Total MRF Size ÷ Low Velocity` = Slowest delivery (Sprints).

---

## 3. Phase 3 — Output Generation & Techniques

### 3.1 On-Demand Reference Pattern
To prevent token bloat during conversation, the mathematical formulas and Cone of Uncertainty concepts are stored separately.
*   **Action:** When performing forecasting calculations, the assistant **MUST** refer to the on-demand reference guide at [references/release-forecasting-guide.md](references/release-forecasting-guide.md).

### 3.2 Template Catalogue Presentation
The assistant **MUST NOT** generate the release plan automatically. Present the math forecast and iGaming limits, then display the template catalogue:

```
Inputs validated. Sprints and scope ranges have been calculated empirically.
Please select which deliverable to generate:

[A] Product Release Plan  → (Ref: templates/release-plan.md)
```

### 3.3 Output Execution & Enrichment Rules
Once the user selects "Generate [A]" or "Làm Release Plan":
1.  Load the target template file at [templates/release-plan.md](templates/release-plan.md).
2.  Follow the **AGENT DIRECTIVE** instructions inside the template precisely.
3.  **Enrichment Rule:** Integrate the calculations from Phase 2 into the roadmap. Ensure that **Sprint Mapping (Slotting)** is strictly limited to Sprint 1 and Sprint 2 to prevent waste. Sprints 3+ must be left unmapped.
4.  **iGaming Timeline Sync:** Inject key vendor testing/certification windows (e.g., "Kambi Sandbox testing in Sprint 1", "Pragmatic Integration audit in Sprint 2") directly into the mapping.

---

## 4. Readiness Self-Audit

Before returning the generated document to the user, the assistant must verify:
*   Did I use the exact structure defined in the selected template?
*   Are all relative paths formatted using relative links?
*   Did I map features to ONLY Sprint 1 and Sprint 2?
*   Did I include the mandatory empirical disclaimer at the top?
*   Is the content written in professional, Scrum Guide 2020 aligned English?
