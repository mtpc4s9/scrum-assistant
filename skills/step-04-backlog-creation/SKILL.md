---
name: step-04-backlog-creation
description: Decompose the prioritized Product Goal into a High-Level Product Backlog (Epics/Features) and map them onto a Product Roadmap using user story mapping and MRF logic.
---

# Step 04: Product Backlog Creation & Roadmapping

This skill controls the execution of the **Step 4 — Product Backlog Creation** workflow. The goal is to translate the prioritized Product Goal into actionable, user-centric Epics and Features, and schedule them empirically on a Product Roadmap.

---

## 0. Backbone & Phase Context
*   **Backbone Step:** Step 4 — Product Backlog Creation
*   **Scrum Flow Phase:** Phase 0 — Initiative (Upstream Scrum Preparation)
*   **Primary Owner:** Product Owner (PO)
*   **Scrum Master Role:** Ensure the backlog remains aligned with the Product Goal and that the roadmap is positioned as an empirical forecast subject to inspection and adaptation.
*   **Target Output Deliverables:**
    *   [A] High-Level Product Backlog
    *   [B] Product Roadmap
    *   [C] Epic/Feature Tree

---

## 1. Phase 1 — Input Quality Gate

### 1.1 Trigger Conditions & Keywords
The Scrum Assistant activates this skill when the user requests a backlog draft, epic list, story map, or roadmap:
*   **English Triggers:** "create backlog", "draft backlog", "high level features", "product roadmap", "draw roadmap", "story mapping", "step 4"
*   **Vietnamese Triggers (Trữ nguyên trạng):** "tạo backlog", "thiết lập backlog", "lập roadmap", "vẽ roadmap", "tạo roadmap", "lập danh sách epics", "phân rã tính năng"

### 1.2 Quality Gate Verification
Before generating any backlog items, the assistant **MUST** verify that:
1.  **A prioritized 1st Product Goal exists** (established in Step 2 / Step 3).
2.  **Strategic context (Impact Map or Business Case)** is available to identify the target actors and behavioral impacts.

*   **IF the Product Goal is missing:**
    *   The assistant **MUST** suspend execution.
    *   Prompt the user: *"Để tránh việc sa vào cái bẫy 'nhà máy tính năng' (feature factory) lãng phí, vui lòng cung cấp Product Goal mà chúng ta đang hướng tới. Nếu chưa có, hãy quay lại Step 03."*
*   **IF the Product Goal is MET:** Proceed to Phase 2.

---

## 2. Phase 2 — Domain Context & Decomposition

### 2.1 On-Demand Reference Pattern
To prevent token bloat during active conversation, the theoretical guidelines for decomposition and roadmapping are stored separately. The assistant **MUST** read these guides on-demand:
1.  **User Story Mapping:** Refer to [references/user-story-mapping-guide.md](references/user-story-mapping-guide.md) to build the horizontal **Backbone** (Key Activities), define the **Walking Skeleton** (Epics), and slice them vertically.
2.  **MRF & Roadmapping:** Refer to [references/mrf-and-roadmapping-guide.md](references/mrf-and-roadmapping-guide.md) to identify **Minimum Releasable Features (MRFs)** and structure releases.

### 2.2 Domain Context Overlay (Optional)
Check if the project is in the iGaming or Online Lottery domain. Ask the user: *"Is this project in the iGaming or Online Lottery domain? (yes/no)"* (or detect from project context).

*   **IF domain is NOT iGaming/Lottery:** Skip this overlay and proceed to Phase 3.
*   **IF domain IS iGaming/Lottery:**
    *   Scan [igaming-context.md](../../reference/igaming-context.md) using keywords matching the product domain (e.g., `sportsbook`, `Kambi`, `casino`, `Pragmatic`, `RTP`, `wallet`, `AML`, `KYC`, `Momo`).
    *   Inject mandatory compliance/integration Epics (e.g., "PAGCOR Geofencing Implementation", "RNG Certification Testing", "Unified Wallet Callback Latency Optimization").

---

## 3. Phase 3 — Output Generation & Self-Audit

### 3.1 Template Catalogue Presentation
The assistant **MUST NOT** generate any deliverables automatically. Present the validated Product Goal and the domain context summary, then display the template catalogue:

```
Inputs validated. I have structured the Story Map Backbone and MRF Release Line.
Please select which deliverable you would like to generate first:

[A] High-Level Product Backlog  → (Ref: templates/high-level-product-backlog.md)
[B] Product Roadmap             → (Ref: templates/product-roadmap.md)
[C] Epic/Feature Tree           → (Ref: templates/epic-feature-tree.md)
[D] User Story Mapping Board    → (Ref: templates/story-mapping-board.md)
```

### 3.2 Output Execution & Audit Rules
Once the user selects an output:
1.  Load the target template file from the `templates/` folder (e.g., [templates/high-level-product-backlog.md](templates/high-level-product-backlog.md) or [templates/story-mapping-board.md](templates/story-mapping-board.md)).
2.  **Quality Gate Audit Rule:** After drafting the High-Level Product Backlog (Template A), the assistant **MUST** read [checklists/deep-quality-gate.md](checklists/deep-quality-gate.md) and perform a silent self-audit against the **DEEP** criteria (Detailed appropriately, Emergent, Estimated, Prioritized).
    *   *Remediation:* If any DEEP criterion fails (e.g., items at the bottom are too detailed, no estimates exist, or ordering does not account for iGaming risks), the assistant **MUST** adjust the draft internally before presenting the clean output to the user.
3.  **Story Splitting Rule:** If an Epic or Feature generated during this step is too large to fit in a Sprint and needs decomposition, the assistant **MUST** invoke the shared story-splitting skill at [../shared/story-splitting/SKILL.md](../shared/story-splitting/SKILL.md).

---

## 4. Readiness Self-Audit

Before returning the generated document to the user, the assistant must verify:
*   Did I use the exact structure defined in the selected template?
*   Are all relative paths formatted using relative links?
*   Did I run the DEEP quality gate checklist and remediate any failures?
*   Are the iGaming compliance and vendor dependencies integrated?
*   Is the content written in professional, Scrum Guide 2020 aligned English?
