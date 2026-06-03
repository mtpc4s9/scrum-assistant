---
artifact_name: Team Norms (Working Agreements) Core Document
purpose: Act as the definitive, living "ground rules" document for the Scrum Team, fostering psychological safety, self-management, and adherence to Scrum Values. Designed for internal use and continuous inspection during Sprint Retrospectives.
---

### 🤖 AGENT DIRECTIVE (HIDDEN FROM FINAL OUTPUT)
When generating the Team Norms Core Document, the AI Agent MUST adhere to these rules:
1.  **Reference First:** Load and apply [references/team-norm-guide.md](references/team-norm-guide.md) before populating this template.
2.  **Format:** Output a clean, structured Markdown document suitable for printing or pinning in the team's physical or virtual workspace.
3.  **Scrum Values Mapping:** Explicitly map the proposed rules to the 5 Scrum Values (Commitment, Focus, Openness, Respect, Courage) in each section header.
4.  **Anti-Punitive Rule:** Ensure NO rules dictate punishments, fines, or individual blame (e.g., "Late members pay $5"). Focus on systemic solutions and a blame-free environment.
5.  **Placeholder Filling:** Replace all `[Fill in]` placeholders with contextually appropriate values derived from the `input-readiness.md` inputs (e.g., team time zones for core hours, tech stack for tooling norms).
6.  **Living Document Disclaimer:** Include a clear statement that this document is owned by the Scrum Team and must be inspected and adapted at every Sprint Retrospective.
7.  **Socratic Closing Prompt:** Append the closing facilitation question after the document body.
8.  **Output Generation:** Output ONLY the section below this line.

---

# 📜 TEAM NORMS (WORKING AGREEMENTS)

**⚠️ THE LIVING DOCUMENT PLEDGE:**
*This document is the core property of the **Scrum Team**. It is not a directive from management or a mandate from the **Scrum Master**. The norms below exist to protect our shared space for psychological safety, **Self-Management**, and **Transparency**. This document must be **Inspected and Adapted** continuously at every **Sprint Retrospective**. It becomes valid only when all Scrum Team members have reviewed, contributed to, and formally acknowledged it.*

---

### 1. 🛡️ RESPECT & BLAME-FREE ENVIRONMENT *(Scrum Value: Respect)*
*   **Behaviour:** We attack problems and processes, NOT individuals.
*   **Practice:** We use the "Yes, and…" mindset instead of "Yes, but…" to build on ideas. We always assume that everyone is doing the best they can given their current knowledge and context (Retrospective Prime Directive).
*   **Disagreement:** All perspectives are heard (no idea is stupid). Final decisions are reached through team consensus.

### 2. 🎯 FOCUS & COMMUNICATION *(Scrum Value: Focus)*
*   **Presence:** Personal device usage for non-work tasks during Scrum Events is not acceptable. If an urgent incident (e.g., hotfix) requires immediate attention, notify the team and step away rather than multitasking in the room.
*   **Punctuality:** Scrum Events start and finish on time (Timeboxed). If you will be late, notify the team in advance. The team starts without waiting.
*   **Communication:** Prefer high-bandwidth communication (face-to-face or video call) for complex or nuanced discussions over long email or message threads.
*   **Core Overlapping Hours:** [Agent: Fill in based on team's time zone distribution from C2 input, e.g., "10:00 AM – 15:00 PM (UTC+7)"]

### 3. 🤝 COMMITMENT & TRANSPARENCY *(Scrum Values: Commitment, Openness)*
*   **Artifact Updates:** The status of work items must be updated on the **Sprint Backlog** *before* each **Daily Scrum** begins.
*   **Quality is Non-Negotiable:** We never compromise on the **Definition of Done**. There is no "almost done". "Done" means zero known Severity-1 or Severity-2 defects and all DoD criteria met.
*   **Product Owner Availability:** The **Product Owner** commits to being available for or responding to clarification requests from the **Developers** within [Agent: fill in, e.g., "4 business hours"] to avoid creating a bottleneck.

### 4. 🦁 COURAGE & OPENNESS *(Scrum Values: Courage, Openness)*
*   **Ask for Help Immediately:** If blocked by an impediment for more than [Agent: fill in, e.g., "30 minutes"], escalate immediately rather than silently struggling. Surfacing blockers is a professional responsibility, not a sign of weakness.
*   **Swarming:** If a build fails or a teammate is blocked, the **Developers** prioritise stopping individual work to help the team recover before starting new tasks.
*   **Accountability Rule:** Any team member has both the right and the responsibility to respectfully call out behaviour that violates these Team Norms, in the spirit of continuous improvement.

---

*> **Socratic Closing Prompt (Agent Appends This):** "These are baseline suggestions derived from Scrum Values and your team context. Which of these norms do you believe your Developers will embrace most easily? Are there specific communication or quality challenges your team currently faces that we should address explicitly in these agreements?"*
