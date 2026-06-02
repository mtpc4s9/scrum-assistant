---
description: Quality self-review checklist for validating Agile User Stories and Acceptance Criteria before finalization.
metadata:
  tags: [quality, checklist, user-story, acceptance-criteria, qa]
  source: internal
---

# User Story & Acceptance Criteria Quality Checklist

This checklist is used for self-reviewing User Story specifications before finalizing them. If any item fails, it **MUST** be corrected prior to output submission.

---

## 1. User Story Card Quality

### Persona (As a...)
- [ ] The persona is specific and well-defined (never use a generic "User" or "Everyone").
- [ ] The persona includes state or context descriptions (e.g., "email-verified student", "premium subscriber").
- [ ] The persona is clearly distinguished from other actors in the system (e.g., Student vs. Mentor vs. Administrator).

### Goal (I want to...)
- [ ] Describes a specific, clear, and unambiguous system action.
- [ ] Uses active, precise verbs (e.g., "schedule a mentoring session", "download the PDF certificate").
- [ ] Avoids generic, vague verbs like "manage", "handle", "administer", or "process".
- [ ] It is obvious when the action is "completed" and can be measured.

### Business Value (So that...)
- [ ] Distinctly different from the "I want to..." goal statement.
- [ ] Describes a real business outcome or user benefit, not just another feature.
- [ ] Answers the question: *"What business metric or user value is lost if we do not build this?"*
- [ ] Does not echo or restate the goal.

---

## 2. INVEST Framework Compliance

| Quality Metric | Status Check | Remedy/Action if Failed |
| :--- | :---: | :--- |
| **Independent** | [ ] | Split dependency or merge closely coupled small stories. |
| **Negotiable** | [ ] | Remove rigid technical instructions or pixel-perfect specifications. |
| **Valuable** | [ ] | Rewrite the "So that..." clause to state clear outcome-driven value. |
| **Estimable** | [ ] | Create a research Spike story first or provide missing system constraints. |
| **Small** | [ ] | Split into smaller vertical slices (CRUD, persona, or business rules). |
| **Testable** | [ ] | Formulate Gherkin Acceptance Criteria with objective success metrics. |

*If **Small** fails (e.g., >8 story points or >7 criteria): Split the story immediately.*  
*If **Estimable** fails (e.g., unknown third-party integration): Propose a time-boxed research Spike story first.*

---

## 3. Acceptance Criteria Quality

### Quantity & Boundaries
- [ ] Minimum of three (3) AC scenarios (1 happy path + 1 edge case + 1 negative path).
- [ ] Maximum of seven to eight (7-8) AC scenarios. If more are required, the story is too large and must be split.

### Given-When-Then Structure
- [ ] Every AC is formatted with explicit `Given`, `When`, and `Then` steps.
- [ ] **Given** states a clear, unambiguous initial system state or pre-condition.
- [ ] **When** describes a single, specific action taken by the user.
- [ ] **Then** defines the testable, expected system outcome.

### Scenario Coverage
- [ ] **Happy Path:** At least one scenario demonstrating successful core execution.
- [ ] **Edge Case:** At least one scenario covering boundaries, timeouts, concurrent events, or network drops.
- [ ] **Negative Path:** At least one scenario handling input validation failures, expired tokens, or permission denials.
- [ ] Scenarios cover domain-specific logic (e.g., exceeding mentor booking quotas, license limits, or prerequisite course locks).

### Objective Measurement
- [ ] Uses precise quantitative values (e.g., processing times in seconds, transaction percentage limits).
- [ ] Specifying exact error messages (never use a generic "displays an error").
- [ ] Mapped to clear system states (e.g., status changed to `Enrolled` or `PaymentFailed`).

### Avoid Anti-Patterns
- [ ] **No Vague Adjectives:** Free of words like "fast", "beautiful", "user-friendly", "intuitive", or "appropriate".
- [ ] **No Technical Code:** Free of API endpoints (e.g., `POST /v1/checkout`), database column names, or programming code.
- [ ] **No Rigid UI Layouts:** Free of specific button colors, pixel positions, font sizes, or screen placements.
- [ ] **No Scenario Bundling:** Each AC represents exactly one testable scenario.

---

## 4. Output Formatting & Structure

- [ ] Assigned a unique, consistent ID (e.g., `US-PAY-001`).
- [ ] Complete metadata is provided: Epic/Feature area, Priority (MoSCoW), and Estimate.
- [ ] Contains a complete 6-row INVEST self-check table with status and notes.
- [ ] Acceptance criteria are clearly numbered and named (e.g., `AC1: [Scenario Name]`).
- [ ] Section for "Notes" is included, documenting dependencies, assumptions, and open questions.

---

## 5. Sanity Checks

Before finalization, perform this 5-question sanity check:
1.  **Is it Business-Readable?** Can a non-technical Product Owner or stakeholder read and fully understand it?
2.  **Is it Estimable?** Can a junior developer look at the narrative and constraints and estimate the effort?
3.  **Is it Testable?** Can a QA engineer write at least five distinct manual/automated test cases based on the ACs?
4.  **Is it Unique?** Is there any overlap with other user stories currently in the backlog?
5.  **Is the "So That" Genuine?** Does the value statement represent real impact, or is it just filler text?

---

## 🚨 Red Flags (Halt & Correct Immediately)

*   ❌ Story description exceeds 200 words (violates Negotiability, too detailed).
*   ❌ An AC scenario exceeds 10 lines of steps (violates Small/Testable, too complex).
*   ❌ User Story has zero Acceptance Criteria (violates Testable).
*   ❌ "So that" repeats the action or is empty (violates Valuable).
*   ❌ The Persona is "User", "Client", or "Everyone" (too generic).
*   ❌ Story title contains "AND" (indicates merged requirements).
*   ❌ AC contains vague terms like "etc." or "and so on" (non-testable).

---
*Standardized according to IIBA® BABOK® Guide v3 terminology for Enterprise AI environments.*
