---
artifact_name: Sprint Review Minimalist Slide Deck & Live Notes
purpose: Provide a timeboxed, low-ceremony presentation structure to set the context for the Sprint Review. It enforces a focus on the Sprint Goal and the working Increment, explicitly avoiding technical task breakdowns. It includes a Live Notes capture area for post-meeting AI triage and release note generation.
---

### 🤖 AGENT DIRECTIVE (HIDDEN FROM FINAL OUTPUT)
When generating this slide deck prior to the Sprint Review, the AI Agent MUST:
1.  **Extract Context:** Pull the **Sprint Goal** and only the high-level Product Backlog Items (PBIs) that meet the **Definition of Done**. Do NOT list technical tasks or the Sprint Backlog.
2.  **Post-Meeting Triage (Handoff to Shared Skills):** After the meeting, when the user provides the updated `[LIVE NOTES]` section, the Agent must analyze the notes:
    *   *If the note is a requested change/new feature (Accepted by PO):* Hand off the context to `../shared/user-story-writing/SKILL.md` to create a new PBI.
    *   *If the note confirms a release decision:* Hand off the context and the "Done" PBIs to `../shared/po-release-notes/SKILL.md` to generate audience-appropriate release notes.
3.  **Output Generation:** Output ONLY the section below this line as a clean, copy-pasteable Markdown format.

---

# 🚀 SPRINT REVIEW: [Insert Sprint Name/Number]
**Date:** [Insert Date] | **Product Owner:** [Insert Name]
**Timebox:** [e.g., 2 Hours max for a 2-week Sprint]

---

## SLIDE 0: MEETING AGENDA & GROUND RULES
*   **Total Duration:** [Insert Timebox, e.g., 2 Hours] (We strictly respect the timebox to maintain focus).
*   **Agenda & Time Allocation:**
    *   ⏱️ **Agenda & Ground Rules:** 5 mins (Slide 0)
    *   ⏱️ **Sprint Goal & Outcome Context:** 10 mins (Slide 1)
    *   ⏱️ **Review of "Done" & "Not Done" Items:** 15 mins (Slide 2)
    *   ⏱️ **Working Software Demonstration:** 60 mins (Slide 3)
    *   ⏱️ **Product Backlog & Next Sprint Planning Sync:** 25 mins (Slide 4)
    *   ⏱️ **Triage & Meeting Wrap-up:** 5 mins

---

## SLIDE 1: THE SPRINT GOAL (WHY)
*   **Our Objective for this Sprint:** 
    *   🎯 *[Agent: Insert Sprint Goal here]*
*   **Outcome:** *[Agent: State whether the Goal was met, partially met, or not met in 1 sentence]*

---

## SLIDE 2: WHAT IS "DONE" (WHAT)
*The following items have successfully met our Definition of Done (Quality, Compliance, and Business requirements) and are part of today's Increment.*
*   ✅ [PBI ID] - [High-level Feature Title / Benefit]
*   ✅ [PBI ID] - [High-level Feature Title / Benefit]
*   *Note: [Insert any items that were planned but NOT done, to maintain Transparency. State they are back in the Product Backlog.]*

---

## SLIDE 3: DEMONSTRATION (SHOW, DON'T TELL)
*   **Time to turn off the slides!** 
*   We invite our Stakeholders to engage directly with the working **Increment**.
*   *Focus areas for testing today:* [Insert 1-2 specific flows to demonstrate]

---

## SLIDE 4: RELEASE PLAN & NEXT STEPS (ADAPTATION)
*   **Current Progress:** *[Agent: Insert brief summary from release burn-down/burn-up chart]*
*   **Market/Domain Updates:** Have there been any shifts in the market, competitor actions, or regulatory changes we should be aware of today?
*   **Next Priorities:** Looking ahead to the next Sprint, our preliminary focus is on [Insert next highest ordered items from Product Backlog].

---

# 📝 [LIVE NOTES CACHE] - FOR POST-MEETING AI TRIAGE
*(**Product Owner:** Type raw feedback, stakeholder requests, or release decisions here during the meeting. Hand this back to the AI Agent afterward).*

*   **Feedback 1:** [e.g., Marketing loves the UI, but wants the checkout button to be red instead of blue. PO Decision: ACCEPT.]
*   **Feedback 2:** [e.g., Compliance officer noted a missing disclaimer. Must fix immediately. PO Decision: ACCEPT - HIGH PRIORITY.]
*   **Release Decision:** [e.g., The core flow is approved. We will deploy the done items to production tonight. Need release notes for end-users.]
