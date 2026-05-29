---
name: ba-requirements-elicitation
description: Use when preparing for, conducting, or synthesizing requirements elicitation sessions with stakeholders in the iGaming or online Lottery domain.
---

# Requirements Elicitation Framework

## Overview
This skill provides a **BABOK-aligned** framework for eliciting system and business requirements in the iGaming and Online Lottery domain. It outlines specialized techniques tailored to technical integration constraints, mathematical accuracy, and compliance-first architectures.

---

## When to Use
*   Kicking off new system capabilities (e.g., introducing a new payment provider, integrating a third-party game server, or redesigning player verification pipelines).
*   Conducting gap analysis against native regulatory licenses (e.g., UKGC, MGA, or state lottery audits).
*   Facilitating collaborative grooming sessions with conflicting stakeholders (e.g., Creative Game Producers seeking flashy features vs. Compliance Officers enforcing strict limits).
*   Planning workshops with technical teams to map ledger APIs, wallet states, or concurrent scaling limits.

---

## iGaming Stakeholder Elicitation Matrix

Successful elicitation relies on speaking the language of each specific stakeholder.

| Stakeholder | Core Concern | Elicitation Technique | Key Questions to Ask |
|:---|:---|:---|:---|
| **Compliance Officer** | License retention, audit trails, geo-gating, RG rules | **Regulation Gap Audit & Structured Interview** | * "What specific regulatory requirements apply to this jurisdiction?"<br>* "What audit logs or reporting structures are mandated?" |
| **Game Producer** | User retention, RTP, math sheets, animations, bonuses | **Visual Storyboarding & Workshops** | * "What is the expected Return to Player (RTP) and volatility?"<br>* "What are the trigger conditions for bonus features and loyalty?" |
| **Platform PM** | Core backend stability, ledger auditability, KYC/payment APIs | **Joint Application Design (JAD) Sessions** | * "Which wallet architecture (Single or Transfer) will be used?"<br>* "What third-party vendor APIs must be integrated?" |
| **Technical Lead** | System throughput, latencies, concurrency, security | **Interface & Schema Mapping Sessions** | * "What is the expected transactional throughput (TPS) at peak times?"<br>* "How are concurrent wallet updates locked in the database?" |

---

## Concrete Elicitation Templates

### Template 1: Regulatory Jurisdiction Onboarding Interview
*Use when analyzing requirements to launch a lottery draw or game suite in a new country or state.*

```markdown
### 1. Licensing & Regulatory Scope
*   **Target Jurisdiction:** [e.g., MGA, UKGC, state lottery board]
*   **Applicable Regulations:** [Reference specific clauses or guidelines]

### 2. Player Gating & Verification Rules
*   **Geofencing:** Are there specific state borders or GPS accuracy thresholds required?
*   **KYC Gates:** Is KYC mandatory *before* any deposit, or only prior to the first withdrawal?
*   **Underage Controls:** What self-declaration checks must be in place at registration?

### 3. Responsible Gaming Constraints
*   **Limit Options:** Must the system offer Daily/Weekly/Monthly deposit, wager, and loss limits?
*   **Limit Changes:** What are the cooling-off periods for limit increases (e.g., mandatory 24 hours)?
*   **Reality Check:** Does the player require a recurring session popup (e.g., every 60 minutes) showing total time and net losses?

### 4. Technical Audit & Reporting Requirements
*   **Outcome Certification:** Does the RNG require local testing agency certification?
*   **Database Retention:** How long must transaction history and spin ledgers be preserved?
*   **Regulator Access:** Does the local regulator require a secure data portal or direct API reporting?
```

---

### Template 2: Technical Wallet & API Integration Guide
*Use when facilitating JAD workshops with Platform PMs and Tech Leads to onboard a new payment vendor.*

```markdown
### 1. Transaction Flow & Ledgers
*   **Wallet Mode:** Single Wallet (direct API debit/credit) or Transfer Wallet (sub-ledger)?
*   **Ledger Account Mapping:** What general ledger (GL) accounts will record deposits, payouts, bonuses, and processing fees?

### 2. API Specifications & Error Handling
*   **Deduction Validation:** If the deduction times out, is the wager automatically rolled back (voided) or retried?
*   **Idempotency:** What unique key handles duplicate transaction triggers?
*   **Security:** How are payload signatures signed and verified (e.g., HMAC-SHA256, RSA)?

### 3. Performance & Capacity (NFRs)
*   **SLA Latency:** What is the maximum acceptable latency for wager deduction checks (e.g., < 200ms)?
*   **Concurrency:** What peak Transactions Per Second (TPS) must the wallet ledger support?
```

---

## Elicitation Best Practices & Pitfalls

### ❌ Anti-Pattern: Treating Compliance as an "Afterthought"
*   *Symptom:* Writing game engine stories and only asking the Compliance Officer for review during the Sprint Review.
*   *Consequence:* Blocked releases, failed audits, and expensive database refactoring.
*   *BA Action:* Always start with a **Regulation Gap Audit** first. Compliance rules are hard, non-negotiable boundaries. Design creative UI/UX around them.

### ❌ Anti-Pattern: Unbound Elicitation (Scope Creep)
*   *Symptom:* Letting Game Producers brainstorm endless bonus schemes without developer input.
*   *Consequence:* Complex code that delays target sprint goals.
*   *BA Action:* Enforce collaborative workshops where developers provide high-level sizing (T-shirt sizes) as requirements are defined.
