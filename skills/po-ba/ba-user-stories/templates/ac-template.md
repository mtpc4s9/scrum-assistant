---
description: Standalone template for drafting testable, Gherkin-style (Given-When-Then) Acceptance Criteria.
metadata:
  tags: [template, gherkin, acceptance-criteria, agile]
  source: internal
---

# Acceptance Criteria Template (Gherkin Syntax)

This standalone template is used when you already have a stable User Story card (Mode C) and only need to draft, refine, or expand its specific Acceptance Criteria (AC).

*Rule: Provide a minimum of three distinct scenarios covering the Happy Path, Edge Case, and Negative/Error Path.*

---

## US-[ID] Acceptance Criteria Specification

### AC1: [Scenario Name - Happy Path]
*   **GIVEN** [specific pre-condition or initial system state]
*   **AND** [additional pre-condition, if applicable]
*   **WHEN** [the primary user/actor trigger action occurs]
*   **THEN** [the expected measurable system response or outcome]
*   **AND** [any secondary outcomes or UI states]

---

### AC2: [Scenario Name - Edge Case / Validation]
*   **GIVEN** [boundary pre-condition or specific business rule constraint]
*   **WHEN** [the actor takes the trigger action]
*   **THEN** [the system validates and enforces the rule correctly]
*   **AND** [provides clear, specific feedback/error styling to the actor]

---

### AC3: [Scenario Name - Negative Path / Error Handling]
*   **GIVEN** [error pre-condition, e.g., expired state or invalid credentials]
*   **WHEN** [the actor attempts the trigger action]
*   **THEN** [the system blocks the action and handles the error gracefully]
*   **AND** [displays a descriptive error message without undesired side-effects]

---

## 📋 Pre-Commit Quality Checklist

Before finalizing these criteria, ensure they pass the following checks:

- [ ] **Single Focus:** Each AC scenario tests exactly one specific path/behavior.
- [ ] **Measurable Steps:** Every `Given`, `When`, and `Then` statement is objective and quantifiable.
- [ ] **No Subjectivity:** Free of vague words like "fast", "beautiful", "user-friendly", or "appropriate".
- [ ] **Technology-Free:** No technical implementation details (no API paths, database tables, or framework names).
- [ ] **UI-Abstract:** Avoids describing specific colors, pixel placements, or font sizes (focus on functional outcomes).
- [ ] **Coverage:** Contains at least 1 Happy Path + 1 Edge Case + 1 Negative Path.
- [ ] **Testable:** A QA engineer can immediately write a test case from these criteria.

---
*Standardized according to IIBA® BABOK® Guide v3 terminology for Enterprise AI environments.*
