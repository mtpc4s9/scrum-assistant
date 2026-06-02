# Detection Logic — Intent Classification

*Aligned with IIBA BABOK v3 Standards*

Use this reference when the user's wording is ambiguous. Each intent type lists signal phrases and the recommended first response.

---

## 1. Feature Request

**Signals:** "I want to add", "we need to build", "add a button for", "can we support feature X".

**Risk:** Stakeholder is already in solution mode. Treat the feature as a *hypothesis to test*.

**First response:** Ask about the underlying business problem, the impacted users, and the success metrics before discussing any feature details.

**Enterprise Platform Example:**
> "We need a progress tracker on our student enrollment portal."
> → Don't design the tracker yet. Ask: *What problem does the applicant have today? Are they unaware of their application status, or is there a communication gap between admissions and applicants?*

---

## 2. Complaint

**Signals:** "X is broken", "users are unhappy with", "the platform is too slow", "we keep getting support tickets about".

**Risk:** The symptom is described, but the root cause is unknown.

**First response:** Use 5-Whys to drill from symptom to root cause. Ask for frequency and business impact before proposing any fix.

**Example:**
> "Registrars say the student sync takes forever."
> → Is the problem the database query, the API gateway, or network latency? What is the frequency? Does it happen during peak enrollment windows?

---

## 3. Operational Pain

**Signals:** "the ops team spends hours doing", "manual reconciliation", "copy-paste between systems", "admin team does this by hand every week".

**Risk:** Users have built workarounds — the real cost is hidden labor.

**First response:** Quantify the labor cost (hours × people × frequency), ask who owns the process today, and what happens when they are unavailable.

---

## 4. Workaround

**Signals:** "we currently do this by exporting to Excel and...", "we use chat channels to coordinate approvals", "the team manages schedules via shared spreadsheets".

**Risk:** The workaround masks the real requirement. Stakeholders may demand the workaround be productized, but a different solution may serve better.

**First response:** Ask why the workaround exists, what the original gap was, and what would happen if the workaround were removed tomorrow.

**ERP Example:**
> "We track inventory adjustments in an offline Excel sheet before importing to Odoo."
> → Why? Does Odoo not support the inventory adjustment workflow directly? Is it a permission issue or a lack of user training?

---

## 5. KPI Goal

**Signals:** "we want to reduce churn by", "increase enrollment rate from X% to Y%", "grow monthly revenue by Q4".

**Risk:** The KPI is clear but the lever to pull is unknown.

**First response:** Ask which user or operator behavior drives the KPI today, and which candidate levers the business is considering. Don't jump to solutions.

---

## 6. Solution Bias ⚠️ HIGHEST PRIORITY

**Signals:** User names a specific technology, platform, or feature pattern as the requirement. "We need AI", "build a recommendation engine", "use blockchain for transcripts".

**Risk:** Stakeholder has skipped problem-discovery entirely.

**First response:** Politely surface the bias. Do not scope the named solution until the business problem is articulated clearly.

**Script:**
> "Before I scope [the solution], I want to make sure it's the right answer. '[Solution name]' is a tool — let's find the problem it's meant to solve first. A few questions: what's breaking today, who experiences it, and how would we measure success?"

**Never** ask what features the named technology should have until you've confirmed the problem justifies that type of solution.

---

## 7. Business Objective

**Signals:** "our OKR this quarter is", "leadership wants us to", "the board asked for".

**Risk:** Objective is high-level; multiple feature paths could satisfy it.

**First response:** Decompose into candidate problem statements, then ask which one is the actual bottleneck today.

---

## 8. Process Issue

**Signals:** "the course registration flow has too many steps", "approval for Odoo purchase orders takes too long", "handoff between Admissions and Finance is unclear".

**Risk:** Process redesign may be in scope, not just a system tweak.

**First response:** Map the as-is flow (steps, actors, handoffs, decision points) before discussing the to-be state. Never design a new flow without understanding the current one.

---

## 9. Reporting Need

**Signals:** "I need a report that shows", "can you export student records", "we need a dashboard for sales performance".

**Risk:** Stakeholder may want a static export when a live dashboard would serve them better — or vice versa.

**First response:** Ask who consumes the report, how often, and what decision it drives. Then evaluate: report vs. dashboard vs. API vs. automated alert.

---

## 10. Compliance Concern

**Signals:** "regulation requires", "auditor flagged", "we need to comply with GDPR / PDPA / KYC", "Ministry of Education requirement".

**Risk:** Compliance language is often imprecise. The actual control required may be narrower than the regulatory citation suggests.

**First response:** Ask for the specific clause or auditor finding, the deadline, and the consequence of non-compliance. Then translate into a testable control requirement.

---

## Ambiguous cases

If the input doesn't clearly fit one type, default to **Feature Request** and ask:
> *"Before I scope this, can you tell me what business problem this is solving and who experiences it most?"*
