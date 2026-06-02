# Input Readiness Checklist — Step 01: Visioning

The Scrum Assistant uses this checklist as a quality gate before starting the iGaming Domain Context Overlay (Phase 2) and generating output artifacts (Phase 3). 

All 5 criteria below must be marked as **MET** before proceeding. If any criterion is missing or unclear, the assistant will trigger the `shared/product-discovery` elicitation workflow to align on the missing information.

| ID | Input Criterion | Verification Question | Status |
|:---|:---|:---|:---|
| **C1** | **Product / Feature Identity** | Is the name or concept of the product/feature clearly specified? | [ ] MET <br> [ ] NOT MET |
| **C2** | **Target Customer / User Segment** | Who is the primary persona, operator, or end-user of this product/feature? | [ ] MET <br> [ ] NOT MET |
| **C3** | **Core Problem / Opportunity** | What pain point is being resolved, or what business opportunity is being captured? | [ ] MET <br> [ ] NOT MET |
| **C4** | **Business Goal / Value Drivers** | What is the quantitative or qualitative business goal (e.g., revenue growth, compliance mitigation, user retention, operational efficiency)? | [ ] MET <br> [ ] NOT MET |
| **C5** | **Domain / Regulatory Boundary** | Are the jurisdictional boundaries (e.g., Vietnam Decree 06, PAGCOR, MGA, UKGC) or regulatory constraints identified, or explicitly declared as none? | [ ] MET <br> [ ] NOT MET |

---

## Decision Logic & Rules

*   **IF any criterion is [ ] NOT MET:**
    *   **Action:** Terminate the standard execution flow. Call the Product Discovery skill located at [shared/product-discovery/SKILL.md](../../shared/product-discovery/SKILL.md) to interview the user and gather missing details.
    *   **Rule:** Repeat the discovery cycle until all 5 checklist items are verified as `MET`.
*   **IF all criteria are [x] MET:**
    *   **Action:** Proceed directly to Phase 2 (Domain Context Overlay).
