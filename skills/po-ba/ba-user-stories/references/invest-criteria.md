---
description: Detailed explanation of the 6 INVEST quality criteria for Agile User Stories with violation symptoms, remedies, and examples.
metadata:
  tags: [invest, agile, user-story, quality-check]
  source: internal
---

# INVEST Criteria - Detailed Guide

The **INVEST** framework, proposed by Bill Wake in 2003, is the industry standard for evaluating and ensuring the quality of Product Backlog Items (User Stories) in Agile and Scrum methodologies.

---

## I - Independent

### Definition
A User Story should be self-contained and deliver a distinct slice of business value. It should be possible to prioritize, develop, test, and release a story independently of other backlog items. Avoid tight coupling between stories.

### Why it Matters
*   Allows the Product Owner (PO) to reorganize and reprioritize the backlog dynamically.
*   Prevents cascading delays or "blockers" if a related story is delayed.
*   Simplifies work allocation and sprint planning for the development team.

### Violation Symptoms
*   "Story B cannot be started or tested until Story A is fully completed and merged."
*   Deploying a single feature requires merging and releasing 3-4 separate stories simultaneously.
*   QA cannot run test cases for a story without depending on the state created by another in-progress story.

### Remedies
*   **Merge:** Combine small, highly dependent stories into a single, cohesive story.
*   **Decouple:** Extract the shared dependency into an independent upstream story (e.g., initial setup or infrastructure) and prioritize it first.
*   **Mocking:** Use mock data, stubs, or test environments to simulate missing dependencies during development and testing.

### Practical Example
*   ❌ **Violation:**
    *   `US-01`: Create Customer Account.
    *   `US-02`: Enroll in E-Course (can only be developed and tested after `US-01` is completed).
*   ✅ **Standardized:**
    *   `US-01`: Create Customer Account (tested independently using database validation).
    *   `US-02`: Enroll in E-Course (decoupled by testing using pre-existing seed customer accounts in the test database).

---

## N - Negotiable

### Definition
A User Story is not a rigid legal contract or a detailed specification document; it is an **"invitation to a conversation."** The details of the implementation are negotiated and refined collaboratively between the business (PO/BA) and the technical team (Dev/QA) during backlog refinement and sprint execution.

### Why it Matters
*   Leverages the technical expertise of developers and QA to find more efficient, creative, or cost-effective solutions.
*   Maintains flexibility to adapt to new technical findings or market feedback.
*   Prevents premature optimization and over-specification.

### Violation Symptoms
*   A story narrative spans 3 pages, specifying pixel-perfect layouts, field sizes, and database names.
*   The narrative specifies a rigid technical implementation (e.g., "must use Redis cache with a 15-minute TTL, using SHA-256...").
*   Developers simply execute instructions blindly without understanding the business problem or offering alternatives.

### Remedies
*   Keep the story narrative focused strictly on the "What" and "Why."
*   Move design constraints to the "Acceptance Criteria" or attach wireframes/technical specifications separately.
*   Use low-fidelity sketches or wireframes instead of high-fidelity mockups in early refinement stages to encourage design suggestions.

### Practical Example
*   ❌ **Violation:**
    *   "As a registered student, I want the system to authenticate me using a 256-bit AES-encrypted JWT token stored in `localStorage` with a 15-minute refresh rotation, so that I don't have to re-login."
*   ✅ **Standardized:**
    *   "As a registered student, I want to log in securely to PlatformX, so that I can access my courses without repeated authentication."
    *   *(Note: The technical security implementation is negotiated during refinement and documented in the technical design.)*

---

## V - Valuable

### Definition
Every User Story must deliver clear, recognizable value to a customer, end-user, or the business. Technical tasks that do not yield observable value should not be framed as user stories.

### Why it Matters
*   Ensures that every development effort generates a return on investment (ROI).
*   Enables the PO to make value-based prioritization decisions.
*   Helps external stakeholders understand the progress and business impact of the sprint.

### Violation Symptoms
*   The "So that..." clause in the narrative is empty, repeats the action, or is vague (e.g., "...so that the feature works").
*   The story is written purely for developer convenience (e.g., "Refactor database helper class").
*   No one can clearly answer the question: *"What happens if we do not build this story in this sprint?"*

### Remedies
*   Write the "So that..." clause using the formula: `Measurable Business Outcome` or `Direct User Benefit`.
*   Wrap technical debt or refactoring work into a valuable business story (e.g., "Optimize database performance so that checkout page load times are under 2 seconds").
*   Apply the **5 Whys** technique to surface the underlying business value.

### Practical Example
*   ❌ **Violation:**
    *   "As a developer, I want to upgrade the video player library from v2 to v4, so that we use the latest library version."
*   ✅ **Standardized:**
    *   "As a student, I want course videos to buffer and play in under 3 seconds even on low-bandwidth connections, so that I can continue learning without interruption."
    *   *(Note: Upgrading the video player library is the solution, but the value is fast video playback under weak network conditions.)*

---

## E - Estimable

### Definition
The development team must have sufficient domain and technical understanding to estimate the relative effort, complexity, and time required to complete the story (often represented in Story Points).

