# Requirement Layers — BABOK v3 Taxonomy

*Aligned with IIBA® BABOK® Guide v3 §3 Standards*

This reference classifies every requirement into one of five standard layers. Most user inputs start at the Business or Stakeholder layer — lower layers are often empty initially. The BA Copilot's job is to populate the missing layers progressively through interactive elicitation.

---

## 1. Business Requirement

**Definition:** *Why* the organization is performing the initiative — the goal, the problem, the underlying business value.

**Owner:** Executive Sponsor / Product Owner / Business Unit Head.

**Example:**
> "Increase student application conversion rate from 45% to 60% by the upcoming Academic Year, to optimize admissions capacity and reduce marketing acquisition cost per student."

**Empty-layer signal:** The user describes a system feature but cannot state why it matters to the organization.
→ Ask: *"What business KPI does this impact? What happens if we don't build this?"*

---

## 2. Stakeholder Requirement

**Definition:** *Who* needs what, expressed from the perspective of the stakeholder / user role.

**Owner:** End-user / Business Stakeholder / Domain SME.

**Example:**
> "As a School Registrar, I need to see the integration status of student records between iSAMS and Toddle in a single view so that I can resolve syncing discrepancies before grades are locked."

**Empty-layer signal:** The user describes system behaviors but no specific stakeholder, actor, or role is named.
→ Ask: *"Who is the primary actor or stakeholder for this capability? What is their exact context?"*

---

## 3. Functional Requirement

**Definition:** *What* the system must do — behaviors, data transformations, inputs, outputs, and business logic.

**Owner:** Business Analyst / Product Manager / Solution Architect / Tech Lead.

**Example:**
> "The system shall flag any student record that fails to synchronize between the SIS and Toddle, write a detailed error log with the iSAMS Student ID, and send an alert notification to the assigned Registrar's queue."

**Empty-layer signal:** The user is at the stakeholder-need level but no concrete system actions or data inputs/outputs are articulated.
→ Ask: *"What specific behavior, validation, or data output must the system execute when this event occurs?"*

---

## 4. Non-functional Requirement (NFR)

**Definition:** *How well* the system must perform its functions — performance, availability, security, scalability, usability, compliance, and supportability.

**Owner:** Enterprise Architect / Security Engineer / DevOps / Compliance Officer.

**Example:**
> "The student data sync API must complete synchronization within 5 seconds of the source change. Student record data must comply with local privacy regulations (GDPR/PDPA) and be encrypted at rest and in transit using TLS 1.3."

**Empty-layer signal:** Functional requirements exist but no quantitative quality attributes or architectural constraints have been stated.
→ Ask: *"What are the quantitative performance targets, uptime expectations, security controls, or data compliance policies required for this capability?"*

---

## 5. Transition Requirement

**Definition:** What capabilities are required to transition from the *current* (As-Is) state to the *future* (To-Be) state — data migration, business process changes, training, cutover, and parallel run operations.

**Owner:** Project Manager / Change Management Lead / Operations Lead.

**Example:**
> "Migrate 3 years of historical student records from the legacy database to Odoo. Run both systems in parallel for 14 days post-deployment. Conduct a 4-hour training session for all Academic Coordinators before go-live."

**Empty-layer signal:** The future state is agreed upon, but there has been no discussion of *how the organization successfully moves from As-Is to To-Be*.
→ Ask: *"What historical data must be migrated? What training or process changes are needed for the users? Is there a parallel run or rollback strategy?"*

---

## Layer Status Table (Required Every Turn)

After collecting new elicitation details, present this table to make the discovery status visible to the User:

| Layer | Status | Evidence / Notes |
|---|---|---|
| Business Requirement | ✅ / 🟡 / ⛔ | *[one-line summary of verified business goal]* |
| Stakeholder Requirement | ✅ / 🟡 / ⛔ | *[one-line summary of user roles and needs]* |
| Functional Requirement | ✅ / 🟡 / ⛔ | *[one-line summary of system behaviors]* |
| Non-functional Requirement | ✅ / 🟡 / ⛔ | *[one-line summary of quantitative targets/security]* |
| Transition Requirement | ✅ / 🟡 / ⛔ | *[one-line summary of migration/cutover plan]* |

**Legend:**
*   **✅** = Clear, complete, and confirmed.
*   **🟡** = Partial information collected — more detail required.
*   **⛔** = Empty — not yet discussed.
