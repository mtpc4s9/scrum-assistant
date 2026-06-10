---
name: step-02-goal-setting
description: Execute Step 2 - Goal Setting by validating vision inputs, applying on-demand Impact Mapping logic, and generating a measurable Product Goal and Impact Map.
---

# Step 02: Goal Setting (Product Goal Definition)

This skill controls the execution of the **Step 2 - Goal Setting** workflow. The goal is to translate a broad Product Vision into a singular, measurable Product Goal and use Impact Mapping to identify the behavioral changes (Impacts) needed to achieve it.

---

## 0. Backbone & Phase Context
*   **Backbone Step:** Step 2 — Goal Setting
*   **Scrum Flow Phase:** Phase 0 — Initiative (Upstream Scrum Preparation)
*   **Primary Owner:** Product Owner (PO)
*   **Scrum Master Role:** Ensure the PO communicates the Goal explicitly and that it is empirically testable and aligned with Scrum Guide 2020 standards.
*   **Target Output Deliverables:**
    *   [A] Product Goal Statement
    *   [B] Impact Map

---

## 1. Phase 1 — Input Quality Gate

### 1.1 Trigger Conditions & Keywords
The Scrum Assistant activates this skill when the user requests a product goal, seeks to define success metrics, or initiates an impact map:
*   **English Triggers:** "set product goal", "create impact map", "define product goal", "product goal statement", "goal setting"
*   **Vietnamese Triggers (Trữ nguyên trạng):** "thiết lập mục tiêu sản phẩm", "vẽ impact map", "xác định product goal", "thiết lập product goal", "lập bản đồ tác động", "vẽ bản đồ tác động"

### 1.2 Quality Gate Verification
Upon activation, the assistant must load the input quality gate checklist from [input-readiness.md](checklists/input-readiness.md) and evaluate the user's request against the 4 core criteria:
1.  **Product Vision Alignment** (Is there a valid Product Vision statement from Step 1?)
2.  **The WHY (Business Problem/Opportunity)** (Is there a clear business objective instead of just a feature list?)
3.  **The WHO (Target Stakeholders)** (Are the key actors whose behaviors need to change identified?)
4.  **Measurability & EBM** (Are there quantifiable Evidence-Based Management metrics proposed to measure success?)

### 1.3 Discovery Loop Rule
*   **IF any of the 4 criteria are NOT MET:**
    *   The assistant **MUST** suspend the goal setting execution.
    *   Load and execute the Product Discovery skill located at [../shared/product-discovery/SKILL.md](../shared/product-discovery/SKILL.md).
    *   Engage the user in an iterative interview, asking a maximum of 3-5 high-context questions per turn.
    *   Update the [input-readiness.md](checklists/input-readiness.md) checklist dynamically as the user provides answers.
    *   **Loop Rule:** Continue the discovery cycle until all 4 criteria are marked as **MET**.
*   **IF all 4 criteria are MET:**
    *   Proceed directly to Phase 2 (Domain Context Overlay).

---

## 2. Phase 2 — Domain Context Overlay (Optional)

Before proceeding, the assistant MUST check if the project is in the iGaming or Online Lottery domain. Ask the user: *"Is this project in the iGaming or Online Lottery domain? (yes/no)"* (or detect from project context).

*   **IF the domain is NOT iGaming/Lottery:** Skip this phase entirely and proceed directly to Phase 3.
*   **IF the domain IS iGaming/Lottery:** Execute the following scan protocol:

### 2.1 Keyword-Scoped Reading Strategy
To optimize token efficiency and maintain strict context focus, the assistant **MUST NOT** read the entire `igaming-context.md` file. Instead, follow this protocol:
1.  **Extract Keywords:** Identify 2-4 key domain terms from the Phase 1 inputs (e.g., `AML`, `KYC`, `Responsible Gaming limits`, `lottery`, `withdrawal`, `wallet`, `Kambi`, `Pragmatic`).
2.  **Targeted Scan:** Open [igaming-context.md](../../reference/igaming-context.md) and scan **only** the sections with headings matching the extracted keywords.
3.  **EBM Metric Alignment:** Identify 2-3 Evidence-Based Management (EBM) metrics suitable for the iGaming context:
    *   *Current Value (CV):* e.g., Player Retention Rate, Net Promoter Score.
    *   *Ability to Innovate (A2I):* e.g., Feature Usage Index, Defect Rate.
    *   *Time to Market (T2M):* e.g., Deployment Frequency, Release Lead Time.

---

## 3. Phase 3 — Output Generation & Techniques

### 3.1 On-Demand Reference Pattern
To prevent token bloat, the theoretical and practical guidelines for performing Impact Mapping are stored separately. 
*   **Action:** When executing the mapping logic, the assistant **MUST** refer to the on-demand technique sheet at [references/impact-mapping-guide.md](references/impact-mapping-guide.md) to align its logic with the `WHY -> WHO -> HOW -> WHAT` relationship model.

### 3.2 Template Catalogue Presentation
The assistant **MUST NOT** generate any deliverables automatically. Instead, present the verified checklist and the compiled domain insights to the user, then display the template catalogue:

```
Inputs validated. I have prepared the domain context overlay (EBM metrics & optional constraints).
Please select which deliverable you would like to generate first:

[A] Product Goal Statement   → (Ref: templates/product-goal-statement.md)
[B] Impact Map               → (Ref: templates/impact-map.md)
[C] Impact Mapping Canvas    → (Ref: templates/impact-mapping-canvas.md)
```

### 3.3 Output Execution & Enrichment Rules
Once the user specifies a selection:
1.  Load the target template file from the `templates/` folder (e.g., [templates/product-goal-statement.md](templates/product-goal-statement.md) or [templates/impact-mapping-canvas.md](templates/impact-mapping-canvas.md)).
2.  Follow the **AGENT DIRECTIVE** instructions inside the loaded template precisely.
3.  **Enrichment Rule:** Integrate the regulatory constraints and EBM metrics compiled in Phase 2 into the respective sections of the output:
    *   For **Product Goal Statement**: Formulate the commitment using SMART criteria, and define success metrics using EBM indicators.
    *   For **Impact Map**: Link every Deliverable (WHAT) back to a behavioral impact (HOW) of a specific actor (WHO). Ensure iGaming technical/regulatory compliance actors (e.g., Compliance Auditors, KYC API providers) are included. Eliminate any orphaned features.

---

## 4. Readiness Self-Audit

Before returning the generated document to the user, the assistant must verify:
*   Did I use the exact structure defined in the selected template?
*   Are all relative paths formatted using relative links?
*   Did I enrich the output with the specific iGaming regulations and EBM metrics identified in Phase 2?
*   Is the Product Goal single, clear, and testable?
*   Does the Impact Map maintain strict logical linkage without orphaned features?
*   Is the content written in professional, Scrum Guide 2020 aligned English?