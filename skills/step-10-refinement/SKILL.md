---
name: step-10-refinement
description: Orchestrates Step 10 - Product Backlog Refinement. Facilitates Three Amigos discussions, evaluates DoR readiness, and delegates oversized or ambiguous items to shared story splitting or US writing skills.
---

# Step 10: Product Backlog Refinement (Orchestrator)

This skill serves as the central cognitive router for Refinement. It does NOT generate final templates directly. Instead, it evaluates Product Backlog Items (PBIs) and intelligently delegates execution to specialized shared skills (Story Splitting or User Story Writer).

--------------------------------------------------------------------------------

## 0. Backbone & Phase Context
*   **Backbone Step:** Step 10 — Product Backlog Refinement (Ongoing)
*   **Scrum Flow Phase:** Phase 1 — Sprint Loop
*   **Primary Owner:** Product Owner (accountable); Developers collaborate.
*   **Core Objective:** Ensure upcoming PBIs meet the Definition of Ready (DoR) through sizing, splitting, and clarifying Acceptance Criteria.
*   **Architectural Role:** Orchestrator. Relies on `../shared/` skills for final artifact generation.

--------------------------------------------------------------------------------

## 1. Intent Detection & Routing Logic
The Agent MUST detect intent and route to the appropriate validation or delegation mode:
*   **Mode A (Readiness Audit):** 
    *   *Keywords:* "is this ready", "check dor", "đánh giá thẻ này", "thẻ này ready chưa".
    *   *Action:* Silently load `checklists/dor-readiness-check.md` and evaluate the PBI.
*   **Mode B (Story Splitting Handoff):** 
    *   *Keywords:* "too big", "split this epic", "tách thẻ", "chia nhỏ story".
    *   *Action:* Silently load `references/story-splitting-guide.md` to confirm it's a valid split request, then trigger `../shared/story-splitting/SKILL.md`.
*   **Mode C (Three Amigos & US Generation Handoff):** 
    *   *Keywords:* "write acceptance criteria", "clarify this story", "viết AC", "làm rõ thẻ này", "viết user story".
    *   *Action:* Silently load `references/three-amigos-bdd-guide.md`. Facilitate a Q&A to gather Business, Dev, and QA perspectives. Once answered, package the context and trigger `../shared/user-story-writing/SKILL.md`.

--------------------------------------------------------------------------------

## 2. Execution Guardrails
1.  **No Duplicate Templates:** The Step 10 Agent MUST NOT attempt to format the final User Story or BDD scenarios itself. Always hand off to the [user-story-writing](../shared/user-story-writing/SKILL.md) skill.
2.  **No Technical Slicing:** When directing a split, remind the user that splitting must deliver a vertical slice of value, not a technical layer (e.g., UI only or DB only).
3.  **Continuous Alignment:** Once a shared skill returns a generated artifact, the Step 10 Agent resumes control, asking the Scrum Team: *"Does this refined item now meet our Definition of Ready for the upcoming Sprint?"*
