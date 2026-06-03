---
artifact_name: MRF and Roadmapping Reference Guide
purpose: Equip the AI Agent with the strategic logic to organize a High-Level Product Backlog into a viable, empirical Product Roadmap using Minimum Releasable Features (MRFs).
---

### MRF and Roadmapping Reference Guide
This document instructs the Scrum Assistant on how to group and schedule items from the Story Map into sequential, value-driven releases during **Step 4**. It prevents the Agent from creating predictive, fixed-Gantt-chart roadmaps.

--------------------------------------------------------------------------------

#### 1. Core Mechanics
A Product Roadmap communicates the incremental nature of how the product will be built and delivered. To avoid becoming a "feature factory," the Scrum Team must define the smallest set of features necessary to validate the core business assumptions.

#### 2. The MRF Logic (Agent Thought Process)
When mapping Epics and Features onto a Product Roadmap, the Agent must internally categorize the items:

*   **Must-Have (Minimum Releasable Features - MRFs):** The absolute minimum features required to meet customer value and quality expectations. If one of these is missing, the release is not viable.
*   **Nice-to-Have:** Features that provide value but can be dropped if constraints (time/budget) tighten.
*   **Won't-Have:** Features explicitly declared out of scope for the current horizon.

#### 3. Agent Execution Directives
*   **Draw the Release Line:** When generating the `product-roadmap.md` artifact, place all "Must-Have" items from the top horizontal slice of the Story Map into **Release 1.0 (MVP)**.
*   **Protect the Goal, Flex the Scope:** Ensure that Release 1.0 does NOT consume 100% of anticipated capacity. Leave room for emergent requirements.
*   **Mandatory Empirical Disclaimer:** The Agent MUST prepend every generated Roadmap with a warning: *"This roadmap is an empirical forecast, not a fixed-date commitment. It will adapt based on market feedback and Increment inspection."*
