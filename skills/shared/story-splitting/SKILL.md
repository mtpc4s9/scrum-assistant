---
name: story-splitting
description: >
  Applies proven story splitting patterns to break an oversized user story or epic into sprint-sized, independently deliverable stories.
  Triggered when the user says: "this story is too big", "we need to split this", "this will not fit in a sprint", "break this epic down", "help me slice this story", "fails INVEST", or in Vietnamese: "tách user story", "chia nhỏ story", "split story", "tách nhỏ công việc", "phân rã story".
license: MIT
compatibility: Platform agnostic. Designed for manual copy-paste workflow. Does not directly modify target ticketing systems, keeping all control with the user.
metadata:
  ceremony: Backlog Refinement
  perspective: Product Owner / Developer
  scrum_guide_ref: https://scrumguides.org/scrum-guide.html
  version: "1.0.0"
---

# Story Splitting

## Purpose

A story that cannot fit in one Sprint is a planning liability — it blocks commitment, obscures progress, and almost always hides scope nobody agreed to. This skill applies the nine proven splitting patterns to turn one large story into multiple small ones, each independently valuable and completable in a single Sprint.

---

## Step 1 — Get the Story

Ask the user to paste the content or provide the title and description of the User Story or Epic that needs splitting.

Store this as `$STORY`.

---

## Step 2 — Diagnose Why It Is Too Large

Before splitting, understand *what* makes it large. This determines which pattern fits best.

Ask yourself — and the PO if needed:
- Does it cover **multiple user types**? → split by persona
- Does it span **multiple workflow steps** end-to-end? → split by workflow
- Does it handle **many data variations or edge cases**? → split by data
- Does it cover **both the happy path and error handling**? → split happy/unhappy
- Does it need to work across **multiple channels** (web, mobile, API)? → split by interface
- Does it include **both basic and high-performance** versions? → split by performance
- Does it bundle **create, read, update, delete**? → split by operation (CRUD)
- Does it mix **a core feature with validation, logging, or notifications**? → split cross-cutting concerns
- Does it depend on **a system integration that is not ready**? → defer the integration, stub it first

---

## Step 3 — Apply the Best-Fit Pattern

### Pattern 1 — Workflow Steps
Split the story at each step in the user's journey. Each step becomes its own story.

```
Original: As a manager, I want to approve expense claims end-to-end.

Split:
→ Submit an expense claim for approval
→ Review pending expense claims as a manager
→ Approve or reject an individual claim
→ Receive a decision notification as a claimant
```

### Pattern 2 — Business Rule Variations
Keep the happy path in one story. Each significant business rule variation becomes its own story.

```
Original: Apply discount rules to an order at checkout.

Split:
→ Apply a fixed percentage discount code at checkout
→ Apply a tiered loyalty discount based on account history
→ Apply free-shipping thresholds to qualifying orders
```

### Pattern 3 — Happy Path / Unhappy Path
Deliver the working case first. Error handling, edge cases, and validation follow as separate stories.

```
Original: Export transaction history with full validation.

Split:
→ Export transaction history as CSV for a valid date range [happy path]
→ Show an error when the date range exceeds 12 months [unhappy path]
→ Handle export timeouts gracefully for large datasets [edge case]
```

### Pattern 4 — Data Variations
Same operation, different data types or states.

```
Original: Manage all document types in the file library.

Split:
→ Upload and preview PDF documents
→ Upload and preview image files
→ Upload and preview spreadsheets
```

### Pattern 5 — Interface / Channel
Deliver one channel first. Other channels follow as separate stories.

```
Original: Receive low-balance alerts across all channels.

Split:
→ Receive low-balance alerts via email
→ Receive low-balance alerts via push notification
→ Receive low-balance alerts via SMS
```

### Pattern 6 — Operations (CRUD)
Split by create, read, update, delete. Read is usually the most valuable starting point.

```
Original: Manage team members.

Split:
→ View the list of current team members [Read]
→ Add a new team member [Create]
→ Update a team member's role [Update]
→ Remove a team member [Delete]
```

### Pattern 7 — Performance
Deliver basic functionality first. Optimised performance is a separate story.

```
Original: Generate the annual report with real-time data.

Split:
→ Generate the annual report from cached data [basic]
→ Generate the annual report with real-time refresh [optimised]
```

### Pattern 8 — Deferred System Integration
Replace the integration with a manual or stub step. Automate it as a follow-up story.

```
Original: Sync approved claims to the accounting system automatically.

Split:
→ Export approved claims as a CSV for manual upload to accounting [stub]
→ Sync approved claims to the accounting system via API [automation]
```

### Pattern 9 — Cross-Cutting Concerns
Deliver core functionality first. Add notifications, audit logs, and validation as follow-up stories.

```
Original: Create a project with full validation, notifications, and audit log.

Split:
→ Create a project with basic required fields
→ Validate project name uniqueness across the organisation
→ Notify project stakeholders when a project is created
→ Log project creation events to the audit trail
```

---

## Step 4 — Present the Split

For each resulting story, produce a complete draft:

```
Split Story [N] of [total]

Title: [action-oriented title]
As a [specific persona],
I want [concrete action],
so that [measurable benefit].

Acceptance Criteria:
- [ ] [Observable condition]
- [ ] [Observable condition]

Size signal: [Small — fits one Sprint / Medium — verify with team]
Dependency: [None / Depends on Story N being done first]
```

Then present the full set and ask: *"Does this split make sense? Any stories to merge, rename, or reorder?"*

---

## Step 5 — Present for Copy-Paste

After the user confirms the proposed split:
1. Output the final refined list of all split User Stories with Gherkin-style Acceptance Criteria.
2. Prompt the user to copy-paste the outputted Markdown content to JIRA/ADO to create the new Product Backlog Items manually.
3. Remind the user to reference the original oversized story's ID or parent (Epic/Feature) when creating the new stories.

---

## Step 6 — Verify Against Definition of Ready (DoR)

Before completing the handoff back to the Backlog Refinement orchestrator (Step 10):
1. Validate that each new split story complies with the Definition of Ready (DoR) standard at [../../step-06-standards-setup/templates/definition-of-ready.md](../../step-06-standards-setup/templates/definition-of-ready.md).
2. Ensure each story is small enough, independent, and clear.

---

## Guardrails

- Every split story must be independently valuable — if story N is useless without story N+1, it is not a valid split.
- Never split by technical layer (frontend story, backend story, database story) — that is task decomposition, not story splitting. A story must deliver user value end-to-end.
- If a story cannot be split without losing value, say so: *"This story is atomic — the value only exists when all parts are present. Consider whether the whole story fits in the Sprint with the current team capacity."*
- Keep the original story's parent link on all split stories — they should all trace back to the same Feature or Epic.
