# Game Rules & Math Model Specification Sheet

This document defines the gameplay mechanics, prize structure tiers, return-to-player (RTP) statistics, and mathematical blueprints for lottery games. It is a critical deliverable for Game Producers, Math Analysts, and Compliance Officers.

---

## 1. Game Meta Information
*   **Game Name:** [e.g., Lucky Spin Lottery, Neon Scratchcard]
*   **Game ID:** [e.g., lot_luckyspin_v1]
*   **Target Jurisdictions:** [e.g., MGA, SGA, Pennsylvania State Lottery]
*   **Certified RTP:** [e.g., 96.50%]
*   **Volatility Class:** [Low / Medium / High]
*   **GLI Certification ID:** [Leave blank until certified by independent lab]

---

## 2. Core Game Rules & Mechanics

### 2.1 Gameplay Sequence
*   *Step 1 (Bet Selection):* Describe player choices (e.g., selecting numbers, selecting stake amount, quick-pick option).
*   *Step 2 (Wager deduction):* Wallet API deducts wager (must refer to ledger atomicity rules).
*   *Step 3 (Draw evaluation):* Triggering certified RNG, matching reels/strips or numbers drawn.
*   *Step 4 (Win credit & animations):* Awarding wins, credit balances, and presenting payouts.

### 2.2 Game Settings Parameters
*   **Minimum Bet:** [Amount + Currency]
*   **Maximum Bet:** [Amount + Currency]
*   **Base Jackpot Tier:** [Yes/No, starting pool amount if progressive]

---

## 3. Prize Structure & Probability Matrix

This table summarizes the math engine outcomes, odds of hit frequencies, and the contribution of each tier to the total RTP.

| Prize Tier | Winning Match Condition | Probability | Theoretical Odds (1 in X) | Payout Multiplier | Fixed Payout Value | RTP Contribution (%) |
|:---:|:---|:---:|:---:|:---:|:---:|:---:|
| **1 (Jackpot)** | Match 6 of 6 numbers | 0.00000007 | 13,983,816 | 100,000x | USD 250,000.00 | 0.70% |
| **2** | Match 5 of 6 numbers | 0.00001844 | 54,201 | 5,000x | USD 12,500.00 | 9.22% |
| **3** | Match 4 of 6 numbers | 0.00096861 | 1,032 | 100x | USD 250.00 | 9.69% |
| **4** | Match 3 of 6 numbers | 0.01765040 | 57 | 10x | USD 25.00 | 17.65% |
| **5 (Min Win)** | Match 2 of 6 numbers | 0.15147020 | 6.6 | 2x | USD 5.00 | 30.29% |
| **6 (Free Spin)** | Match 1 of 6 numbers | 0.28000000 | 3.5 | Free Play | USD 2.50 (Valued) | 29.00% |
| **Total** | **Any Payout Match** | **0.45010772** | **2.22 (Hit Freq)** | **N/A** | **N/A** | **96.55% (Total RTP)** |

---

## 4. Mathematical Model & Volatility Blueprint

*   **Hit Frequency:** [Total winning combinations / Total possible outcomes. Expressed as percentage, e.g., 45.01%].
*   **RTP Split:**
    *   *Real Cash RTP:* [e.g., 90.50%]
    *   *Bonus/Promo RTP (Free plays, jackpots):* [e.g., 6.05%]
*   **Standard Deviation ($\sigma$):** [Mathematical value indicating risk/spread of winnings].
*   **Volatility Rating:** [Detailed math scale description, e.g., High volatility slot game with a standard deviation of 12.4, suited for longer play sessions].

---

## 5. Certified RNG & Integration Security
*   **RNG Engine Model:** [e.g., Mersenne Twister, hardware cryptographical source]
*   **Seed Refresh Cadence:** [e.g., fresh seed requested every 10,000 draws, or time-locked cryptographical rotation]
*   **Security Protocol:**
    *   Outcome generation must be fully decoupled from the wallet ledger (RNG does not know the player's balance).
    *   Audit logs must capture: `seeding_timestamp`, `raw_hex_output`, `resultant_draw_tiers`, and `server_signature` using SHA-256 signatures.

---

## 6. Compliance Sign-off & Audit Log
*   **Compliance Lead:** [Name / Date / Approved Status]
*   **Principal Math Analyst:** [Name / Date / Approved Status]
*   **External Lab Reference:** [Certificate ID / Expiry Date]
