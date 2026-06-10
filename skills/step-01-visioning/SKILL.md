---
name: step-01-visioning
description: Execute Step 1 - Visioning by verifying inputs, optional domain context overlays (e.g. iGaming), and generating product vision boards, elevator pitches, stakeholder maps, and presentation decks.
---

# Step 01: Visioning (Product Vision Creation)

This skill controls the execution of the **Step 1 - Visioning** workflow of the Scrum Flow Backbone. The goal is to establish a shared, clear product vision and identify initial key stakeholders, adaptively aligned with project domain realities.

---

## 0. Backbone & Phase Context
*   **Backbone Step:** Step 1 — Visioning
*   **Scrum Flow Phase:** Phase 0 — Initiative (Upstream Scrum Preparation)
*   **Primary Owner:** Product Owner (PO) in collaboration with Stakeholders & Business Leaders.
*   **Core Objective:** Translate vague concepts into structured, domain-aware vision statements and stakeholder alignments before defining product goals or backlogs.
*   **Input Requirements:** High-level idea or business request.
*   **Target Output Deliverables:** 
    *   [A] Elevator Pitch
    *   [B] Product Vision Board
    *   [C] Initial Stakeholder Map
    *   [D] Product Vision Presentation Deck

---

## 1. Phase 1 — Input Quality Gate

### 1.1 Trigger Conditions & Keywords
The Scrum Assistant activates this skill when the user initiates a new project, requests a product vision, or specifies keywords related to visioning:
*   **English Triggers:** "start new project", "create product vision", "write elevator pitch", "product vision board", "stakeholder map", "define stakeholders", "initiative visioning", "product vision presentation"
*   **Vietnamese Triggers (Trữ nguyên trạng):** "khởi tạo dự án", "thiết lập tầm nhìn", "viết elevator pitch", "product vision board", "bản đồ stakeholder", "stakeholder map", "vẽ bản đồ bên liên quan", "slide trình bày tầm nhìn"

### 1.2 Quality Gate Verification
Upon activation, the assistant must load the input quality gate checklist from [input-readiness.md](checklists/input-readiness.md) and evaluate the user's request against the 5 core criteria:
1.  **Product / Feature Identity** (Is the concept named or clearly described?)
2.  **Target Customer / User Segment** (Who is it for?)
3.  **Core Problem / Opportunity** (What pain point is being resolved?)
4.  **Business Goal / Value Drivers** (What is the success metric or business objective?)
5.  **Domain / Regulatory Boundary** (Is the jurisdictional scope or constraint stated, or explicitly marked as none?)

### 1.3 Discovery Loop Rule
*   **IF any of the 5 criteria are NOT MET:**
    *   The assistant **MUST** suspend the visioning execution.
    *   Load and execute the Product Discovery skill located at [../shared/product-discovery/SKILL.md](../shared/product-discovery/SKILL.md).
    *   Engage the user in an iterative interview, asking a maximum of 3-5 high-context questions per turn.
    *   Update the [input-readiness.md](checklists/input-readiness.md) checklist dynamically as the user provides answers.
    *   **Loop Rule:** Continue the discovery cycle until all 5 criteria are marked as **MET**.
*   **IF all 5 criteria are MET:**
    *   Proceed directly to Phase 2 (Domain Context Overlay).

---

## 2. Phase 2 — Domain Context Overlay (Optional)

Before proceeding, the assistant MUST check if the project is in the iGaming or Online Lottery domain. Ask the user: *"Is this project in the iGaming or Online Lottery domain? (yes/no)"* (or detect from project context).

*   **IF the domain is NOT iGaming/Lottery:** Skip this phase entirely and proceed directly to Phase 3.
*   **IF the domain IS iGaming/Lottery:** Execute the following scan protocol:

### 2.1 Keyword-Scoped Reading Strategy
To optimize token efficiency and maintain strict context focus, the assistant **MUST NOT** read the entire `igaming-context.md` file. Instead, follow this protocol:
1.  **Extract Keywords:** Identify 2-4 key domain terms from the Phase 1 inputs (e.g., "sports betting" -> `sportsbook`, `Kambi`; "slot game" -> `casino`, `Pragmatic Play`, `RTP`; "lottery" -> `lottery`, `Decree 30`; "deposit/withdrawal" -> `wallet`, `payment`, `Momo`, `KYC`, `AML`).
2.  **Targeted Scan:** Open [igaming-context.md](../../reference/igaming-context.md) and scan **only** the sections with headings matching the extracted keywords.
3.  **Compile Internal Context:** Summarize internally (do not output immediately to the user):
    *   **1-3 Regulatory Constraints** (e.g., age verification check, transaction betting caps under Vietnam Decree 06, PAGCOR geofencing).
    *   **1-2 Technical Risks** (e.g., database concurrency on wallets, Kambi callback latency, RNG certification needs).

---

## 3. Phase 3 — Output Generation & Techniques

### 3.1 On-Demand Reference Pattern
To prevent token bloat, the theoretical and practical guidelines for analyzing ideas via the Lean Business Model Canvas are stored separately.
*   **Action:** When analyzing the raw product idea, the assistant **MUST** refer to the on-demand technique sheet at [references/lean-business-model-canvas-guide.md](references/lean-business-model-canvas-guide.md) to dissect the idea into customer segments, problems, value propositions, metrics, and cost structures before synthesizing outputs.

### 3.2 Template Catalogue Presentation
The assistant **MUST NOT** generate any deliverables automatically. Instead, present the verified checklist and the compiled domain insights to the user, then display the template catalogue:

```
Inputs validated. I have prepared the iGaming context overlay (Regulatory constraints & Technical risks).
Please select which deliverable you would like to generate first:

[A] Elevator Pitch                 → (Ref: templates/elevator-pitch.md)
[B] Product Vision Board           → (Ref: templates/product-vision-board.md)
[C] Initial Stakeholder Map        → (Ref: templates/initial-stakeholder-map.md)
[D] Product Vision Presentation    → (Ref: templates/product-vision-deck.md)
```

### 3.3 Output Execution & Enrichment Rules
Once the user specifies a selection (e.g., "Generate [A]" or "Làm Slide trình bày tầm nhìn"):
1.  Load the target template file from the `templates/` folder (e.g., [templates/elevator-pitch.md](templates/elevator-pitch.md)).
2.  Follow the **AGENT DIRECTIVE** instructions inside the loaded template precisely.
3.  **Enrichment Rule:** Integrate the regulatory constraints and technical risks compiled in Phase 2 into the respective sections of the output:
    *   For **Elevator Pitch**: Incorporate constraints into the "Unlike [existing alternatives]" or product characteristics.
    *   For **Product Vision Board**: List regulatory limits under "Constraints" and technical risks under "Cost Factors & Feasibility".
    *   For **Initial Stakeholder Map**: Ensure compliance officers, regulatory bodies (e.g., PAGCOR, Vietnamese Ministry of Finance), and integration vendors (e.g., Kambi, Pragmatic Play) are mapped as key external stakeholders with appropriate influence ratings.
    *   For **Product Vision Presentation**: Load [templates/product-vision-deck.md](templates/product-vision-deck.md), populate all slides, and ensure the iGaming regulatory and tech risks compiled in Phase 2 are detailed on Slide 7 (Feasibility & Risks).

---

## 4. Readiness Self-Audit

Before returning the generated document to the user, the assistant must verify:
*   Did I use the exact structure defined in the selected template?
*   Are all relative paths formatted using relative links?
*   Did I enrich the output with the specific iGaming regulations and technical vendor integration risks identified in Phase 2?
*   Is the content written in professional, Scrum Guide 2020 aligned English?
