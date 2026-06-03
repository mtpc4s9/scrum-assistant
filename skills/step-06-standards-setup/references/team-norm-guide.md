---
artifact_name: Team Norms (Working Agreements) Reference Guide
purpose: Provide the AI Agent with the behavioral, psychological, and Scrum-value-driven parameters required to facilitate the creation of a self-managing Scrum Team's ground rules.
---

### Team Norms Reference Guide
This document serves as the hidden cognitive framework for the Scrum Assistant during **Step 6 - Standards Setup**. It ensures the Agent drafts Team Norms that foster a psychologically safe, empirical, and self-managing environment, strictly adhering to the 2020 Scrum Guide and 'Essential Scrum' principles.

--------------------------------------------------------------------------------

#### 1. Core Principles of Team Norms
*   **Behavioral Manifestation of Scrum Values:** Team Norms translate the five Scrum Values (Commitment, Focus, Openness, Respect, and Courage) into everyday actionable behaviors.
*   **The Blame-Free Environment:** According to *Essential Scrum*, Team Norms must establish an atmosphere where expressing opinions, exploring what went wrong, and "airing dirty laundry" are considered safe. The focus must ALWAYS be on improving the systemic process, not blaming individuals.
*   **Self-Managing & Voluntary:** The Scrum Team internally decides who does what, when, and how. Therefore, Team Norms cannot be dictated by management, the Product Owner, or the Scrum Master. They must be collaboratively authored and unanimously agreed upon by the entire Scrum Team.

--------------------------------------------------------------------------------

#### 2. Essential Dimensions of a Team Norm (Agent Focus Areas)
When drafting or reviewing a baseline Team Norm, the Agent should cover the following dimensions:
1.  **Logistics & Cadence:** Core overlapping working hours (especially for distributed teams), punctuality for Scrum events, and availability of the Product Owner.
2.  **Transparency & Artifact Ownership:** Rules around updating the Sprint Backlog (e.g., "Always update remaining effort before the Daily Scrum"), making impediments visible, and ensuring the Product Backlog reflects reality.
3.  **Communication & Collaboration:** Ground rules for high-bandwidth communication (e.g., preferring face-to-face or video calls over long email threads), respectful dissent, and listening actively.
4.  **Quality & Focus:** Strict adherence to the Definition of Done, eliminating multitasking (working on one thing at a time), and asking for help immediately when blocked.

--------------------------------------------------------------------------------

#### 3. Agent Execution Directives
*   **Socratic Facilitation:** When the user (Scrum Master) asks to create a Team Norm, the Agent MUST NOT just print a final list. It must propose a baseline draft and append a prompt: *"These are baseline suggestions. Which of these do you think your Developers will embrace, and what specific communication challenges does your team currently face that we should add?"*
*   **Rejecting Punitive Rules:** If the user attempts to add a punitive rule (e.g., "Anyone late to the Daily Scrum is fined $5" or "Developers who write bugs will be formally reprimanded"), the Agent MUST respectfully challenge this using the Scrum Value of *Respect* and the principle of a blame-free environment.
*   **Mandatory Disclaimer:** Every generated `team-norm-presentation-deck.md` MUST include a disclaimer: *"This is a living document owned by the Scrum Team. It must be physically or digitally signed by all members to be valid, and should be inspected and adapted frequently during Sprint Retrospectives."*
