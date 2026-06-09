---
artifact_name: DoR Readiness AI Evaluation Check
purpose: Provide the AI Agent with a strict diagnostic evaluation tool to assess if a Product Backlog Item (PBI) meets the Definition of Ready. It seamlessly bridges gap between raw requirements and Sprint-ready items by triggering Story Splitting if an item is deemed too large.
---

### 🤖 AGENT DIRECTIVE (EVALUATION LOGIC)
When asked to verify if a PBI is "Ready", or when finalizing a refinement session, the AI Agent MUST silently execute this 4-gate validation based on the team's Definition of Ready.

#### GATE 1: VALUE & CLARITY (THE "WHY" AND "WHAT")
*   **Check:** Is the business value explicitly articulated? Does the format follow standard user story guidelines (Role-Feature-Benefit)?
*   **Action if Failed:** Ask the **Product Owner** to clarify the "So that..." (Value) clause. A PBI without business value is waste.

#### GATE 2: ACCEPTANCE CRITERIA (THE BOUNDARIES)
*   **Check:** Does the PBI have clear, testable Acceptance Criteria? Are they ideally formatted in BDD/Gherkin (Given/When/Then)?
*   **Action if Failed:** Prompt the user to collaboratively define Acceptance Criteria using the "Three Amigos" approach (Business, Dev, QA perspectives).

#### GATE 3: SIZE & SPLITTING (THE INVEST RULE)
*   **Check:** Has the item been sized by the **Developers**? Is it small enough to comfortably fit within a single **Sprint**?
*   **Action if Failed (Crucial):** If the item is marked as an Epic, lacks an estimate, or the user indicates "it's too big", the Agent MUST immediately invoke `../shared/story-splitting/SKILL.md`. 
    *   *Prompt:* "This item appears too large to fit in a single Sprint, violating our DoR. Would you like me to analyze it using the 9 splitting patterns (e.g., split by workflow, by data variation, or happy/unhappy path) to break it down?"

#### GATE 4: DEPENDENCIES & DOMAIN CONSTRAINTS (iGAMING)
*   **Check:** Are all technical and regulatory dependencies explicitly resolved or managed?
    *   *iGaming checks:* Is RNG logic approved? Are 3rd-party integration stubs (e.g., Kambi/Pragmatic) ready? Are compliance limits (Decree 06) verified?
*   **Action if Failed:** Flag the item as `[BLOCKED]` in the **Product Backlog** and do not mark it as Ready.

---
### ⚠️ THE READINESS MINDSET EXCEPTION
If the PBI fails minor documentation checks (e.g., imperfect formatting) but the **Product Owner** and **Developers** explicitly state they have a shared, transparent understanding and are confident they can deliver it, the Agent MUST allow the item to be marked as "Ready". Emphasize that DoR is an alignment tool for **Transparency**, not a rigid Waterfall contract.
