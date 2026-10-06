# Test Suite 07: Workstation & Environment Inspection

## Module Overview
Validates inspection of environmental objects in the prototype, focusing on the Alchemy Workbench and Garden Plots. Confirms camera focus changes during inspection and camera reset upon exiting.

---

## Test Cases

### TC-M07-01: Alchemy Table Focus & Close-Up View
- **Objective:** Verify interacting with the Alchemy Table transitions the camera to a close-up workstation perspective.
- **Preconditions:** Player stands in front of the Alchemy Table inside the shop.
- **Steps:**
  1. Approach the alchemy table until the prompt `[E] Inspect Workstation` appears.
  2. Press `E`.
  3. Observe camera movement.
- **Expected Result:** Camera smoothly moves to the predefined close-up angle over the alchemy surface; an informative note appears stating brewing mechanics will be unlocked in upcoming milestones.
- **Status:** **PASS**

---

### TC-M07-02: Workstation Inspection Exit & Camera Restoration
- **Objective:** Verify pressing `Esc` releases workstation focus and restores third-person player camera.
- **Preconditions:** Workstation close-up inspection active from TC-M07-01.
- **Steps:**
  1. Press `Esc` while in workstation view.
  2. Move mouse to rotate camera.
  3. Press `W` to walk away.
- **Expected Result:** Camera snaps/transitions cleanly back to the standard third-person orbit behind the avatar; gameplay locomotion resumes immediately.
- **Status:** **PASS**

---

### TC-M07-03: Garden Bed Inspection
- **Objective:** Confirm garden bed plots display status prompts and explain future farming systems clearly.
- **Preconditions:** Player walks out to the garden beds behind the shop.
- **Steps:**
  1. Approach garden plot #1.
  2. Press `E` to inspect.
- **Expected Result:** Inspection dialog displays soil status ("Fertile soil bed ready for seeding in upcoming seasons"); dismisses cleanly without locking controls.
- **Status:** **PASS**
