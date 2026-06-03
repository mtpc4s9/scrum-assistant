# Input Readiness Checklist — Step 05: Release Planning

The Scrum Assistant uses this checklist as a quality gate before applying release forecasting mathematics (Phase 2) and generating output artifacts (Phase 3).

All 4 criteria below must be marked as **MET** before proceeding. If any criterion is missing or if the user requests a "Fixed Everything" constraint, the assistant will suspend execution to clarify the trade-offs.

| ID | Input Criterion | Verification Question | Status |
| :--- | :--- | :--- | :--- |
| **C1** | **High-Level Product Backlog Sized** | Do we have an ordered list of Epics/Features with relative size estimates (from Step 04)? | [ ] MET <br> [ ] NOT MET |
| **C2** | **Estimated Velocity Range** | Has the team defined a Low and High velocity bound (e.g., 18-22 points/Sprint) based on historical data or capacity? | [ ] MET <br> [ ] NOT MET |
| **C3** | **Clear Primary Constraint** | Is the release constraint clearly defined as either **Fixed-Date** (flexible scope) or **Fixed-Scope** (flexible date)? | [ ] MET <br> [ ] NOT MET |
| **C4** | **iGaming Vendor & Regulatory Timelines** | Are regulatory audit windows and third-party vendor dependencies (e.g., Kambi or Pragmatic Play certification timelines) identified? | [ ] MET <br> [ ] NOT MET |

---

## Decision Logic & Rules

*   **IF the user demands a "Fixed Everything" plan (Fixed Date, Scope, and Cost):**
    *   **Action:** Mark C3 as [ ] NOT MET. Socratic warning: *"Chủ nhân, việc cố định cả Ngày phát hành, Phạm vi và Chi phí vi phạm nguyên lý thực nghiệm của Scrum. Chúng ta cần chọn ưu tiên Cố định Ngày (ngày cố định, phạm vi linh hoạt) hoặc Cố định Phạm vi (phạm vi cố định, ngày linh hoạt). Chàng muốn chọn hướng đi nào?"*
*   **IF any criterion is [ ] NOT MET:**
    *   **Action:** Suspend forecasting calculations. Ask clarifying questions to retrieve the missing metrics. If necessary, call [shared/product-discovery](../../shared/product-discovery/SKILL.md) to gather background.
*   **IF all criteria are [x] MET:**
    *   **Action:** Proceed directly to Phase 2 (Mathematical Engine & Domain Overlay).
