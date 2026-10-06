# Test Suite 06: Inventory Bag & Modal HUD System

## Module Overview
Verifies inventory toggle functionality via `Tab`, locomotion input locking while menus are open, font scaling, auto-sizing within UI containers, and UI text readability.

---

## Test Cases

### TC-M06-01: Inventory Toggle (Tab Key)
- **Objective:** Verify pressing `Tab` opens the inventory screen and pressing `Tab` or `Esc` closes it.
- **Preconditions:** Player in normal gameplay locomotion state.
- **Steps:**
  1. Press `Tab` -> verify Bag screen appears over gameplay view.
  2. Press `Tab` again -> verify Bag screen closes.
  3. Press `Tab` to open, then press `Esc` -> verify Bag screen closes.
- **Expected Result:** Bag screen toggles reliably without double-opening or input deadlocks.
- **Status:** **PASS**

---

### TC-M06-02: Movement Input Lock During Open UI
- **Objective:** Verify avatar cannot walk, run, or drift while inspecting inventory or dialogue menus.
- **Preconditions:** Player standing in open courtyard.
- **Steps:**
  1. Press `Tab` to open the bag.
  2. Press and hold `W`, `A`, `S`, `D`.
  3. Try moving the mouse to rotate the camera.
- **Expected Result:** Character remains completely stationary; camera remains fixed; no inputs leak to the physics controller.
- **Status:** **PASS**

---

### TC-M06-03: Font Scaling & Text Auto-Sizing (No Truncation)
- **Objective:** Verify dialogue body text and inventory item descriptions do not clip outside container bounds.
- **Preconditions:** Player interacts with dialogues of varying lengths.
- **Steps:**
  1. Trigger longer multi-line dialogue branches (e.g. Rowan's forest gossip or quest explanations).
  2. Inspect text margins at 1920x1080 and 1280x720 resolutions.
- **Expected Result:** Text auto-scales dynamically between 18pt and 23pt to maintain full readability without overflowing border panels or getting clipped.
- **Status:** **PASS** (Resolved in M1 fix)
