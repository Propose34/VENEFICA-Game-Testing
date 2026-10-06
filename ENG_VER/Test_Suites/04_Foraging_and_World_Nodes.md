# Test Suite 04: Foraging & World Gathering Nodes

## Module Overview
Validates world resource gathering (Moonleaf nodes located in the garden and forest grove). Ensures choice logic between "Leave it growing" and "Collect", enforces single-harvest rules, and verifies inventory addition without duplicate exploits.

---

## Test Cases

### TC-M04-01: "Leave It Growing" Decision Check
- **Objective:** Verify choosing not to gather preserves the plant in the world and does not modify player inventory.
- **Preconditions:** Player has 0 Moonleaf in bag. Stands in front of unharvested Moonleaf node in the garden.
- **Steps:**
  1. Press `E` on the Moonleaf plant.
  2. Dialog prompt appears: Choose **[1] Leave it growing**.
  3. Open bag with `Tab` and verify inventory contents.
- **Expected Result:**
  - Bag remains empty (0 Moonleaf).
  - Plant remains physically present in the garden.
  - Interacting again allows player to choose again.
- **Status:** **PASS**

---

### TC-M04-02: Successful Harvest & Inventory Increment
- **Objective:** Verify collecting yields 2 Moonleaf and updates inventory count.
- **Preconditions:** Fresh Moonleaf node; bag contains 0 Moonleaf.
- **Steps:**
  1. Press `E` on the Moonleaf plant.
  2. Choose **[2] Collect**.
  3. Open bag (`Tab`).
- **Expected Result:**
  - Inventory shows: `Moonleaf x2`.
  - Plant in the world changes visual state / disappears / becomes depleted.
- **Status:** **PASS**

---

### TC-M04-03: Single-Harvest Rule (Anti-Duplication Enforcement)
- **Objective:** Verify a harvested node cannot be re-harvested repeatedly.
- **Preconditions:** Node has just been collected in TC-M04-02.
- **Steps:**
  1. Approach the depleted plant location.
  2. Attempt to press `E`.
- **Expected Result:** Prompt is either disabled or displays "Already harvested"; player does not receive extra items.
- **Status:** **PASS**

---

### TC-M04-04: Multi-Node Accumulation
- **Objective:** Verify harvesting from multiple independent nodes accumulates items correctly.
- **Preconditions:** Garden node harvested (Bag has 2 Moonleaf).
- **Steps:**
  1. Follow the stone trail into the forest grove.
  2. Locate the second Moonleaf node.
  3. Press `E` -> Choose **Collect**.
  4. Open inventory with `Tab`.
- **Expected Result:** Bag accurately shows `Moonleaf x4` total.
- **Status:** **PASS**
