---
artifact_name: Lean Business Model Canvas Reference Guide
purpose: Provide the AI Agent with a structured analytical framework to dissect raw product ideas into economic and customer-centric dimensions before synthesizing Product Visions or Elevator Pitches.
---

### Lean Business Model Canvas Reference Guide
This document serves as the foundational economic and strategic thought process for the AI Agent during **Step 1 - Visioning**. It aligns the raw product idea with Empirical Process Control and Lean Thinking principles before generating physical artifacts (like the Elevator Pitch or Product Vision Board).

--------------------------------------------------------------------------------

#### 1. Core Mechanics
In agile product management, a product is a vehicle to deliver value, balancing both short-term growth and long-term sustainability [3]. Before crafting a compelling Product Vision, the Product Owner must understand the business model. This canvas identifies the rationale of how an organization creates, delivers, and captures value [2].

The AI Agent must internally evaluate the user's input against the following 9 blocks (adapted from the Business Model Canvas and Lean Canvas) to ensure the idea is economically viable and customer-centric [4, 5].

--------------------------------------------------------------------------------

#### 2. The 9 Analytical Blocks (Agent Thought Process)

**1. Customer Segments (WHO)**
*   *Analysis:* Who gets value from this product? Differentiate between the *Consumer* (who uses it) and the *Buyer* (who pays for it) [6]. 
*   *iGaming Context:* Is the target segment Casual Players, VIPs, or internal roles like Compliance Officers or Customer Support?

**2. Problem / Needs (WHY)**
*   *Analysis:* What specific pain points, needs, or opportunities does this product address for the Customer Segments? [7]

**3. Unique Value Proposition (Tell It and Sell It)**
*   *Analysis:* How does this product solve the problem? It must be both *Practical* (what it actually does) and *Emotional* (how it makes the user feel, e.g., peace of mind, excitement) [8, 9].

**4. Solution / Product (WHAT)**
*   *Analysis:* What are the 3-5 core capabilities or high-level features that form the initial foundation (the Minimum Viable Product - MVP)? [10, 11].

**5. Revenue Streams / Business Value (PRODUCER BENEFIT)**
*   *Analysis:* How does this product generate value for the organization? Focus on direct revenue, cost savings, risk mitigation, or compliance [12, 13].

**6. Channels**
*   *Analysis:* How will the value proposition be delivered to the customers? (e.g., App stores, affiliate marketing, direct B2B integration) [7].

**7. Key Metrics (Evidence-Based Management - EBMgt)**
*   *Analysis:* How will we empirically validate that value is delivered? Identify lagging and leading indicators (e.g., Current Value, Time to Market, Ability to Innovate, Usage Index) [14-16].

**8. Cost Structure**
*   *Analysis:* What are the major investments required? Consider the cost of the Developers (Sprint run-rates), operational costs, and the long-term cost of potential Technical Debt [17, 18].

**9. Unfair Advantage / Key Partnerships**
*   *Analysis:* What constraints or assets give this product an edge? (e.g., exclusive 3rd-party vendor contracts like Kambi/Pragmatic, proprietary RNG algorithms, or existing regulatory licenses) [19].

--------------------------------------------------------------------------------

#### 3. Agent Directives & Execution Logic

**A. Hidden Pre-Processing (Do Not Output the Canvas unless explicitly requested):**
When the user requests an *Elevator Pitch* or *Product Vision Board*, the Agent **MUST** first silently map the user's raw idea against these 9 blocks. 

**B. Socratic Discovery for Missing Links:**
If the user's input critically lacks data for Block 1 (Customer Segments), Block 2 (Problem), or Block 5 (Business Value), the Agent must pause generation. 
*Action:* Invoke `shared/product-discovery` tactics to ask the user clarifying questions. *Example:* "I see the features (Solution), but to craft a compelling vision, how exactly will this generate revenue or reduce costs (Revenue Streams) for the target user?"

**C. Artifact Synthesis:**
Once the 9 blocks are internally populated:
*   Use Blocks 1, 2, 3, 4, and 5 to populate the *Product Vision Board* (Roman Pichler format) [20].
*   Distill Blocks 1, 2, 3, and 4 through the "2 Brains" technique (Practical + Emotional) [8, 21] to generate the *Elevator Pitch* (Geoffrey Moore format) [22].