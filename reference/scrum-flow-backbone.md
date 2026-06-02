# Scrum Flow Backbone

> **Sources:**
> - [2020 Scrum Guide](https://scrumguides.org/) — Ken Schwaber & Jeff Sutherland
> - [Scrum Guide Expanded (SGEP v2026.1)](https://scrumexpansion.org/scrum-guide-expanded/) — John Coleman, Ralph Jocham, Jeff Sutherland
> - Initial draft: `../refs/the-scrum-flow.md`
>
> **Purpose:** This document serves as the definitive backbone for all ceremony skills, PO/BA skills,
> and SM operations skills within this scrum-assistant toolkit. Every sub-skill should trace its
> inputs, outputs, and techniques back to this document.

---

## Foundational Principles (Non-Negotiable)

Before stepping through the flow, every practitioner using this toolkit must internalize these pillars.

### Empirical Process Control
Scrum is grounded in **three pillars**: Transparency → Inspection → Adaptation.
- **Transparency:** Reality and work must be visible to all who perform or receive the work.
- **Inspection:** Artifacts, commitments, and progress are inspected frequently to detect emergence and variances.
- **Adaptation:** The moment improvement opportunities emerge, the Scrum Team adapts — to artifacts, commitments, team composition, or organization.

### Scrum Values
**Focus · Openness · Commitment · Courage · Respect**
These values are not decorative; they define the behavioral contract of the Scrum Team. Violations erode trust and reduce empiricism effectiveness.

### Complexity Acknowledgment (SGEP)
iGaming / Lottery product development is firmly in the **complex domain**: more unknowns than knowns, cause-and-effect are only coherent in retrospect, and expertise alone is insufficient. Scrum is the appropriate framework — it enables the Scrum Team to discover desirable patterns and amplify them.

---

## PHASE 0 — Initiative & Planning

> **Scope:** Pre-Sprint activities. Establishes the strategic foundation before the Sprint Loop begins.
> These steps are NOT Scrum events per the 2020 Scrum Guide, but are recognized as essential pre-work
> in the Scrum Guide Expanded under "Product Thinking" and "Discovery."

---

### Step 1 — Visioning (Product Vision Creation)

| Attribute | Detail |
|-----------|--------|
| **Owner** | Product Owner (+ Stakeholders / Business) |
| **SM Role** | Facilitate; coach PO on vision clarity |
| **Input** | Raw idea, market opportunity, regulatory insight, business goal |
| **Techniques** | Lean Business Model Canvas, Elevator Pitch, Product Vision Board (Roman Pichler), User Research |
| **Output** | **Product Vision Statement** — a concise, inspiring, durable statement of the product's purpose |
| **SGEP Note** | Value remains an assumption until confirmed by evidence. The vision must be testable over time. |

**Output Artifacts:**
- Elevator Pitch (1–2 sentences)
- Product Vision Board
- Initial Stakeholder Map

---

### Step 2 — Goal Setting (Product Goal Definition)

| Attribute | Detail |
|-----------|--------|
| **Owner** | Product Owner |
| **SM Role** | Ensure PO communicates the Goal explicitly and that it is understood by the entire Scrum Team |
| **Input** | Product Vision Statement |
| **Techniques** | Impact Mapping, OKR (Objectives & Key Results), SMART Goal Criteria |
| **Output** | **Product Goal** — the long-term objective for the Scrum Team (2020 SG: PB Commitment) |
| **2020 SG** | "The Product Goal describes a future state of the product which can serve as a target for the Scrum Team to plan against." One Goal at a time — must be fulfilled or abandoned before the next. |
| **SGEP Note** | Product Goal must reflect Stakeholder value; value remains an assumption until confirmed by result feedback (quantitative + qualitative). |

**Output Artifacts:**
- Product Goal statement (formally documented in the Product Backlog header)
- Impact Map (optional but recommended for complex domains)

---

### Step 3 — Goal Prioritization

| Attribute | Detail |
|-----------|--------|
| **Owner** | Product Owner |
| **Input** | Multiple potential Product Goals (if applicable) |
| **Techniques** | Cost of Delay (CoD), WSJF (Weighted Shortest Job First), MoSCoW |
| **Output** | **Single prioritized Product Goal** — 1st Product Goal to pursue |

**Decision Criteria for iGaming Context:**
- Regulatory compliance deadlines (non-negotiable)
- RTP (Return to Player) validation requirements
- 3rd-party vendor integration readiness (Kambi, Pragmatic, payment gateways)

---

### Step 4 — Product Backlog Creation

| Attribute | Detail |
|-----------|--------|
| **Owner** | Product Owner (accountable); Developers + SM may support |
| **Input** | Product Goal (Step 2) |
| **Techniques** | User Story Mapping, Story Splitting (SPIDR, Cake Slice), Epic decomposition |
| **Output** | **Initial Product Backlog** — an emergent, ordered list. Contains Epics, Features, and large PBIs. |
| **2020 SG** | "The Product Backlog is an emergent, ordered list of what is needed to improve the product. It is the single source of work undertaken by the Scrum Team." |
| **SGEP Note** | Each PBI has: description, order, size estimate, and Acceptance Criteria. The PO orders; Developers size. |

**Output Artifacts:**
- Product Backlog (in tool: Jira, Linear, or physical board)
- Epic/Feature tree (Story Map visual)

---

### Step 5 — Release Planning

| Attribute | Detail |
|-----------|--------|
| **Owner** | Product Owner (leads); entire Scrum Team collaborates |
| **Input** | Initial Product Backlog, Team Capacity, Technical constraints |
| **Techniques** | Relative Sizing (Fibonacci / T-shirt), Velocity Forecasting, Cone of Uncertainty |
| **Output** | **Release Plan** |

**Release Plan Structure:**
```
Release Goal    : [What outcome will be released?]
Target Date     : [Calendar date or Sprint #]
Budget Estimate : [If applicable]
Scope Range     : [Min viable scope — Max desirable scope]
Sprint Map      : [Sprint 1: ..., Sprint 2: ..., Sprint N: ...]
```

**iGaming Considerations:**
- Align Release Plan with game launch windows, regulatory submission deadlines, and payment gateway certification timelines.
- Reference `../templates/third-party-integration-matrix.md` for vendor dependencies.

---

### Step 6 — Standards Setup (DoR · DoD · Working Agreements)

| Attribute | Detail |
|-----------|--------|
| **Owner** | Scrum Master (facilitates); entire Scrum Team defines |
| **Input** | Team capabilities, organizational constraints, regulatory requirements |
| **Techniques** | Working Agreements Workshop, Definition of Ready Workshop, Definition of Done Workshop |
| **Output** | Three formal agreements |

**Output: Definition of Ready (DoR)**
A PBI is ready for Sprint Planning when it satisfies:
- [ ] User Story written in agreed format
- [ ] Acceptance Criteria defined (BDD/Gherkin preferred)
- [ ] Sized by Developers
- [ ] Dependencies identified and resolved (or explicitly managed)
- [ ] No open blocking questions

**Output: Definition of Done (DoD)**
A PBI is Done when:
- [ ] Code written and peer-reviewed
- [ ] Unit tests pass (coverage threshold met)
- [ ] Acceptance criteria verified
- [ ] Integrated into main branch (CI/CD green)
- [ ] Regulatory / compliance checks passed (iGaming: RTP validation, game certification)
- [ ] Deployed to staging / production (as agreed)
> 2020 SG: "Work cannot be considered part of an Increment unless it meets the Definition of Done."

**Output: Working Agreements**
```
Section                      | Content
-----------------------------|----------------------------------
Core Principles              | [Team's shared values & commitments]
Expected Behaviors           | [Communication norms, meeting etiquette]
Exception Handling           | [Escalation path, impediment protocol]
Accountability Signatures    | [Team members acknowledge and commit]
```

---

## PHASE 1 — Sprint Loop

> The Sprint is the **heartbeat of Scrum** — a fixed-length container (≤ 1 month) for all other events.
> A new Sprint starts immediately after the conclusion of the previous Sprint.
>
> **Sprint Rules (2020 SG):**
> - No changes that endanger the Sprint Goal
> - Quality does not decrease
> - Product Backlog is refined as needed
> - Scope may be clarified/renegotiated with PO without affecting Sprint Goal

---

### Step 7 — Sprint Planning

| Attribute | Detail |
|-----------|--------|
| **Owner** | Entire Scrum Team (PO proposes, Developers commit) |
| **Timebox** | Max 8h for 1-month Sprint; proportionally shorter for shorter Sprints |
| **Input** | Product Backlog (PBIs meeting DoR), DoD, Team Capacity, Previous Velocity, Product Goal |
| **Techniques** | Three Topics (Why → What → How), Task Breakdown, Capacity Planning |

**Topic 1 — WHY (Sprint Goal)**
- PO proposes the Sprint's value to stakeholders
- Entire Scrum Team collaborates to craft the **Sprint Goal**
- Sprint Goal = single objective, creates focus and coherence
- Must be finalized before end of Sprint Planning

> 2020 SG: "The Sprint Goal must be finalized prior to the end of Sprint Planning."

**Topic 2 — WHAT (Selected PBIs)**
- Developers select PBIs from the Product Backlog based on capacity
- PO clarifies; Developers may refine PBIs to increase understanding
- Selection driven by Sprint Goal alignment, not arbitrary capacity-filling

**Topic 3 — HOW (Sprint Backlog Plan)**
- Developers decompose each selected PBI into tasks (≤ 1 day each)
- Task breakdown is at the sole discretion of Developers (no one else dictates)
- Estimate remaining work for transparency

**Output:**
- **Sprint Goal** (documented in Sprint Backlog)
- **Sprint Backlog** = Sprint Goal (Why) + Selected PBIs (What) + Task Plan (How)

---

### Step 8 — Daily Scrum

| Attribute | Detail |
|-----------|--------|
| **Owner** | Developers (PO/SM participate as Developers if working on Sprint Backlog items) |
| **Timebox** | 15 minutes — same time, same place every working day |
| **Input** | Current progress, Sprint Backlog, Sprint Goal |
| **Techniques** | Walk the Board (preferred over 3-question round-robin), Flow-based inspection |
| **Output** | Updated Sprint Backlog; Plan for next 24 hours |

**Recommended Format — Walk the Board:**
1. Walk each in-progress item on the board
2. Is this item progressing toward the Sprint Goal?
3. Are there impediments blocking progress?
4. Adjust the plan for the next 24h accordingly

> 2020 SG: "The Daily Scrum is not the only time Developers are allowed to adjust their plan. They often meet throughout the day for more detailed discussions about adapting or replanning."

**Anti-patterns to avoid:**
- Status reporting to SM/PO (it's a Developers' event)
- Skipping when "nothing has changed"
- Running beyond 15 minutes

---

### Step 9 — Sprint Execution

| Attribute | Detail |
|-----------|--------|
| **Owner** | Developers |
| **Input** | Sprint Backlog |
| **Techniques** | Swarming, Pair Programming, TDD (Test-Driven Development), BDD, CI/CD, Mob Programming |
| **Output** | **Increment** — concrete, usable, meets DoD |

**Key Principles:**
- Each Increment is additive to all prior Increments
- Multiple Increments may be created within a Sprint
- An Increment may be delivered to stakeholders **before** Sprint Review — Sprint Review is NOT a release gate
- Increment must be usable to provide value

> SGEP: "Technical excellence encompasses: Specification by Example, Clean Code, Unit Testing, TDD, Test Automation, Continuous Integration, Continuous Delivery, Architecture and Design, Acceptance Testing."

**iGaming Engineering Notes:**
- Game logic must be testable in isolation (unit tests for RTP calculation, prize structure)
- Payment gateway integrations require sandbox testing before integration into Increment
- Regulatory compliance checks (game certification) are part of DoD — not a post-release step

---

### Step 10 — Product Backlog Refinement (Ongoing)

| Attribute | Detail |
|-----------|--------|
| **Owner** | Product Owner (accountable); Developers collaborate; SM facilitates |
| **Timing** | Ongoing activity — typically mid-Sprint, not exceeding 10% of Sprint capacity |
| **Input** | PBIs in the "middle zone" of Product Backlog (upcoming 1-2 Sprints) |
| **Techniques** | BDD/Gherkin (Acceptance Criteria), Planning Poker, Story Splitting (SPIDR, Cake Slice), Three Amigos |
| **Output** | PBIs meeting DoR — ready for next Sprint Planning |

**Refinement Outcomes per PBI:**
- [ ] Description is clear and unambiguous
- [ ] Acceptance Criteria written (preferably as BDD scenarios)
- [ ] Sized by Developers
- [ ] Dependencies identified
- [ ] Meets DoR

> 2020 SG: "Product Backlog refinement is the act of breaking down and further defining Product Backlog items into smaller more precise items. This is an ongoing activity to add details, such as a description, order, and size."

---

### Step 11 — Sprint Review

| Attribute | Detail |
|-----------|--------|
| **Owner** | Scrum Team + Stakeholders (collaborative working session) |
| **Timebox** | Max 4h for 1-month Sprint; proportionally shorter for shorter Sprints |
| **Input** | Increment(s), Stakeholder feedback, Product Backlog, Product Goal progress |
| **Techniques** | Live Demonstration, Collaborative Discussion, Product Backlog Adjustment |
| **Output** | Updated Product Backlog; insights for next Sprint; Product Goal progress validated |

**Sprint Review Structure:**
1. **Context** — SM/PO presents Sprint Goal and what was planned
2. **Demonstration** — Developers demonstrate the Increment (live, not slides)
3. **Discussion** — Stakeholders and Scrum Team discuss what was accomplished and what changed in the environment
4. **Adaptation** — Collaborative decision on what to do next; Product Backlog adjusted accordingly

> 2020 SG: "The Sprint Review is a working session and the Scrum Team should avoid limiting it to a presentation."
> SGEP: "Inspecting and adapting should be more valued than keeping promises."

**Anti-patterns:**
- Treating Sprint Review as a demo-only event (no discussion, no adaptation)
- PO approving/rejecting items (that's a DoD gate, not a Review decision)
- Skipping if Increment "isn't impressive enough"

---

### Step 12 — Sprint Retrospective

| Attribute | Detail |
|-----------|--------|
| **Owner** | Scrum Master (facilitates); entire Scrum Team participates |
| **Timebox** | Max 3h for 1-month Sprint; proportionally shorter for shorter Sprints |
| **Input** | Sprint data (velocity, burndown, impediment log), Team's emotional experience, current DoD |
| **Techniques** | Event Timeline, Emotions Seismograph, Dot Voting, 4Ls (Liked/Learned/Lacked/Longed for), Starfish, FLAP |
| **Output** | **Actionable Improvements** (at least 1, ideally committed to next Sprint Backlog) |

**Retrospective Structure (Three Questions):**
1. **What went well?** (Amplify these patterns)
2. **What problems did we encounter?** (Be specific — data over feelings)
3. **How were those problems solved (or not)?** (Identify systemic causes)

> 2020 SG: "The most impactful improvements are addressed as soon as possible. They may even be added to the Sprint Backlog for the next Sprint."

**Output Format:**
```
Improvement Item       | Owner    | Target Sprint | Success Metric
-----------------------|----------|---------------|---------------
[Specific action]      | [Person] | Sprint N+1    | [Measurable outcome]
```

---

## Artifact Summary

| Artifact | Commitment | Owner | Updated When |
|----------|------------|-------|--------------|
| Product Backlog | Product Goal | Product Owner | Continuously (Refinement, Review) |
| Sprint Backlog | Sprint Goal | Developers | Daily (Daily Scrum) |
| Increment | Definition of Done | Developers | Each time a PBI is completed |

---

## Accountability Summary

| Accountability | Primary Responsibilities |
|----------------|--------------------------|
| **Product Owner** | Maximize product value; own Product Goal; order Product Backlog; communicate PBIs clearly |
| **Scrum Master** | Establish Scrum; enable Scrum Team effectiveness; remove impediments; facilitate events; coach PO and organization |
| **Developers** | Create Increment; own Sprint Backlog; define tasks; hold each other accountable; maintain DoD |
| **Stakeholders** (SGEP) | Engage at Sprint Review; provide feedback; define value; not manage the team |
| **Supporters** (SGEP) | Proactively support and enhance Scrum adoption; guided by SM |

---

## Sprint Timebox Reference

| Event | Max Duration (1-month Sprint) |
|-------|-------------------------------|
| Sprint | ≤ 4 weeks (fixed) |
| Sprint Planning | 8 hours |
| Daily Scrum | 15 minutes |
| Sprint Review | 4 hours |
| Sprint Retrospective | 3 hours |
| Refinement | ~10% of Sprint capacity (ongoing) |

---

## Skill Cross-Reference Map

This backbone maps to the following skills in this toolkit:

| Step(s) | Skill File |
|---------|------------|
| Step 1 | `../skills/step-01-visioning/SKILL.md` |
| Step 2 | `../skills/step-02-goal-setting/SKILL.md` |
| Step 3 | `../skills/step-03-goal-prioritization/SKILL.md` |
| Step 4 | `../skills/step-04-backlog-creation/SKILL.md` |
| Step 5 | `../skills/step-05-release-planning/SKILL.md` |
| Step 6 | `../skills/step-06-standards-setup/SKILL.md` |
| Step 7 | `../skills/step-07-sprint-planning/SKILL.md` |
| Step 8 | `../skills/step-08-daily-scrum/SKILL.md` |
| Step 9 | `../skills/step-09-sprint-execution/SKILL.md` |
| Step 10 | `../skills/step-10-refinement/SKILL.md` |
| Step 11 | `../skills/step-11-sprint-review/SKILL.md` |
| Step 12 | `../skills/step-12-sprint-retrospective/SKILL.md` |

---

## iGaming Domain Overlays

The following domain-specific concerns apply across all steps for iGaming / Online Lottery context:

| Concern | Applies To | Reference |
|---------|------------|-----------|
| RTP Validation | DoD, Step 9 | `../templates/game-rules-math-sheet.md` |
| Prize Structure Review | PBI Acceptance Criteria, Step 4/10 | `../templates/game-rules-math-sheet.md` |
| Vendor/3rd-Party Dependencies | Release Planning, Refinement | `../templates/third-party-integration-matrix.md` |
| Regulatory Compliance Gate | DoD, Sprint Review | `../reference/igaming-context.md` |
| Payment Gateway Certification | Release Plan, Step 5 | `../templates/third-party-integration-matrix.md` |

---

*Last updated: see Git log. Maintained by: Scrum Master / Product Owner using scrum-assistant toolkit.*
