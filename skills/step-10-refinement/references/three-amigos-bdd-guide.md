---
artifact_name: Three Amigos Cognitive & Handoff Guide
purpose: Instruct the Step 10 Refinement Agent on how to facilitate a "Three Amigos" (Business, Dev, QA) discussion to uncover edge cases and hidden complexities. Once the context is gathered, the Agent MUST hand off the actual writing of the User Story and BDD/Gherkin Acceptance Criteria to the dedicated Shared Skill.
---

### 🤖 AGENT DIRECTIVE (COGNITIVE ROUTING & FACILITATION LOGIC)

This document is the routing engine for dealing with ambiguous Product Backlog Items (PBIs) during Refinement. The Step 10 Agent MUST NOT attempt to write the final BDD/Gherkin syntax itself to avoid conflict with the dedicated User Story/AC Writer module.

#### 1. The Three Amigos Elicitation (The Triad)
When a PBI needs clarification, the Agent must act as a facilitator, prompting the user (and the Scrum Team) to view the requirement through three lenses before writing any code:
*   **Business Perspective (Product Owner):** Ask about the exact business value, regulatory/iGaming compliance (e.g., Decree 06), and happy path expectations.
*   **Development Perspective (Programmer):** Ask about architectural constraints, performance limits, and system dependencies.
*   **Testing Perspective (QA):** Ask about the "Unhappy Path" — timeouts, invalid inputs, concurrent transaction conflicts, and security thresholds.

#### 2. The Socratic Handoff (Agent-to-User Protocol)
The Agent must facilitate a quick Q&A to gather these parameters. 
*   *Example Prompt:* "To ensure this PBI is 'Ready', let's look at it through the Three Amigos lenses. Business-wise, what is the maximum transaction limit? Tech-wise, are there API rate limits? QA-wise, what should happen if the payment gateway times out?"

Once the user provides the answers, the Agent MUST NOT format them into Gherkin. Instead, it proposes a handoff:
*   *Handoff Prompt:* "Thank you for clarifying those edge cases. Shall I pass this rich context to our dedicated **User Story & BDD Writer Skill** to generate the perfectly formatted INVEST Story and Gherkin Acceptance Criteria for you?"

#### 3. Delegation to Shared Skill (Worker Execution)
Upon user confirmation, the Step 10 Agent silently packages the original PBI idea plus the newly discovered Three Amigos constraints and triggers the shared module:
👉 `../shared/user-story-writing/SKILL.md` (or the exact path of the user's specific module).

#### 4. Post-Generation Verification (The Return Loop)
After the Shared Skill has generated the BDD/Gherkin artifacts, the Step 10 Agent resumes control and runs the newly created PBI through `checklists/dor-readiness-check.md` to officially mark it as "Ready" for upcoming Sprints.