### Why it Matters
*   Allows the team to accurately plan sprint capacity and predict delivery.
*   Helps the PO perform cost-benefit analysis before prioritizing.
*   Highlights stories that are too complex or poorly understood before they enter execution.

### Violation Symptoms
*   Developers state: "We have no idea how long this will take; we need to research first."
*   Story point estimations among team members vary wildly (e.g., ranging from 2 points to 21 points).
*   The story contains major unknown technical dependencies or unconfirmed external API contracts.

### Remedies
*   **Spike Story:** Create a dedicated, time-boxed research task (a "Spike") to investigate the technology. The primary output is a technical proposal, allowing the main story to be estimated in the next sprint.
*   Break down complex stories into smaller, more understandable slices.
*   Provide clear system constraints, UI sketches, and external API documentation as references.

### Practical Example
*   ❌ **Violation:**
    *   "As a student, I want an AI-powered system to automatically recommend a customized learning path based on my background." *(Too vague, unknown algorithm, unknown data inputs).*
*   ✅ **Standardized:**
    *   `Spike-01`: "Research recommendation algorithms and evaluate required data inputs for student profiles. Output: Technical Architecture Proposal (Max: 3 days)."
    *   `US-02`: "Implement the profile recommendation engine as defined in the approved `Spike-01` architecture."

---

## S - Small

### Definition
A User Story should be small enough to be fully designed, developed, tested, and accepted within a single sprint (typically 1 to 3 working days for a single developer). It must represent a small, manageable vertical slice of a feature.

### Why it Matters
*   Reduces planning risk and increases sprint predictability.
*   Enables rapid feedback loops and early testing.
*   Simplifies code reviews, builds, and rollbacks.

### Violation Symptoms
*   The story estimation is greater than 5 working days (or > 8 story points).
*   The story contains more than 7-8 acceptance criteria scenarios.
*   The narrative contains multiple CRUD operations (Create, Read, Update, and Delete all in one story).
*   The story title contains the word "AND" (e.g., "Add profile image AND change password").

### Story Splitting Strategies
1.  **By CRUD operations:** Split a large feature into separate Create, Read, Update, and Delete stories.
2.  **By Business Rules:** Handle the simple "Happy Path" first, and write separate stories for validations and complex business rules.
3.  **By Persona/Actor:** Separate stories based on who is performing the action (e.g., student vs. admin).
4.  **By Data Type/Complexity:** Start with text input first, then write a separate story for media attachments (e.g., image, video, document uploads).
5.  **By Workflow Step:** Split a long multi-step workflow into individual step-by-step stories (e.g., Step 1: Select items -> Step 2: Enter shipping -> Step 3: Authorize payment).

### Practical Example
*   ❌ **Violation:**
    *   "As a student, I want to manage my profile page (view details, update name, change password, upload an avatar image, and delete account)."
*   ✅ **Standardized (Split):**
    *   `US-01`: View personal profile details.
    *   `US-02`: Update profile display name.
    *   `US-03`: Change account password.
    *   `US-04`: Upload avatar profile image.
    *   `US-05`: Request account deletion.

---

## T - Testable

### Definition
A User Story must have clear, measurable, and objective criteria that allow the team to verify whether the story has been implemented successfully and is "Done."

### Why it Matters
*   Prevents subjective debates during sprint reviews regarding whether a feature is complete.
*   Enables QA engineers to draft test cases and test automation scripts early.
*   Aligns stakeholder expectations with actual system behavior.

### Violation Symptoms
*   Acceptance criteria contain vague or subjective terms (e.g., "fast", "intuitive", "beautiful", "user-friendly").
*   The story has no acceptance criteria, only a narrative card.
*   The criteria are impossible to verify through manual or automated test execution.

### Remedies
*   Write acceptance criteria using the strict **Gherkin Given-When-Then** syntax.
*   Replace subjective adjectives with measurable metrics (e.g., replace "loads quickly" with "loads in under 2 seconds").
*   Clearly define success messages, error states, and database transformations.

### Practical Example
*   ❌ **Violation:**
    *   "Acceptance Criteria: The login system must respond quickly and display a friendly error message when the user fails."
*   ✅ **Standardized:**
    *   "**Scenario: Failed login attempts**
       - **GIVEN** a registered customer has entered an incorrect password 3 consecutive times,
       - **WHEN** the customer attempts to log in a 4th time,
       - **THEN** the system blocks the login attempt and displays the message: 'Your account is temporarily locked for 15 minutes due to security rules.',
       - **AND** the system sends a security alert email to the customer's registered email address."

---

## INVEST Quick Lookup Table

| Letter | Quality Metric | One-Line Evaluation Question |
| :--- | :--- | :--- |
| **I** | **Independent** | Can this story be developed and shipped without depending on in-progress stories? |
| **N** | **Negotiable** | Does the story focus on the business need, leaving implementation details open? |
| **V** | **Valuable** | Does this story deliver clear, observable benefit to a user or the business? |
| **E** | **Estimable** | Does the development team understand the scope well enough to estimate its effort? |
| **S** | **Small** | Can this story be fully completed, tested, and accepted in 1-3 days? |
| **T** | **Testable** | Are the acceptance criteria objective and measurable for QA test design? |

---
