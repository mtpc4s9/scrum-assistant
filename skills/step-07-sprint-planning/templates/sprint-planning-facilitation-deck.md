---
artifact_name: Sprint Planning Facilitation Deck
purpose: Serve as the primary, live-updatable facilitation deck for the Scrum Master to guide the Scrum Team through the Sprint Planning event (Why, What, How), displaying team-wide capacity (Figure 19.5 Pie & Table 19.2 Aggregate).
---

### 🤖 AGENT DIRECTIVE (HIDDEN FROM FINAL OUTPUT)
1.  **Reference First:** Load and apply [references/one-part-planning-guide.md](references/one-part-planning-guide.md) before populating this template.
2.  **Format:** Output a slide-by-slide presentation deck using markdown page breaks (`---` and `## SLIDE X:`).
3.  **Real-Time Facilitation Prompts:** Include a dedicated "🎤 *SM Facilitation Prompt*" for each slide to assist the Scrum Master in running the event.
4.  **Capacity Visuals (Figure 19.5 & Table 19.2 Aggregate):** 
    - Include the Mermaid Pie Chart (Figure 19.5) on the Capacity slide.
    - Provide a team-wide aggregate version of Table 19.2 (no individual names to prevent micromanagement, but clear mathematical breakdown of the team's total capacity).
5.  **Socratic Closing Prompt:** Append the closing Socratic facilitation question at the very end.
6.  **Output Generation:** Output ONLY the section below this line.

---

# 🖥️ SPRINT PLANNING FACILITATION DECK (SM TOOL)

## SLIDE 1: Sprint Planning Kickoff
*   **Sprint Reference:** *[Agent: Sprint Name or Number]*
*   **Timebox Limit:** *[Agent: e.g., 4 Hours]*
*   **Attendees:** Product Owner, Scrum Master, Developers
*   **Agenda:**
    1.  **WHY:** Craft the Sprint Goal
    2.  **WHAT:** Forecast Product Backlog Items (PBIs)
    3.  **HOW:** Define Tasks, Estimate Effort & Confirm Commitment

🎤 *SM Facilitation Prompt: "Welcome team to the Sprint Planning for [Sprint Name]. Today we align on a shared direction and commit to what we can realistically achieve. Let's start with the business value."*

---

## SLIDE 2: One-Part Sprint Planning Process
*This flowchart illustrates the iterative One-Part Sprint Planning loop: we select a PBI, task it out immediately to gain confidence, and subtract its hours from our capacity before deciding to pull the next item.*

```mermaid
flowchart LR
    A(["📊 Determine Capacity"])
    B(["🎯 Refine Sprint Goal"])
    C(["📋 Select Product Backlog Item"])
    D(["🔍 Gain Confidence \n Item Can Be Completed"])
    E{"🤔 Can Commit?"}
    F(["➕ Add Story To Commitment"])
    G{"📦 At Capacity?"}
    H(["✅ Finalize Sprint Commitment"])

    A --> B
    B --> C
    C --> D
    D --> E
    E -->|"Yes"| F
    F --> G
    E -->|"No"| G
    G -->|"No"| B
    G -->|"Yes"| H

    classDef process fill:#1E3A5F,stroke:#60A5FA,stroke-width:2px,color:#DBEAFE,font-size:13px,font-weight:600
    classDef decision fill:#78350F,stroke:#FBBF24,stroke-width:2px,color:#FEF3C7,font-size:13px,font-weight:600
    classDef finish fill:#064E3B,stroke:#34D399,stroke-width:3px,color:#D1FAE5,font-size:13px,font-weight:700

    class A,B,C,D,F process
    class E,G decision
    class H finish

    linkStyle 7 stroke:#F97316,stroke-width:2px,stroke-dasharray:8 4
    linkStyle 8 stroke:#34D399,stroke-width:2px
```

🎤 *SM Facilitation Prompt: "Team, this is the One-Part Planning process we will follow today. Instead of sizing everything first, we will take one PBI at a time, break it down to tasks, check if it fits our remaining capacity, and commit to it before moving to the next one. This prevents over-commitment."*

---

## SLIDE 3: Topic 1: WHY is this Sprint valuable?
*   **Business Opportunity / Context:**
    *   *[Agent: Insert 1-2 sentences summarizing the PO's current market driver or user problem]*
*   **Drafting the Sprint Goal:**
    *   **Sprint Goal:** *[Agent: Insert Proposed Sprint Goal]*
*   **Expected Business Value:**
    *   *[Agent: Describe the measurable/verifiable benefit of achieving this goal]*

🎤 *SM Facilitation Prompt: "Product Owner, please walk us through the vision. Developers, does this goal provide a clear focus? Let's refine it together until we have a single, cohesive Sprint Goal."*

---

## SLIDE 4: Historical Velocity Analysis
*Reviewing recent Sprint performance to establish an empirical baseline for point commitment:*

| Sprint | committed | Completed | Predictability |
| :--- | :---: | :---: | :---: |
| *[Agent: Sprint N-3]* | *[Committed]* pts | *[Completed]* pts | *[Completed/Committed]*% |
| *[Agent: Sprint N-2]* | *[Committed]* pts | *[Completed]* pts | *[Completed/Committed]*% |
| *[Agent: Sprint N-1]* | *[Committed]* pts | *[Completed]* pts | *[Completed/Committed]*% |

*   **Average Velocity:** *[Agent: Avg Points]* points
*   **Predictability Trend:** *[Agent: Stable / Declining / Improving]* (Avg: *[Predictability]*%)
*   **Variability:** *[Agent: Low / Moderate / High]* (Std Dev: *[X]* pts)
*   🎤 **Coaching Observation:** *[Agent: Insert relevant SM coaching pattern - e.g. stable, chronic overcommitment, or high variability]*

🎤 *SM Facilitation Prompt: "Team, let's review our recent velocity. Remember, velocity is an empirical forecasting tool, not a measure of team productivity or a performance KPI. We use it as a guideline to prevent overcommitment. If our predictability is below 80%, we should discuss why in the retrospective and plan more conservatively."*

---

## SLIDE 5: Team Capacity Overview (Figure 19.5)
*To plan realistically and maintain a sustainable pace, we allocate our total Sprint hours across five key categories:*

```mermaid
pie title Team Capacity Allocation
    "Capacity for PBIs (Sprint Execution)" : 60
    "Personal Time Off (PTO)" : 10
    "Other Scrum Activities (Events, Grooming)" : 15
    "Non-Sprint Commitments (Support, Org Meetings)" : 10
    "Sprint Buffer (Unknown unknowns)" : 5
```

🎤 *SM Facilitation Prompt: "This chart represents how we divide our total Sprint timebox. We protect 10% as buffer and allocate 15% to Scrum events. This keeps our plan realistic and prevents the team from running at 100% capacity."*

---

## SLIDE 6: Capacity Calculation (Table 19.2 Aggregate)
*Team-wide aggregate math to determine total effort-hours available for PBI task work:*

| Capacity Metric | Team Total (Aggregate) |
| :--- | :---: |
| **Gross Developer Days Available** *(e.g., [N] Devs x 10 days)* | *[Agent: Total Days]* |
| ➖ Planned PTO & Holidays (Days) | *[Agent: Total PTO Days]* |
| **Days Available for Focus Capacity** | **[Agent: Net Days]** |
| ✖️ Focus Hours per Day *(8 hrs/day x Focus Factor 70% = 5.6 hrs/day)* | **5.6 hours/day** |
| **Gross Focus Hours Baseline** | **[Agent: Net Days x 5.6]** hours |
| ➖ Scrum Events & Refinement overhead (Ceremony Hours) | *[Agent: Ceremony Hours]* |
| **🎯 NET AVAILABLE EFFORT-HOURS (Team Total)** | **[Agent: Total Effort-Hours]** |
| **Recommended Story Point Commitment Range** *(0.85x to 1.00x)* | **[Agent: Range Floor] - [Agent: Range Ceiling]** points |

🎤 *SM Facilitation Prompt: "We have a total of [Total Effort-Hours] net effort-hours available for active Sprint execution. Based on our point productivity, this maps to a recommended commitment range of [Range Floor] to [Range Ceiling] story points. Let's use this capacity boundary to guide our selection loop."*

---

## SLIDE 7: Topic 2: WHAT can be done this Sprint?
*Evaluating the highest priority Product Backlog Items (PBIs) matching our Sprint Goal:*

*   **PBI 1:** *[Agent: User Story Story-1]* (*[Size]* pts) - Meets DoR: **Yes**
*   **PBI 2:** *[Agent: User Story Story-2]* (*[Size]* pts) - Meets DoR: **Yes**
*   **PBI 3:** *[Agent: User Story Story-3]* (*[Size]* pts) - Meets DoR: **Yes**

*Current Backlog Forecast Status:*
*   **Sprint Goal Alignment:** *[Agent: Describe how these items support the Goal]*
*   **Current Confidence Level:** *[Agent: e.g., High / Medium]*

🎤 *SM Facilitation Prompt: "Are the top stories on this slide clear? Have we verified that they meet our Definition of Ready? Let's take the first item and move directly to breaking it down."*

---

## SLIDE 8: Topic 3: HOW will the work get done?
*Executing the One-Part Planning Loop: Select -> Task Out -> Deduct Hours -> Repeat.*

*   **PBI #1: [PBI Name]**
    *   Task Breakdown: Tasks planned and estimated at **[X]** total hours.
*   **PBI #2: [PBI Name]**
    *   Task Breakdown: Tasks planned and estimated at **[Y]** total hours.
*   **PBI #3: [PBI Name]**
    *   Task Breakdown: Tasks planned and estimated at **[Z]** total hours.

**Calculated Totals for this Sprint:**
*   **Total Task Hours Planned:** *[Sum of X+Y+Z]* hours
*   **Remaining Team Capacity:** *[Net Available Effort-Hours - Planned Hours]* hours

🎤 *SM Facilitation Prompt: "Developers, as you design the technical tasks, ensure no task is larger than 8 hours. If we run out of capacity, we must stop and discuss with the Product Owner what we can remove."*

---

## SLIDE 9: Commitment & Definition of Done (DoD)
*Confirming the plan and aligning on quality standards:*

*   **Definition of Done (DoD) Agreement:**
    *   All developers agree that the task plan covers all verification checks to build a "Done", shippable increment.
*   **Quality Gates Checklist:**
    *   - [ ] Automated tests written and executed
    *   - [ ] Code review completed by another developer
    *   - [ ] *[Agent: Insert iGaming/project regulatory checklist item]*
*   **Team Commitment Statement:**
    *   "The Developers forecast that we can deliver the selected items and achieve the Sprint Goal within our available capacity."

🎤 *SM Facilitation Prompt: "Developers, do you feel this plan is realistic and that you have the capability to deliver these items by the end of the Sprint? If yes, let's finalize our commitment."*

---

## SLIDE 10: Sprint Review Invitation
*Sharing our commitment and inviting collaboration at the end of the Sprint:*

*   **What will be inspected:**
    *   A live demonstration of the Sprint increment, proving the Sprint Goal is achieved.
*   **Sprint Review Details:**
    *   **Date/Time:** *[Agent: Date & Time]*
    *   **Location/Link:** *[Agent: Meeting link]*
    *   **Audience:** Scrum Team + Key Stakeholders

🎤 *SM Facilitation Prompt: "Great work completing the Sprint Planning. I will distribute this facilitation output and send out the invitation for the Sprint Review. Let's make this a successful Sprint!"*

---

*> **Socratic Closing Prompt (Agent Appends This):** "Chủ nhân, the Facilitation Deck is ready. Does it provide the appropriate visual support for your live sessions? Would you like to adjust the facilitation prompts or the categories in Figure 19.5?"*
