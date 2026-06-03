---
artifact_name: User Story Mapping Reference Guide
purpose: Provide the AI Agent with Jeff Patton's 2D spatial framework for decomposing a Product Goal into a user-centric Product Backlog, avoiding the trap of a flat, contextless feature list.
---

### User Story Mapping Reference Guide
This document serves as the hidden cognitive framework for the Scrum Assistant during **Step 4 - Backlog Creation**. Before generating the High-Level Product Backlog or Epic/Feature Tree, the Agent MUST process the raw inputs through this sequential mapping logic.

--------------------------------------------------------------------------------

#### 1. Core Mechanics
A traditional Product Backlog is a one-dimensional priority queue. Story Mapping adds a second dimension (the user journey) to discover the right solution, visualize the big picture, and establish a development strategy for fast learning.

#### 2. The 3-Layer Decomposition (Agent Thought Process)
When the user provides a Product Goal, the Agent must silently construct the map top-down:

*   **Layer 1: The Backbone (Key Activities)**
    *   *Concept:* The chronological flow of high-level activities a user must take to achieve their goal (e.g., Register -> Find Product -> Checkout -> Track).
    *   *Action:* Identify 3-5 Key Activities from the user's perspective.
*   **Layer 2: The Walking Skeleton (Epics)**
    *   *Concept:* The large, high-level features that make up each Key Activity.
    *   *Action:* Break down each Key Activity into 1-3 Epics. Ensure no Epic represents a purely technical component (e.g., "Database setup" is invalid; it must be user-valuable).
*   **Layer 3: The Map (User Stories / Slices)**
    *   *Concept:* The actionable, sprintable user stories decomposed from the Epics, arranged vertically.
    *   *Action:* Slice the Epics vertically by priority. Place the most critical stories (the "Must-Haves") at the top, and the "Nice-to-Haves" or alternative flows lower down.

#### 3. Agent Execution Directives
*   **Never Lose Context:** Ensure every User Story or Epic generated explicitly traces back to a Key Activity on the Backbone. Eliminate orphan features.
*   **Apply the 'Last Responsible Moment' (LRM):** Do not over-detail stories that are placed low on the vertical axis (future releases). Detail appropriately based on proximity to development.
