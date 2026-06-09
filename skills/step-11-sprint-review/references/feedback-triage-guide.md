---
artifact_name: Sprint Review Feedback Triage & Handoff Guide
purpose: Instruct the Step 11 AI Agent on how to process raw `[LIVE NOTES]` captured during the Sprint Review. It enforces a Socratic evaluation of stakeholder feedback to protect the Product Backlog from low-value clutter, and routes approved decisions to the appropriate Shared Skills (User Story generation or Release Notes generation).
---

### 🤖 AGENT DIRECTIVE (COGNITIVE TRIAGE LOGIC)

After the Sprint Review, when the user provides the updated `[LIVE NOTES]` from the slide deck, the Agent MUST NOT blindly accept all feedback. The Agent MUST execute the following 3-phase Triage Protocol.

#### PHASE 1: CATEGORIZATION
Silently read the `[LIVE NOTES]` and categorize each item into one of three buckets:
1.  **New Feature / Change Request:** A stakeholder asked for new functionality, a modification, or identified an unmet need.
2.  **Defect / Bug:** A stakeholder identified a flaw in the demonstrated Increment.
3.  **Release Decision:** A decision was made regarding deploying the "Done" Increment to production or users.

#### PHASE 2: THE SOCRATIC TRIAGE (AI-TO-PO INTERVIEW)
Before routing any item to a shared skill, the Agent must act as an Agile Coach and interview the **Product Owner** (User) to validate the economic sense of the feedback. Present these questions conversationally:

*   **For Feature/Change Requests:** *"Regarding the request for [Feature X]: Does this align with our upcoming Product Goal? If we accept it, what is the expected business value or ROI? (If it's low value, I recommend we Reject it to keep our Product Backlog lean)."*
*   **For Defects:** *"Regarding the bug [Bug Y]: Was this an escaped defect that passed our Definition of Done, or a missed Acceptance Criteria? Should we prioritize fixing it in the very next Sprint?"*
*   **For Release Decisions:** *"I see we are releasing the Increment. Who is the target audience for the release notes (e.g., end-customers, internal marketing, technical ops) so I can tailor the tone?"*

#### PHASE 3: DELEGATION & HANDOFF (WORKER EXECUTION)
Once the **Product Owner** answers the triage questions and explicitly states "ACCEPT" for the items:

*   **Route 1 (PBI Generation):** For accepted features, changes, or bugs, the Agent packages the context and triggers the Shared Skill: 
    👉 `../shared/user-story-writing/SKILL.md` 
    *(Tell the user: "I am sending this to the User Story Writer to format it into an INVEST-ready PBI with BDD Acceptance Criteria for your Product Backlog.")*
*   **Route 2 (Release Notes Generation):** For release decisions, the Agent gathers the list of "Done" items from the Sprint Review Slide Deck, incorporates the defined audience, and triggers the Shared Skill: 
    👉 `../shared/po-release-notes/SKILL.md`
    *(Tell the user: "I am generating the release notes tailored for [Audience] now.")*
*   **Route 3 (Rejection):** If the PO rejects an item, acknowledge the decision to protect the Product's vision and discard the note.

**Guardrail:** Always remind the Product Owner that newly generated PBIs will be placed in the **Product Backlog** for future refinement, NOT directly into the current or next **Sprint Backlog** unless urgently prioritized.
