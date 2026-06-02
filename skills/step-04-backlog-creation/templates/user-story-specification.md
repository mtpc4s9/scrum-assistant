---
description: Blank template for Agile User Story Narrative and Gherkin-style Given-When-Then Acceptance Criteria.
metadata:
  tags: [template, agile, user-story, acceptance-criteria]
  source: internal
---

# Agile User Story Specification Template

This template consolidates both the User Story Narrative Card and Gherkin Acceptance Criteria. Use it to specify features ready for development and QA testing.

---

## US-[epic-code]-[number]: [Descriptive Title]

### 1. User Story Card (Narrative)
*   **AS A:** [Specific, well-defined user persona or system actor]
*   **I WANT TO:** [Perform a specific, measurable system action]
*   **SO THAT:** [Achieve a clear business outcome or user benefit — DO NOT repeat the action]

---

### 2. Specification Metadata
*   **Epic/Feature Module:** [e.g., Customer Checkout & Payments]
*   **Priority:** [Must Have / Should Have / Could Have / Won't Have — MoSCoW]
*   **Estimate:** [e.g., 3 Story Points / Small]
*   **Dependencies:** [e.g., US-AUTH-03 (User Registration must be complete)]
*   **Assumptions:** [e.g., Payment gateway supports sandbox testing token exchange]

---

### 3. INVEST Quality Check

Evaluate the story narrative against the six quality criteria:

| Criteria | Status (✅/⚠️) | Remedy/Note (If ⚠️, what must be updated) |
| :--- | :---: | :--- |
| **I**ndependent | | |
| **N**egotiable | | |
| **V**aluable | | |
| **E**stimable | | |
| **S**mall | | |
| **T**estable | | |

---

### 4. Acceptance Criteria (Gherkin Format)

*Provide a minimum of three scenarios covering happy, edge, and negative paths.*

#### AC1: [Scenario Name - Happy Path]
*   **GIVEN** [specific pre-condition or initial system state]
*   **AND** [additional pre-condition, if applicable]
*   **WHEN** [the actor takes the primary trigger action]
*   **THEN** [the expected measurable system response or outcome]
*   **AND** [any secondary visible outcomes]

#### AC2: [Scenario Name - Edge Case / Validation]
*   **GIVEN** [boundary pre-condition or specific business rule constraint]
*   **WHEN** [the actor takes the trigger action]
*   **THEN** [the system validates and enforces the rule correctly]
*   **AND** [provides specific feedback/message to the actor]

#### AC3: [Scenario Name - Negative Path / Error Handling]
*   **GIVEN** [error pre-condition, e.g., expired state or invalid credentials]
*   **WHEN** [the actor attempts the trigger action]
*   **THEN** [the system blocks the action and handles the error gracefully]
*   **AND** [displays a descriptive error message without undesired side-effects]

---

### 5. Notes & Open Questions
*   [e.g., Awaiting final UX/UI wireframe confirmation for the card entry modal]
*   [e.g., Confirm if gateway supports dynamic currency conversion at checkout]

---
