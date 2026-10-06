# Defect & Bug Tracking Log — VENEFICA

## 1. Defect Summary Metrics
| Severity | Total Found | Resolved | Open / By-Design |
|---|---|---|---|
| **Critical / Blocker (P1)** | 1 | 1 | 0 |
| **High (P2)** | 2 | 2 | 0 |
| **Medium (P3)** | 1 | 1 | 0 |
| **Low / Limitation (P4)** | 2 | 0 | 2 |
| **Total** | **6** | **4** | **2** |

---

## 2. Resolved Defects

### DEF-01: Camera Spawns Obstructed by Shop Sign & Wall Geometry
- **Severity:** High (P2)
- **Component:** Camera System (`PrototypeCamera.cs`)
- **Status:** **RESOLVED**
- **Description:** Upon initial game launch, the third-person camera spawned inside or behind the shop front wooden sign, resulting in severe visual obstruction where the character was completely hidden behind wall geometry.
- **Steps to Reproduce:**
  1. Load `Venefica_Prototype.unity`.
  2. Enter Play Mode.
  3. Look at starting viewport immediately without moving the mouse.
- **Expected Result:** Camera starts at a clear, unobstructed angle behind the player avatar.
- **Actual Result (Before Fix):** Camera clipped inside the exterior wall and sign geometry.
- **Resolution:** Implemented `SnapToPlayer()` with `Physics.SphereCast` collision detection at spawn, automatically pulling the camera inward to a collision-safe vantage point before the first frame renders.

---

### DEF-02: Missing Prefab Overrides Resulting in Player Script Disconnection
- **Severity:** Critical (P1)
- **Component:** Core Session / Player Prefab (`BlockWitch.prefab`)
- **Status:** **RESOLVED**
- **Description:** Player GameObject references to the scene session controller and camera view were not serialized as persistent prefab overrides in the scene file, causing player control scripts to lose reference upon fresh load.
- **Steps to Reproduce:**
  1. Re-open project or instantiate player prefab.
  2. Enter Play Mode and attempt WASD movement.
- **Expected Result:** Player immediately moves and camera tracks correctly.
- **Actual Result (Before Fix):** Missing reference exceptions prevented movement.
- **Resolution:** Explicitly serialized player-session references using Unity Prefab Modification APIs to guarantee persistence.

---

### DEF-03: Modal Choice Text Clipping Beyond UI Container Bounds
- **Severity:** Medium (P3)
- **Component:** User Interface (`PrototypeHud.cs` / TextMeshPro)
- **Status:** **RESOLVED**
- **Description:** When interacting with NPCs featuring detailed multi-sentence dialogue (such as Rowan's town directions), the text font size exceeded the UI panel height, cutting off bottom paragraphs.
- **Steps to Reproduce:**
  1. Talk to Rowan at the market.
  2. Select longer dialogue inquiries.
  3. Observe text boundary at 1280x720 window resolution.
- **Expected Result:** Text remains fully readable within the panel with appropriate margins.
- **Actual Result (Before Fix):** Text overflowed past the bottom border of the frame.
- **Resolution:** Configured auto-sizing on the dialogue body TextMeshPro component (`fontSizeMin = 18`, `fontSizeMax = 23`), ensuring dynamic scaling to accommodate diverse content lengths.

---

### DEF-04: Accidental Raycast Interaction Through Solid Interior Walls
- **Severity:** High (P2)
- **Component:** Interaction Raycast System
- **Status:** **RESOLVED**
- **Description:** When standing behind the exterior wall of the customer counter, the player could press `E` through the wall to talk to Lina.
- **Steps to Reproduce:**
  1. Walk to the shop exterior back wall.
  2. Aim directly at Lina's coordinates inside.
  3. Press `E`.
- **Expected Result:** Interaction rejected due to line-of-sight blockage.
- **Actual Result (Before Fix):** Dialogue prompt appeared through solid plaster wall.
- **Resolution:** Added line-of-sight raycast occlusion checks ignoring trigger volumes, ensuring interaction prompts only show when direct line-of-sight is clear.

---

## 3. Known Limitations & By-Design Behaviors (Milestone M1)

### LIM-01: Session State Resets on Play Mode Exit (No Save / Load)
- **Severity:** Low / By-Design (P4)
- **Component:** Session Persistence
- **Status:** **OPEN (Scheduled for Milestone M4)**
- **Description:** Coins, inventory items, and harvested node states reset back to default upon exiting Play Mode.
- **Impact:** Expected prototype behavior for M1 validation; no player impact during single play sessions.

---

### LIM-02: Advanced Workstation Crafting & Market Barter Placeholder
- **Severity:** Low / By-Design (P4)
- **Component:** Economy & Alchemy
- **Status:** **OPEN (Scheduled for Milestone M2 - M3)**
- **Description:** Rowan provides lore dialogue and market directions, but does not yet buy/sell merchandise. The Alchemy table provides an inspection camera view, but does not process ingredients.
- **Impact:** System UI transparently notifies the player that these stations are preview blockouts.
