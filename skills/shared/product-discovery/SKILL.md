---
name: product-discovery
description: Use when the user describes any feature ideas, business problems, operational pain points, process issues, system requests, business goals, or vague stakeholder requests before a formal task execution.
---

# Product Discovery (Upstream Elicitation Engine)

## Overview

This module acts as the upstream elicitation engine. It ensures that the Senior Business Analyst Copilot uncovers the real business needs, challenges assumptions, and detects missing requirements **BEFORE** drafting specifications or solutioning.

It follows a discovery-first workflow based on the **IIBA® BABOK® Guide v3** standards.

---

## When to Use

Activate this skill whenever the user describes ANY of:
*   Feature ideas or requests ("we need X", "I want to build Y")
*   Operational pain points or manual process bottlenecks
*   Business problems, workflow frustrations, or KPI gaps
*   Compliance or regulatory concerns

### When NOT to Use
Do not use this skill when writing final deliverables (BRD/SRS/PRD) from already confirmed and fully-elicited specifications, drawing final diagrams, or writing test cases.

---

## Core Workflow

The discovery process runs incrementally. **Do NOT complete the whole loop in one response.** Progress 1-2 steps per turn, ask the user context-specific questions, integrate their answers, and move forward.

```
User Input
    ↓
1. Intent Detection          ← Classify the type of request
    ↓
2. Requirement Layer Check   ← Identify which of the 5 BABOK layers are missing
    ↓
3. Gap Detection             ← Determine knowns vs. unknowns
    ↓
4. Ask Strategic Questions   ← Present 3-5 high-context questions max
    ↓
5. Insight Extraction        ← Paraphrase, classify, and update findings
    ↓
6. Edge Case Scan            ← Prompt for exception flows
    ↓
7. Structured Summary        ← Once stop condition is met, generate summary
```

---

## Elicitation Steps

### Step 1 — Intent Detection
Classify the request's intent (e.g., Feature Request, Complaint, Operational Pain, Workaround, KPI Goal, Solution Bias, Business Objective, Process Issue, Reporting Need, Compliance Concern).
*   *Solution Bias Note:* When the user demands a specific tool or tech (e.g., "we need an AI chatbot"), treat the named solution as a *hypothesis to investigate*, never as a confirmed requirement. Focus on the problem behind it.

### Step 2 — Requirement Layer Check
Verify which BABOK layer is defined and which are missing, displaying this table:

| Layer | Question it answers | Status |
|---|---|---|
| Business Requirement | *Why* are we doing this? | ✅ / 🟡 / ⛔ |
| Stakeholder Requirement | *Who* needs what? | ✅ / 🟡 / ⛔ |
| Functional Requirement | *What* must the system do? | ✅ / 🟡 / ⛔ |
| Non-functional Requirement | *How well* must it do it? | ✅ / 🟡 / ⛔ |
| Transition Requirement | How do we *get from current to future state*? | ✅ / 🟡 / ⛔ |

### Step 3 — Gap Detection
List the **Knowns** and **Unknowns** across business objectives, actors, rules, edge cases, risks, and performance targets.

### Step 4 — Ask Context-Specific Questions
*   Ask **3-5 questions maximum per turn** to avoid overwhelming the user.
*   Prioritize: Business Impact → Root Cause → Actor/Stakeholder → Process Handoffs → Exception/Edge Cases.

### Step 5 — Business Insight Extraction
Paraphrase the user's answers, classify them (e.g., symptom, constraint, rule), and update the running discovery status.

### Step 6 — Edge Case Scan
Prompt for failure scenarios, data consistency issues, concurrency/duplicates, role-based access control, or regulatory controls (e.g., KYC, PII, PDPA).

### Step 7 — Stop Condition & Structured Summary
Stop elicitation only when goals are measurable, root causes are clear, requirements are actionable, and risks are surfaced. Present the final discovery artifact using the summary template.

---

## Reference Map

All supporting assets for this engine are de-branded and integrated:
*   **Intent Signals & Rules:** `references/detection-logic.md`
*   **Requirement Taxonomy:** `references/requirement-layers.md`
*   **Contextual Question Library:** `references/question-library.json`
*   **Discovery Output Schema:** `references/output-schema.json`
*   **Structured Output Template:** `templates/findings-summary.md`

After discovery is completed and agreed upon by the User, proceed to the **Readiness Check (Tollgate)** at `references/advisor/readiness-check.md` to transition to task execution.
