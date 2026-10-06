# Test Suite 05: Quest Hand-In & Currency Economy

## Module Overview
Validates Lina's early prototype quest (turn in 3 Moonleaf for 10 Gold coins), item deduction accuracy, gold balance addition (from 40 to 50 coins), and strict anti-exploit enforcement to prevent duplicate rewards.

---

## Test Cases

### TC-M05-01: Insufficient Items Hand-In Prevention
- **Objective:** Verify player cannot complete the delivery option if holding fewer than 3 Moonleaf.
- **Preconditions:** Player has 2 Moonleaf in inventory; starting gold balance is 40.
- **Steps:**
  1. Talk to Lina at the counter.
  2. Inspect the option: **Give 3 Moonleaf**.
- **Expected Result:** Option is either greyed out, disabled, or Lina politely declines stating you do not have enough items. Gold remains at 40; Moonleaf count remains at 2.
- **Status:** **PASS**

---

### TC-M05-02: Successful Delivery & Accurate Currency Update
- **Objective:** Verify hand-in deducts 3 Moonleaf, leaves remaining items intact, and adds 10 coins.
- **Preconditions:** Player collected 4 Moonleaf (from Garden + Grove); Gold balance is 40.
- **Steps:**
  1. Talk to Lina at the counter.
  2. Select option: **Give 3 Moonleaf**.
  3. Close conversation and open bag (`Tab`).
- **Expected Result:**
  - Gold balance increases: `40 -> 50 coins` (+10 coins).
  - Moonleaf inventory count: `4 - 3 = 1 Moonleaf` remains in bag.
  - Lina expresses gratitude in dialogue.
- **Status:** **PASS**

---

### TC-M05-03: Repeat Delivery Prevention (Idempotency Check)
- **Objective:** Ensure the player cannot turn in the same quest multiple times to farm infinite gold.
- **Preconditions:** TC-M05-02 completed successfully.
- **Steps:**
  1. Immediately talk to Lina again.
  2. Observe available dialogue options.
- **Expected Result:** "Give 3 Moonleaf" option is removed or marked as already fulfilled; repeated interaction yields standard conversation only without additional gold rewards.
- **Status:** **PASS**
