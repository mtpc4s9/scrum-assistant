---
name: audit-sprint-health
description: Audits a completed or in-progress sprint's health against Scrum best practices — checks Sprint Goal presence, issue hygiene, workflow transitions, field completeness, story point coverage, and Definition of Done consistency. Surfaces findings with severity levels and outputs formatted feedback for the user to copy-paste. Use when anyone says things like "audit our sprint", "review our sprint health", "are our issues following best practices", or "sprint health check".
---

# Sprint Health Audit

## Purpose

A healthy Sprint requires a clear goal, consistent quality baselines, and transparent workflow tracking. This audit evaluates the current Sprint backlog and team execution data, highlighting process gaps and hygiene issues so the team can inspect and adapt.

---

## Step 1 — Collect Sprint Data

Ask the user to paste their Sprint data. The data should ideally contain:
1.  **Sprint Goal** (if defined)
2.  **Sprint Duration & Current Day** (e.g., Day 5 of 10)
3.  **List of Sprint Backlog Items** (including: Title/ID, Status, Story Points, Assignee, and whether it has Acceptance Criteria / meets DoD)

Store the content as `$SPRINT_DATA`.

---

## Step 2 — Run the Audit

Evaluate `$SPRINT_DATA` across five core areas. Grade each check as:
- ✅ **Pass** — meets the standard
- ⚠️ **Warning** — worth improving
- ❌ **Fail** — missing or broken; impacts team effectiveness

### Area 1 — Sprint Goal (Scrum alignment)

| Check | Pass condition |
|---|---|
| Sprint Goal defined | Sprint has a clear, non-empty goal |
| Sprint Goal is outcome-oriented | Goal is a value statement, not a task list or feature dump |
| Backlog items relate to the Goal | The majority of committed items directly support the Sprint Goal |

A missing Sprint Goal means the team cannot assess whether the Sprint succeeded — it reduces the Sprint to a time-boxed to-do list.

### Area 2 — Backlog Hygiene

| Check | Pass condition |
|---|---|
| All items have an assignee | No unassigned "In Progress" or "Done" items |
| Parent/Epic alignment | Items are linked to an Epic or high-level Feature (provides context) |
| Clear and descriptive titles | No placeholder titles (e.g., "Fix bug", "Update UI") |

### Area 3 — Story Points and Sizing

| Check | Pass condition |
|---|---|
| All Stories have story points | No unpointed stories in the active Sprint |
| Reasonable point sizing | No single story is larger than half the team's average velocity (suggests it should be split) |
| Total commitment is realistic | Total story points committed are within the range of historical velocity (e.g., 85% to 100% of average) |

### Area 4 — Acceptance Criteria and Definition of Done (DoD)

| Check | Pass condition |
|---|---|
| Active stories have AC | AC is clearly defined before work starts (DoR) |
| Done items meet DoD | Checked items marked as "Done" have passed all QA, review, and compliance gates |
| Sub-task consistency | All sub-tasks are closed if the parent story is marked "Done" |

### Area 5 — Flow & Workflow Transitions

| Check | Pass condition |
|---|---|
| No skipped transitions | Items do not move directly from "To Do" to "Done" without peer review/QA stages |
| Work in Progress (WIP) limits | The number of active "In Progress" items matches team capacity (no bottlenecking in QA/Review) |
| Stale items flagged | No item is stuck in the same status for >3 days without update comments |

---

## Step 3 — Present the Audit Report

Format the audit output as follows:

```markdown
Sprint Health Audit — [SPRINT NAME/NUMBER]
Audited: [DATE]

Sprint Goal
  ✅ / ⚠️ / ❌  [Check]: [finding]

Backlog Hygiene
  ✅ / ⚠️ / ❌  [Check]: [finding]

Story Points & Sizing
  ✅ / ⚠️ / ❌  [Check]: [finding]

Acceptance Criteria & DoD
  ✅ / ⚠️ / ❌  [Check]: [finding]

Flow & Transitions
  ✅ / ⚠️ / ❌  [Check]: [finding]

Summary
  [N] passed · [N] warnings · [N] failed

Top recommendations
1. [Most impactful process or hygiene fix]
2. [Second recommendation]
3. [Third recommendation]
```

Keep findings concise and constructive.

---

## Step 4 — Output Shareable Feedback

Output the audit report in a clean Markdown block so the user can paste it into their team workspace, Retrospective board, or share it on Slack/Teams.

---

## Guardrails

- Never transition issue status, update fields, or reassign issues without explicit user confirmation.
- Never frame findings as individual failures — focus on team patterns and process health.
- If sprint data is incomplete (e.g., Sprint Goal missing, sprint still active), report the gap clearly rather than skipping the check.
- Keep the tone supportive and coaching-focused (servant leadership).
