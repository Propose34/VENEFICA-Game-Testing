# Test Suite 03: NPC Dialogue & Branching System

## Module Overview
Validates dialogue interaction with NPCs: Lina (Shopkeeper at the counter) and Rowan (Merchant at the market stall). Verifies choice selection via mouse and keyboard numbers (1–4), input locking, and clean exit via `Esc`.

---

## Test Cases

### TC-M03-01: Lina Dialogue Initiation & Topic Selection
- **Objective:** Verify player can initiate conversation with Lina and explore available dialogue choices.
- **Preconditions:** Player is at the shop counter facing Lina.
- **Steps:**
  1. Press `E` to talk.
  2. Verify dialogue box opens displaying Lina's greeting and choices:
     - Choice 1: Ask for directions.
     - Choice 2: Ask about the shop.
     - Choice 3: Give 3 Moonleaf (if available).
     - Choice 4: Goodbye / Exit.
  3. Select Choice 1 using mouse click or pressing `1`.
- **Expected Result:** Dialogue updates with the requested information; player locomotion is locked while reading.
- **Status:** **PASS**

---

### TC-M03-02: Rowan Market Conversation & Directional Guidance
- **Objective:** Verify conversation flow with Rowan at the marketplace.
- **Preconditions:** Player walked through side door to the market stall.
- **Steps:**
  1. Approach Rowan and press `E`.
  2. Select options inquiring about the village and nearby forest.
  3. Verify merchant informs player that trade shipments are pending (explaining M1 scope limit cleanly to players).
- **Expected Result:** Dialogue runs smoothly without UI glitches; text wraps properly inside the dialogue box.
- **Status:** **PASS**

---

### TC-M03-03: Dismissal & Input Restoration (Esc Key Handling)
- **Objective:** Confirm pressing `Esc` closes any active dialogue window and restores normal player locomotion.
- **Preconditions:** Active dialogue open with either Lina or Rowan.
- **Steps:**
  1. Open dialogue window with `E`.
  2. Press `Esc` immediately.
  3. Attempt WASD locomotion and camera rotation.
- **Expected Result:** Dialogue modal closes cleanly; cursor locks back to gameplay mode; WASD controls immediately responsive.
- **Status:** **PASS**
