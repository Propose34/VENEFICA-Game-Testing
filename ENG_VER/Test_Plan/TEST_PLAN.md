# Master Test Plan — VENEFICA (Milestone M1 Prototype)

## 1. Document Control & Overview
- **Project Name:** VENEFICA
- **Build / Milestone:** M1 First Playable Prototype (Cozy Gothic Witchcraft Adventure)
- **Engine / Platform:** Unity (URP) / PC Windows (Keyboard & Mouse)
- **Document Version:** 1.0.0
- **Document Owner:** QA Lead / Quality Assurance Team
- **Test Strategy:** Manual Functional Testing, Smoke Testing, Level Obstacle Clearance, UI Readability & Boundary Verification

---

## 2. Test Objectives
The primary objective of Milestone M1 QA is to validate that the fundamental player loop functions reliably and smoothly before moving into production of deeper mechanics (such as advanced crafting and full merchant economies).

Key QA Goals:
1. Ensure the player avatar can navigate the prototype level without getting stuck, falling out of bounds, or suffering camera disorientation.
2. Verify all world interaction targets (NPCs, gatherable nodes, workstations) trigger responsive, readable prompts.
3. Confirm that UI windows (Inventory, Dialogue, Inspect panels) pause character locomotion and cleanly hand back control when dismissed.
4. Verify data integrity in the session state (inventory count, gold balance, quest progression, single-collection enforcement).

---

## 3. Scope of Testing

### 3.1 In-Scope Features
| Feature / Subsystem | Scope Description |
|---|---|
| **Avatar Locomotion** | WASD walk relative to camera view, Shift sprint, gravity, and obstacle step-over. |
| **Camera System** | Third-person orbit, wall collision protection (no clipping into shop walls), and smooth transition during inspection. |
| **NPC Dialogue** | Interactive conversations with Lina (Shopkeeper) and Rowan (Market Merchant), multi-choice dialog branches. |
| **Foraging & Harvesting** | Moonleaf nodes in Garden and Grove; choice between "Leave it growing" and "Collect"; anti-duplication checks. |
| **Quest & Reward** | Lina's starter request (turn in 3 Moonleaf for 10 Gold coins); balance updates; repeat-reward prevention. |
| **Inventory & Pause UI** | Tab bag toggle, item icon & name rendering, font readability, input locking during open modals. |
| **Workstation Inspection** | Alchemy table inspection camera focus, prompt dismissal with `Esc`, seamless camera return. |

### 3.2 Out-of-Scope (Future Milestones)
- Full farming / soil hydration loops (plots are currently inspectable blockouts).
- Complex multi-ingredient brewing recipes (alchemy bench is view-only).
- Save / Load persistence across game restarts (session resets on exit by design in M1).
- Full market trading system (Rowan is conversation/directions only in M1).

---

## 4. Test Environment & Requirements
- **Platform:** Windows 10 / 11 (64-bit)
- **Input Devices:** Keyboard and Mouse
- **Resolution Target:** 1920x1080 (16:9 aspect ratio) with support down to 1280x720 windowed
- **Target Frame Rate:** 60 FPS stable locomotion
- **Rendering Pipeline:** Universal Render Pipeline (URP)

---

## 5. Visual Map Reference
The prototype environment consists of 4 interconnected hubs:
1. **The Witch Shop & Customer Counter** (Starting interior)
2. **The Garden Beds & Moonleaf Patch** (Rear exterior exit)
3. **The Marketplace & Rowan's Stall** (Side pathway exit)
4. **The Old Arch & Forest Grove** (Connecting stone trail)

![Level Overview](../../Media/Prototype_Overview.png)

---

## 6. Entry & Exit Criteria

### 6.1 Entry Criteria
- Prototype scene loads cleanly without missing script warnings or broken shader artifacts (no magenta shaders).
- Player spawns upright on the shop floor with camera properly positioned behind the avatar.

### 6.2 Exit Criteria (Pass Definition)
- **100% Pass** on critical gameplay smoke tests (Movement, Dialogue, Harvesting, Reward exchange).
- **Zero Blocker / Critical Bugs** (no game crashes, soft-locks during modal dialogue, or out-of-bounds falls).
- All identified defects are documented with clear reproduction steps, expected vs. actual behavior, and severity ratings.

---

## 7. Test Suite Index
All detailed functional test cases are organized into modular test suites:
- `Test_Suites/01_Player_Movement_and_Camera.md`
- `Test_Suites/02_Interaction_and_Targeting.md`
- `Test_Suites/03_NPC_Dialogue_System.md`
- `Test_Suites/04_Foraging_and_World_Nodes.md`
- `Test_Suites/05_Quest_and_Economy.md`
- `Test_Suites/06_Inventory_and_Modal_HUD.md`
- `Test_Suites/07_Workstation_Inspection.md`
