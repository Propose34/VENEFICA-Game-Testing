# Test Suite 02: World Interaction & Targeting System

## Module Overview
Verifies that interactable entities (NPCs, foraging nodes, workstations, signs) accurately detect player proximity, display readable action prompts (`E`), and properly filter out targets that are obstructed by solid barriers.

---

## Test Cases

### TC-M02-01: Proximity Trigger & Action Prompt Display
- **Objective:** Verify interaction HUD prompt appears when entering valid trigger radius and disappears when leaving.
- **Preconditions:** Player spawned near an interactable object (e.g. Lina or Garden Node).
- **Steps:**
  1. Walk toward Lina at the customer counter.
  2. Observe the screen HUD when reaching ~2 meters distance.
  3. Step backward away from the counter.
- **Expected Result:**
  - Prompt text reads: `[E] Talk` (or specific interaction verb).
  - Prompt vanishes immediately upon stepping outside interaction threshold.
- **Status:** **PASS**

---

### TC-M02-02: Raycast Occlusion Check (No Interaction Through Walls)
- **Objective:** Ensure the player cannot interact with objects on the other side of a solid wall.
- **Preconditions:** Stand outside the shop behind the customer counter wall where Lina stands inside.
- **Steps:**
  1. Walk to the exterior wall directly opposite Lina.
  2. Aim towards Lina's coordinate through the solid wall.
  3. Observe if prompt appears and press `E`.
- **Expected Result:** No prompt appears, and pressing `E` does not initiate conversation. Direct line-of-sight is required.
- **Status:** **PASS**

---

### TC-M02-03: Multiple Overlapping Target Prioritization
- **Objective:** Ensure predictable behavior when standing between closely packed interactables.
- **Preconditions:** Stand near the garden edge between a Moonleaf patch and a garden plot boundary.
- **Steps:**
  1. Position avatar centered between two adjacent interactable objects.
  2. Rotate camera to face each object in turn.
- **Expected Result:** Prompt highlights the object most directly aligned with the player's center view; no flickering or duplicate UI overlap.
- **Status:** **PASS**
