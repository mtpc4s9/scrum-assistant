---
name: step-06-standards-setup
description: Execute Step 6 — Standards Setup by defining the Scrum Team's foundational operating agreements (Definition of Ready, Definition of Done, and Working Agreements / Team Norms) before Sprint 1 commences.
---

# Step 06: Standards Setup (DoR · DoD · Working Agreements)

This skill controls the execution of the **Step 6 — Standards Setup** workflow. The goal is to establish the three foundational quality and behavioural standards that every Scrum Team must commit to before entering the Sprint Loop. These artefacts are not bureaucratic documents — they are empirical commitments to transparency, quality, and self-management.

---

## 0. Backbone & Phase Context

*   **Backbone Step:** Step 6 — Standards Setup
*   **Scrum Flow Phase:** Phase 0 — Initiative (Upstream Scrum Preparation)
*   **Primary Owner:** Scrum Master (facilitates); the entire Scrum Team authors and owns the outputs
*   **Target Output Deliverables:**
    *   [A] Definition of Ready (DoR)
    *   [B] Definition of Done (DoD)
    *   [C] Team Norms (Working Agreements) — Core Document
    *   [D] Team Norms — Presentation Deck (PPTX-friendly outline for team sign-off ceremony)

---

## 1. Phase 1 — Input Quality Gate

### 1.1 Trigger Conditions & Keywords

The Scrum Assistant activates this skill when the user requests foundational team standards, quality agreements, or working norms before Sprint 1:

*   **English Triggers:** `"standards setup"`, `"step 6"`, `"definition of done"`, `"definition of ready"`, `"DoD"`, `"DoR"`, `"working agreements"`, `"team norms"`, `"team standards"`
*   **Vietnamese Triggers (Giữ nguyên trạng):** `"tiêu chuẩn sẵn sàng"`, `"tiêu chuẩn hoàn thành"`, `"quy tắc làm việc"`, `"thỏa thuận nhóm"`, `"chuẩn bị sprint"`, `"định nghĩa xong"`, `"định nghĩa sẵn sàng"`

### 1.2 Quality Gate Verification

Upon activation, load [checklists/input-readiness.md](checklists/input-readiness.md) and evaluate the user's context against the 4 core criteria:

1.  **C1 — Team Composition & Capabilities:** Are the team size, roles, and cross-functional skills (QA, Backend, UX, DBA, etc.) clearly identified?
2.  **C2 — Operational Environment:** Is the working model defined (co-located vs. distributed, time zones, core overlapping hours)?
3.  **C3 — Technical & Automation Readiness:** Are the engineering tooling constraints (CI/CD status, automated testing capabilities, code review workflow) known?
4.  **C4 — Regulatory & Domain Quality Baselines:** Are mandatory iGaming compliance checks (RTP validation, KYC steps, RNG certification) identified for inclusion in quality standards?

### 1.3 Discovery Loop Rule

*   **IF the request is for a single specific artefact (e.g., "Give me the DoD"):**
    *   The assistant MAY generate that single artefact without requiring all 4 criteria to be met, provided the criteria directly relevant to that artefact are satisfied.
    *   *Example: Generating the DoD requires C3 (Technical Readiness) and C4 (Compliance Baselines) to be MET. C1 and C2 are optional for DoD but required for Team Norms.*
*   **IF any relevant criterion is NOT MET:**
    *   The assistant **MUST** suspend draft generation.
    *   Open a targeted clarification session: *"To ensure the [DoD / DoR / Team Norms] is realistic and applicable to your team, I need additional context regarding [Criterion Name]. Could you describe your team's [specific gap]? Generating standards without this context risks producing agreements the team cannot actually honour, which violates Empirical Process Control."*
    *   Alternatively, call [../shared/product-discovery/SKILL.md](../shared/product-discovery/SKILL.md) to conduct a structured discovery interview.
*   **IF all relevant criteria are MET:**
    *   Proceed directly to Phase 2 (Domain Overlay & Validation).

---

## 2. Phase 2 — Domain Overlay & Standards Calibration (Optional Domain Scan)

Once the quality gate is cleared, the assistant performs a domain-aware calibration before generating any artefact.

### 2.1 Domain Scan (Optional)
Check if the project is in the iGaming or Online Lottery domain. Ask the user: *"Is this project in the iGaming or Online Lottery domain? (yes/no)"* (or detect from project context).

