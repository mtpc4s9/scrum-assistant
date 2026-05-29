---
name: ba-user-stories
description: Use when writing, refining, or evaluating Agile User Stories and Gherkin-style Given-When-Then Acceptance Criteria in the iGaming or online Lottery domain.
---

# User Stories & Acceptance Criteria (BABOK 10.48)

This sub-skill provides comprehensive, BABOK-aligned structured guidelines for drafting, refining, and validating high-quality User Stories and Gherkin-style Acceptance Criteria (AC). It integrates standard product requirements with iGaming-specific transaction, compliance, and lottery rules.

---

## 1. Operating Modes for AI Agent

When Chàng triggers this technique, the agent **MUST** operate in one of the following three distinct modes. Determine the mode based on Chàng's prompt:

*   **Mode A — Generation from Scratch:** Chàng provides a gaming/lottery feature description, compliance PRD, or business requirement, and you generate the complete User Story list, Card narratives, and Gherkin ACs.
*   **Mode B — Refinement & Review:** Chàng provides an existing User Story, and you evaluate it against the **INVEST** quality framework, highlighting gaps and providing a revised, iGaming-ready version.
*   **Mode C — Elicitation of Acceptance Criteria:** Chàng has a stable User Story card but needs detailed, testable Gherkin-style Acceptance Criteria.

---

## 2. Core Operating Rules & Instructions

### Step 1: Input Elicitation (Zero Guessing Rule)
Before drafting a User Story, you **MUST** ensure the following inputs are available in the context. If any are missing, **STOP** and ask Chàng to provide them (never assume business logic):
1.  **Target Persona/User Role:** (e.g., "Registered Lottery Player", "Risk Officer", "Game Engine Client").
2.  **User Goal:** What specific system action does the persona want to perform?
3.  **Business Value:** What benefit or regulatory compliance goal does it deliver?
4.  **Context/Scope:** epic, module, or database/wallet boundaries impacted.

### Step 2: Draft the Narrative Card
Follow the standard three-part Agile card structure:
```text
**US-[ID]**: [Short, Descriptive Title]

**As a** [specific user persona / system actor]
**I want to** [perform a specific, measurable system action]
**So that** [achieve a clear business outcome, player benefit, or compliance goal]
```
*   **⚠️ SHARP NEGATIVE CONSTRAINT:** The "So that..." clause **MUST** express a real business outcome or regulatory compliance value. Never repeat the action (e.g., *Wrong:* "So that I can enter my DOB." *Right:* "So that the system can verify my age against local lottery license gates before allowing play.").

### Step 3: Apply the INVEST Framework
Self-evaluate the drafted story against the 6 INVEST quality criteria. For detailed definitions and splitting strategies, consult:
*   [INVEST Criteria Details](file:///C:/Users/TruongPhan/.gemini/antigravity/scratch/scrum-assistant/skills/po-ba/ba-user-stories/references/invest-criteria.md)

### Step 4: Generate Given-When-Then Acceptance Criteria
Each User Story **MUST** have a minimum of **three (3) distinct Gherkin scenarios**:
1.  **Scenario 1 (Happy Path):** The successful execution of the core transaction.
2.  **Scenario 2 (Edge Case / Validation):** Gating, geofencing, or validation bounds.
3.  **Scenario 3 (Negative Path / Error):** Transaction failovers, rollbacks, or blocked states.

Use the strict Gherkin format:
```text
**AC[Number]: [Scenario Name]**
- **Given** [specific initial context, wallet state, or player location]
- **When** [the specific action taken by the player or system trigger]
- **Then** [the testable system ledger updates, UI changes, or audit logs]
- **And** [additional minor outcomes, if applicable]
```
*   *Detailed Quality Checklist:* [Acceptance Criteria Quality Checklist](file:///C:/Users/TruongPhan/.gemini/antigravity/scratch/scrum-assistant/skills/po-ba/ba-user-stories/checklists/quality-checklist.md)

---

## 3. iGaming & Online Lottery Special Rules

When writing stories in this domain, you **MUST** ensure the following rules are incorporated into the Business Rules and Acceptance Criteria:

1.  **Ledger Atomicity (Transaction Lock):** Real-money wagers and payouts must be atomic. Write Gherkin steps to show balance locking, database row locks, and ledger status writes. Refer to:
    *   [iGaming Wallet Context](file:///C:/Users/TruongPhan/.gemini/antigravity/scratch/scrum-assistant/reference/igaming-context.md)
2.  **Regulatory & Limit Gating:** Incorporate Geofencing coordinates and Responsible Gaming limit checks (deposits, wagers, loss limits) directly into preconditions (`Given`).
3.  **Game Rules & RTP Conformity:** Ensure lottery ticket prices and win distributions match the paytable hit frequencies. Refer to:
    *   [Lottery Rules & RTP Template](file:///C:/Users/TruongPhan/.gemini/antigravity/scratch/scrum-assistant/reference/game-rules-math-sheet.md)
4.  **Integration SLA and Failover:** Scenarios must document retry and rollback logic when Sportbook (Kambi), Casino (Pragmatic), or webhooks (MoMo, Crypto) timeout. Refer to:
    *   [3rd Party Integration Matrix](file:///C:/Users/TruongPhan/.gemini/antigravity/scratch/scrum-assistant/reference/third-party-integration-matrix.md)

---

## 4. Reference Material & Supporting Assets

*   **Templates:** Use the pre-structured [Agile User Story Specification Template](file:///C:/Users/TruongPhan/.gemini/antigravity/scratch/scrum-assistant/skills/po-ba/ba-user-stories/templates/user-story-specification.md) to format your final deliverable.
*   **Production Examples:** Read [High-Fidelity User Story Examples](file:///C:/Users/TruongPhan/.gemini/antigravity/scratch/scrum-assistant/skills/po-ba/ba-user-stories/references/examples.md) to review industry-standard stories.
*   **Quality Checklist:** Review the [Quality Self-Checklist](file:///C:/Users/TruongPhan/.gemini/antigravity/scratch/scrum-assistant/skills/po-ba/ba-user-stories/checklists/quality-checklist.md) before final submission.
