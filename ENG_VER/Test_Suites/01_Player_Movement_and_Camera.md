# Test Suite 01: Player Movement & Camera System

## Module Overview
Validates that the avatar responds predictably to player inputs (WASD + Shift), that character collision prevents walking through solid structures, and that the third-person camera prevents clipping into interior walls and props.

![Player Perspective](../../Media/Prototype_PlayerView.png)

---

## Test Cases

### TC-M01-01: Directional Movement (WASD Relative to Camera)
- **Objective:** Verify player moves forward, backward, left, and right relative to the camera's forward orientation.
- **Preconditions:** Game in Play Mode; player spawned on shop floor.
- **Steps:**
  1. Press `W` -> verify player advances forward along camera direction.
  2. Press `S` -> verify player retreats toward camera direction.
  3. Press `A` and `D` -> verify smooth strafe / turning movement.
  4. Rotate camera 90 degrees with mouse, then press `W`.
- **Expected Result:** Avatar moves in the direction the camera is currently facing without snapping or stuttering.
- **Status:** **PASS**

---

### TC-M01-02: Sprint Mechanics (Left Shift)
- **Objective:** Confirm sprint key increases traversal velocity.
- **Preconditions:** Player in open space (e.g. garden or pathway).
- **Steps:**
  1. Hold `W` to walk across the stone pathway. Note time taken.
  2. Hold `W` + `Left Shift` across the same path.
- **Expected Result:** Walking speed is noticeably increased while holding `Shift`; releasing `Shift` immediately returns movement to standard walking speed.
- **Status:** **PASS**

---

### TC-M01-03: Camera Collision & Wall Occlusion (No Wall Clipping)
- **Objective:** Ensure the camera does not pass through shop walls, shelves, or archways into void space.
- **Preconditions:** Player stands inside the shop with back close to a perimeter wall.
- **Steps:**
  1. Walk the character backward against the shop interior wall.
  2. Rotate the mouse up and down to push camera against the ceiling and wall colliders.
  3. Observe camera distance and rendering.
- **Expected Result:** Camera smoothly pulls closer to the avatar (SphereCast collision detection) instead of clipping through the wall geometry. Interior backfaces and skybox voids remain hidden.
- **Status:** **PASS** (Resolved in M1 fix)

---

### TC-M01-04: Obstacle Traversal & Pathway Routes
- **Objective:** Verify unobstructed movement along the three main routes connecting hubs.
- **Preconditions:** Player stands at starting shop point.
- **Steps:**
  1. Walk Route A: Shop Interior -> Back Door -> Garden Beds.
  2. Walk Route B: Shop Interior -> Side Door -> Market Stall.
  3. Walk Route C: Garden -> Stone Trail -> Forest Archway.
- **Expected Result:** No invisible walls, seam snags, or step-height blockages occur along any of the three standard paths.
- **Status:** **PASS**