*   **IF domain is NOT iGaming/Lottery:** Skip this domain scan and proceed directly to 2.2 Socratic Validation Layer.
*   **IF domain IS iGaming/Lottery:**
    1.  **Extract Keywords:** Identify domain-specific terms from the user's context (e.g., `Kambi`, `Pragmatic Play`, `PAGCOR`, `Decree 06`, `Vietlott`, `Momo`, `KYC`, `RNG`, `PAM`).
    2.  **Scan iGaming Context:** Open [../../reference/igaming-context.md](../../reference/igaming-context.md) and read **only** the sections with headings matching the extracted keywords.
    3.  **Inject Domain Constraints:** Determine which iGaming-specific quality checks must be embedded in the DoD (e.g., RTP validation, RNG fairness certification, transaction cap enforcement) and which must appear in the DoR (e.g., "Compliance impact assessed by Legal prior to sprint pull-in").

### 2.2 Socratic Validation Layer

Before generating the artefact, the assistant **MUST** challenge any unrealistic inputs:

*   **DoD Anti-Pattern Check:** If the user states the team has no automation but requests "100% automated test coverage" in the DoD, the assistant **MUST** pause: *"I notice your team currently lacks an automated testing pipeline. Setting 100% automation in the initial DoD may prevent the team from ever delivering a 'Done' Increment. Should we start with a manual baseline and add an Improvement Backlog item to build automation incrementally?"*
*   **Team Norms Anti-Punitive Check:** If the user attempts to include punitive rules (e.g., fines for being late), the assistant **MUST** reject them by referencing the Scrum Value of **Respect** and the blame-free environment principle.
*   **DoR Anti-Contract Check:** If the user applies DoR as a mandatory phase gate (blocking all PBIs without 100% criteria met), the assistant **MUST** clarify: *"The DoR is a collaborative guideline, not a rigid Waterfall gate. If the Developers and Product Owner share a clear understanding of an item, it may enter the Sprint even if the checklist is not perfectly complete."*

### 2.3 On-Demand Reference Loading

Reference guides are stored separately to keep this orchestrator context-lean. Load them **only when performing the corresponding generation task:**

| Artefact to Generate | Reference Guide to Load |
| :--- | :--- |
| Definition of Ready (DoR) | [references/definition-of-ready-guide.md](references/definition-of-ready-guide.md) |
| Definition of Done (DoD) | [references/definition-of-done-guide.md](references/definition-of-done-guide.md) |
| Team Norms / Working Agreements | [references/team-norm-guide.md](references/team-norm-guide.md) |

---

## 3. Phase 3 — Output Generation

### 3.1 Template Catalogue Presentation

The assistant **MUST NOT** auto-generate all artefacts simultaneously. After Phase 2 validation, present the template catalogue and wait for the user's explicit selection:

```
Quality gate cleared. Team context and domain constraints have been calibrated.
Please select which standard to generate:

[A] Definition of Ready (DoR)         → templates/definition-of-ready.md
[B] Definition of Done (DoD)          → templates/definition-of-done.md
[C] Team Norms — Core Document        → templates/team-norm.md
[D] Team Norms — Presentation Deck    → templates/team-norm-presentation-deck.md
```

### 3.2 Output Execution Rules

Once the user selects a deliverable:

1.  Load the corresponding on-demand reference guide from Section 2.3.
2.  Load the target template file from the `templates/` directory.
3.  Follow the **AGENT DIRECTIVE** embedded inside the template precisely.
4.  **iGaming Enrichment:** Inject domain-specific checks from Section 2.1 into the appropriate sections of the generated artefact.
5.  **Mandatory Disclaimer:** Every generated artefact must be prefaced with a clear statement that it is a **baseline draft** requiring collaborative team review, consensus, and formal sign-off before becoming a binding agreement.
6.  **Socratic Closing Prompt:** After each generated artefact, append a facilitation prompt to trigger team reflection (per the guide's directive). Do not present the artefact as a finished product.

### 3.3 Team Norms Sign-Off Protocol

When generating the Team Norms Presentation Deck [D]:

*   Confirm with the user whether the sign-off ceremony will be **in-person** or **remote** (digital signature tool required).
*   Remind the user that the document becomes valid **only** when all Scrum Team members (Product Owner, Scrum Master, and all Developers) have reviewed, contributed to, and formally signed or acknowledged it.
*   Note that these norms must be **inspected and adapted** at every Sprint Retrospective.

---

## 4. Readiness Self-Audit

Before returning the generated document to the user, the assistant must verify:

*   Did I use the exact structure defined in the selected template?
*   Did I inject relevant iGaming domain constraints identified in Phase 2?
*   Did I include the mandatory baseline disclaimer?
*   Did I append the Socratic closing prompt to encourage team dialogue?
*   Are all relative paths formatted using relative links (no absolute paths)?
*   Is the content written in professional, Scrum Guide 2020-aligned English?
