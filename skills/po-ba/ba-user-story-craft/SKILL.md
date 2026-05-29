---
name: ba-user-story-craft
description: Use when drafting, documenting, or refining user stories and writing acceptance criteria using BDD/Gherkin in the iGaming or online Lottery domain.
---

# User Story Crafting & BDD Acceptance Criteria

## Overview
This skill provides the structure, rules, and examples for drafting **INVEST-compliant** User Stories and **BDD (Behavior-Driven Development) / Gherkin** Acceptance Criteria. It is optimized for high-concurrency gaming systems, compliance gates, and ledger integrity.

---

## When to Use
*   Translating high-level product briefs or regulatory mandates into developer-ready engineering tickets.
*   Writing acceptance criteria for game mechanics, wallet integrations, bonus schemes, geofencing, or KYC pipelines.
*   Grooming backlog items with Product Owners and tech leads to ensure they meet the **Definition of Ready (DoR)**.
*   Refining vague business rules into structured, unambiguous Gherkin statements (`Given-When-Then`).

---

## Standard User Story Template

Every story must be structured using the following sections to prevent ambiguity and ensure testing readiness.

### 1. Header & Statement
*   **Jira Title Pattern:** `[Module/Feature] Concise Action Description` (e.g., `[Wallet] Single-Wallet Wager Deduction`)
*   **Core Statement:**
    ```text
    As a [Player / Backoffice User / Compliance Officer]
    I want to [clear action/capability]
    So that [quantifiable business value or regulatory compliance goal]
    ```

### 2. Context & Technical Scope
*   **Background:** Brief context on why this is being built.
*   **API/Database Dependencies:** Specific endpoints or databases impacted (e.g., `POST /v1/wallet/debit`, updates `player_balances`).
*   **Security & Compliance Constraints:** Relevant license rules (MGA, UKGC, state lottery laws).

### 3. Business Rules & Logic
Bullet points defining calculations, system states, and business parameters:
*   *Formulas:* Exact mathematical equations (e.g., `Wager Rollover = Bonus Received * 35`).
*   *Ledger Locks:* State updates during asynchronous API calls (e.g., locking player balance during spin evaluation).

### 4. BDD Acceptance Criteria (Gherkin Format)
Write criteria using clean, testable scenarios:
```gherkin
Scenario: [Descriptive Scenario Title]
  Given [initial state, player credentials, wallet balance, geofencing status]
  When [the player triggers an action or system event occurs]
  Then [expected UI updates, wallet ledger shifts, third-party syncs, audit logs]
```

### 5. Non-Functional Requirements (NFRs)
*   **Concurrency:** Maximum concurrent transactions expected.
*   **Latency:** Permitted response time (e.g., `< 150ms`).
*   **Data Integrity:** Requirement for transactional atomicity (all-or-nothing ledger balance updates).

---

## Real-World iGaming Examples

### Example 1: Platform Single-Wallet Wager Deduction

```text
Title: [Wallet] atomic debit deduction on Slot Spin trigger

As a Game Server Client
I want to atomically deduct a wager amount from a player's real balance
So that the player's funds are securely debited before a game outcome is evaluated.
```

#### Context & Dependencies
*   Impacts: `POST /v1/wallet/debit`
*   Database: `player_wallets` (row locking required during update).
*   Dependencies: Triggered by Game Server prior to calling the certified RNG.

#### Business Rules
1.  **Atomicity:** If the debit deduction fails, the slot spin must not proceed.
2.  **Concurrency Lock:** The player's ledger entry must be locked for the duration of the transaction to prevent race conditions (double spending via multiple simultaneous spins).
3.  **Balance Check:** Debit must fail if `Available Balance` < `Wager Amount`.

#### Acceptance Criteria
```gherkin
Scenario: Successful wager deduction with sufficient balance
  Given a player "Player_A" has a real balance of USD 50.00
  And "Player_A" triggers a spin with a total wager of USD 2.50
  When the Game Server requests a wallet debit of USD 2.50 with transaction ID "tx_100239"
  Then the system must lock "Player_A"'s wallet row
  And deduct USD 2.50 from the balance
  And write an audit log entry in the ledger table with "tx_100239", debit, status = SUCCESS
  And return HTTP 200 with the new balance USD 47.50
  And release the wallet row lock.

Scenario: Failed wager deduction due to insufficient balance
  Given a player "Player_B" has a real balance of USD 1.00
  And "Player_B" triggers a spin with a total wager of USD 2.50
  When the Game Server requests a wallet debit of USD 2.50 with transaction ID "tx_100240"
  Then the system must reject the transaction
  And make no changes to "Player_B"'s wallet balance
  And write an audit log entry in the ledger table with "tx_100240", status = FAILED_INSUFFICIENT_FUNDS
  And return HTTP 422 with error code "INSUFFICIENT_FUNDS".
```

---

### Example 2: Responsible Gaming - Daily Deposit Limit Gating

```text
Title: [RG] Gating deposits against player-defined Daily Deposit Limits

As a Compliance Officer
I want the system to block deposits that exceed a player's daily limit
So that we adhere to MGA/SGA license conditions and promote player safety.
```

#### Business Rules
1.  **Daily Window:** A rolling 24-hour window from the time of transaction.
2.  **Gating Threshold:** Checks `sum(successful_deposits_last_24h) + proposed_deposit > daily_limit`.
3.  **Limit Adjustments:** Decreasing a limit takes effect immediately. Increasing a limit requires a 24-hour cooling-off period.

#### Acceptance Criteria
```gherkin
Scenario: Block deposit exceeding player's daily deposit limit
  Given a player "Player_C" who has set a Daily Deposit Limit of USD 100.00
  And "Player_C" has already successfully deposited USD 80.00 in the last 24 hours
  When "Player_C" attempts to deposit USD 30.00
  Then the Payment Gateway request must be blocked before calling the payment provider
  And the user must see an error message "Deposit exceeds your daily limit of USD 100.00. You can deposit up to USD 20.00."
  And a compliance audit log must record a rejected deposit attempt of USD 30.00 due to limit breach.
```

---

## Definition of Ready (DoR) Checklist
Before handing the story over to the engineering team:
*   [ ] User story statement is complete and clear.
*   [ ] BDD Acceptance Criteria cover positive, negative, and edge-case scenarios.
*   [ ] Technical integrations, endpoints, and database tables are documented.
*   [ ] Mathematical formulas and validation constraints are explicitly detailed.
*   [ ] Non-functional constraints (NFRs) are specified.
*   [ ] Out-of-scope items are listed to prevent scope creep.
