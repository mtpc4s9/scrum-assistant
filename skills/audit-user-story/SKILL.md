---
name: audit-user-story
description: Audits an existing user story against Scrum best practices — checks INVEST criteria, story format, acceptance criteria quality, and Definition of Ready compliance. Raises findings with clear severity levels and outputs formatted feedback for the user to copy-paste. Use when anyone says things like "audit this story", "review this user story", "is this story ready", "check this PBI", "does this story meet best practices", or pastes a story and asks for feedback. Don't use for creating new stories, sprint planning, or general Scrum questions.
---

# User Story Audit

## Purpose

A story that is unclear, too large, or untestable wastes the whole team's time — in refinement, in planning, and in delivery. This skill runs a structured audit so issues are caught before the story enters a Sprint, not during one.

---

## Step 1 — Fetch the Story

Ask the user to paste the user story content directly into the chat (including title, description, acceptance criteria, or any other relevant details).

Store the content as `$STORY`.

---

## Step 2 — Run the Audit

Evaluate `$STORY` across four areas. Grade each check as:
- ✅ **Pass** — meets the standard
- ⚠️ **Warning** — present but weak; worth improving
- ❌ **Fail** — missing or clearly broken; blocks readiness

### Area 1 — Story Format

| Check | Pass condition |
|---|---|
| Title is action-oriented | Starts with a verb + noun (e.g., "View monthly summary") |
| Story statement present | Has "As a / I want / So that" or equivalent |
| Persona is specific | Not "user", "the system", or "admin" |
| "So that" states value | Names an outcome or benefit, not a restatement of the want |
| No implementation detail in the story | Story describes *what*, not *how* |

### Area 2 — Acceptance Criteria

| Check | Pass condition |
|---|---|
| ACs present | At least 3 criteria exist |
| ACs are conditions, not UI steps | Each AC describes an observable outcome, not a sequence of clicks |
| ACs are independently verifiable | Each AC can be tested without depending on another |
| Edge cases covered | Error states, empty states, or boundary conditions addressed where relevant |
| No ambiguous language | Avoid "should", "might", "fast", "easy" — prefer measurable specifics |

### Area 3 — INVEST

| Criterion | What to look for |
|---|---|
| **Independent** | Can this be delivered without another unfinished story? |
| **Negotiable** | Is the story a conversation starter, not a rigid spec? |
| **Valuable** | Does it deliver a real outcome to a user or the business? |
| **Estimable** | Enough detail for developers to size it? |
| **Small** | Completable within one Sprint by the team? |
| **Testable** | Can the ACs be verified objectively? |

Flag only the INVEST criteria that are genuinely at risk — not all six for every story.

### Area 4 — Definition of Ready

| Check | Pass condition |
|---|---|
| Persona named and understood | Team knows who this is for |
| Business value clear | PO can explain why this is prioritized now |
| Dependencies identified | Blockers or upstream dependencies are named |
| Size estimate present | Story has been sized (optional but flag absence) |
| No open assumptions | Any assumptions are captured and resolved |

---

## Step 3 — Present Findings

Format the audit output as follows:

```markdown
User Story Audit — [Title]
Audited: [DATE]

Story Format
  ✅ / ⚠️ / ❌  [Check]: [brief finding]

Acceptance Criteria
  ✅ / ⚠️ / ❌  [Check]: [brief finding]

INVEST
  ✅ / ⚠️ / ❌  [Criterion]: [brief finding]

Definition of Ready
  ✅ / ⚠️ / ❌  [Check]: [brief finding]

Overall readiness: Ready / Needs work / Not ready

Top recommendations
1. [Most important fix — be specific, offer a rewrite if helpful]
2. [Second fix]
3. [Third fix]
```

Keep findings concise — a one-line note per check is enough unless a rewrite is warranted. Offer a specific rewrite for the persona, "So that" clause, or individual ACs when the existing text is weak.

---

## Step 4 — Output Shareable Feedback

Output the audit comment in a clean Markdown block so the user can easily copy and paste it as a comment into their Project Management tool (Jira/Azure DevOps).

Frame the comment as constructive peer feedback, not a rejection:

> **Story Audit Findings** — [DATE]
>
> This story was reviewed against Scrum best practices. Here are the findings:
>
> [Paste the formatted findings block]
>
> These are suggestions to help the team get the most value from this story — happy to discuss any of them in refinement.

---

## Guardrails

- Never reject a story outright — frame every finding as an improvement opportunity.
- Never suggest story points or estimates — sizing belongs to the Developers.
- Never rewrite the full story without being asked — offer rewrites for specific weak sections only.
- If the story is clearly an epic (covers multiple independent workflows), say so clearly: *"This reads like an epic — the most valuable single story might be [X]. Want me to help split it?"*
- Keep the tone peer-to-peer. The audit is a team quality tool, not a gate kept by a single role.
