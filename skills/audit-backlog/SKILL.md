---
name: audit-backlog
description: Audits the product backlog for hygiene, story quality, and refinement readiness — identifying items that are too large, missing acceptance criteria, stale, unestimated, or out of priority order. Surfaces findings with severity levels and outputs formatted feedback for the user to copy-paste. Use when a Scrum Master or Product Owner says things like "audit the backlog", "is the backlog healthy", "review the backlog before refinement", "clean up the backlog", "check backlog hygiene", or "prepare the backlog for planning". Do not use for individual story audits — use audit-user-story for that.
---

# Backlog Audit

## Purpose

A neglected backlog is a planning liability. Items without acceptance criteria become guesswork in Sprint Planning. Items that haven't moved in months crowd out real priorities. Items sized too large cannot be completed in a Sprint. This audit surfaces all of it before it causes a problem, so the team walks into refinement with a clear picture of what needs attention.

---

## Step 1 — Collect Backlog Data

Ask the user to paste their backlog data. The data should ideally contain:
1.  **Backlog Level / Team Name**
2.  **List of top 20–40 Product Backlog Items (PBIs)** (including: Title/ID, Status/State, Story Points, Last Modified Date, whether it has Acceptance Criteria, and priority rank)

Store the content as `$BACKLOG_DATA`.

---

## Step 2 — Run the Health Checks

Evaluate `$BACKLOG_DATA` across the following four core criteria.

### 2a — Readiness (Definition of Ready)

| Check | Pass condition | Flag if |
|---|---|---|
| Has a title | Clear, action-oriented | Title is "Story", "TBD", or too vague to understand without context |
| Has a description | As a / I want / So that OR a clear description | Empty description |
| Has acceptance criteria | At least one testable AC | No acceptance criteria at all |
| Has an estimate | Story points > 0 | Unestimated (null or 0) |

### 2b — Size

| Check | Flag if |
|---|---|
| Story fits one Sprint | Story points > team's average Sprint velocity ÷ 2 (or > 13 points as a default threshold) |
| Epic disguised as story | Title or description spans multiple independent capabilities |

### 2c — Staleness

| Check | Flag if |
|---|---|
| Item is active | Last modified > 90 days ago AND still in New/Refining state |
| Item is not blocked | Tagged "Blocked" or "On Hold" with no resolution plan |
| Item is not a duplicate | Title is near-identical to another item in the backlog |

### 2d — Priority Coherence

- Are the top 10 items the ones the PO would actually commit to next Sprint?
- Are there items in the top 10 that depend on items ranked below them? (dependency inversion risk)

---

## Step 3 — Produce the Audit Report

Format the audit output as follows:

```markdown
Backlog Audit — [DATE]

Items reviewed: [N]
Items flagged: [N] ([X]%)

━━━ Critical — blocks Sprint Planning ━━━━━━━━━━━━━━━━━

Missing acceptance criteria: [N items]
  - #[ID] [Title] — last modified [date]
  - ...

Unestimated items in top 20: [N items]
  - #[ID] [Title]
  - ...

━━━ Size issues ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Oversized items (> [threshold] points): [N]
  - #[ID] [Title] — [N] points — consider splitting

━━━ Staleness ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Items not touched in 90+ days: [N]
  - #[ID] [Title] — last modified [date] — still in [state]

Blocked / On Hold with no path forward: [N]
  - #[ID] [Title] — tagged [tag] since [date]

━━━ Priority concerns ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Dependency inversions detected: [N]
  - #[ID] [Title] ranked above #[ID] [Title] which it depends on

━━━ Summary & Next Steps ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Refinement-ready (top [N] items): [N] of [N]
Recommended refinement focus: [list top 3–5 most critical items to fix]
```

---

## Step 4 — Output Shareable Recommendations

Output the audit report in a clean Markdown block so the user can easily copy and paste it into Confluence, a Wiki, a tracking issue, or share it on Slack/Teams.

Propose a prioritized **Refinement Agenda** order: critical items first (missing ACs, unestimated), then oversized (needs splitting), then stale or priority concerns.

---

## Guardrails

- Never change backlog priority (stack rank) without explicit PO confirmation — rank is a PO decision.
- Never mark items as Resolved or Closed — only flag for PO attention.
- If the backlog has more than 100 items, focus the detailed audit on the top 40 (the realistic planning horizon).
- Keep the tone peer-to-peer and supportive.
