---
artifact_name: Insight Backlog & Improvement Triage
purpose: Act as a repository for deferred retrospective insights and provide the AI Agent with strict triage logic to classify incoming improvement ideas into either direct Sprint Backlog Tasks or formal Product Backlog Items (PBIs).
---

### 🤖 AGENT DIRECTIVE (COGNITIVE TRIAGE & HANDOFF LOGIC)

When the user inputs "improvement ideas" generated from the **Sprint** Retrospective, the Agent MUST NOT blindly treat all of them as PBIs. The Agent MUST execute the following 3-phase processing logic to maintain Scrum framework integrity.

#### PHASE 1: CLASSIFICATION (TASK vs. PBI)
Analyze each inputted improvement idea and classify it:
*   **Type A (Process/Team Task):** Behavioral changes, team agreements, or minor process tweaks (e.g., "Update Jira daily", "Pair programming for critical bugs").
    *   *Action:* Format these strictly as actionable `[TASKS]`. Instruct the user to place these directly into the upcoming **Sprint Backlog** to ensure continuous improvement ("Don't separate, integrate").
*   **Type B (Technical Debt / Infrastructure / Tooling PBI):** Significant engineering work, architectural changes, or tooling development that consumes meaningful capacity (e.g., "Build CI/CD pipeline", "Refactor legacy payment module").
    *   *Action:* These MUST be treated as formal PBIs. Proceed to Phase 2.
*   **Type C (Deferred Insight):** Great ideas that the team does not have the capacity to address in the very next Sprint.
    *   *Action:* Append these to the `[INSIGHT REPOSITORY]` section below.

#### PHASE 2: PBI READINESS & SHARED SKILL HANDOFF (For Type B only)
If an idea is classified as a Type B PBI, it must meet the Definition of Ready (DoR) before it can enter the **Product Backlog** and potentially the next **Sprint Backlog**.
1.  **Size Check:** Evaluate the complexity. If the improvement is too large (e.g., "Automate all manual tests"), silently invoke the routing prompt to call: 
    👉 `../shared/story-splitting/SKILL.md` to break the technical epic into vertical slices.
2.  **US Writing & DoR Check:** Once appropriately sized, silently package the context and trigger the shared skill:
    👉 `../shared/user-story-writing/SKILL.md` to format the improvement into an INVEST-ready PBI with BDD Acceptance Criteria.
3.  **Handoff Message:** *"Ý tưởng [Tên ý tưởng] là một hạng mục kỹ thuật lớn. Tôi đã gọi đặc vụ Story Splitting để cắt nhỏ và đặc vụ US Writer để viết thành PBI chuẩn BDD. Vui lòng đưa PBI này cho **Product Owner** để đánh giá ưu tiên trong **Product Backlog** nhé."*

#### PHASE 3: OUTPUT GENERATION
Output the summarized Action Items for the upcoming **Sprint**, followed by the updated Insight Repository containing deferred items.

---

# 💡 THE INSIGHT BACKLOG

## 🚀 ACTION ITEMS FOR UPCOMING SPRINT BACKLOG
*(These are Type A process improvements or small tasks committed for the next Sprint. They DO NOT go to the Product Owner for prioritization; the Developers own them).*
*   [ ] *[Agent: Insert Type A task here]*
*   [ ] *[Agent: Insert Type A task here]*

## 📋 NEW TECHNICAL PBIs (ROUTED TO PRODUCT BACKLOG)
*(These are Type B technical improvements. The AI has processed them via Shared Skills to meet DoR. They must be negotiated with the PO).*
*   **PBI:** *[Agent: Insert link or summary of generated PBI]*

## 🗄️ DEFERRED INSIGHT REPOSITORY
*(These are Type C insights. Good ideas, but no capacity to tackle them right now. We will review this list at the start of the next Retrospective).*
1.  *[Agent: Insert deferred insight here]*
2.  *[Insert historical deferred insights here]*
