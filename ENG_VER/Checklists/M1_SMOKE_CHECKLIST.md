# Milestone M1 — Playtest Smoke Checklist

A rapid, repeatable 20-point verification checklist designed for QA testers to run through during every build or playtest session.

| # | Test Scenario / Action | Expected Result | Pass / Fail | Notes |
|---|---|---|:---:|---|
| **01** | Press Play and enter game | Player spawns safely on shop floor, camera clear | [x] PASS | Camera at safe angle |
| **02** | Press `W`, `A`, `S`, `D` | Player moves relative to camera orientation | [x] PASS | Smooth acceleration |
| **03** | Hold `Left Shift` while walking | Character sprints at noticeably increased speed | [x] PASS | Returns to walk on release |
| **04** | Walk against shop walls | Physics collision prevents walking through walls | [x] PASS | Solid boundary collision |
| **05** | Rotate mouse against walls/ceilings | Camera smoothly pulls closer, no void clipping | [x] PASS | SphereCast active |
| **06** | Walk out back door to Garden | Seamless transition without snags or invisible walls | [x] PASS | Route verified |
| **07** | Approach Moonleaf node in Garden | Interaction prompt `[E] Moonleaf` appears | [x] PASS | Clean trigger radius |
| **08** | Press `E` -> Select "Leave it growing" | Plant remains in garden, bag count remains 0 | [x] PASS | State preserved |
| **09** | Press `E` -> Select "Collect" | Receive Moonleaf x2, plant node becomes depleted | [x] PASS | Inventory updated |
| **10** | Attempt to re-harvest depleted node | Action rejected; node cannot give duplicate items | [x] PASS | Anti-exploit passed |
| **11** | Walk through stone arch to Grove | Route is clear of navigation blockers | [x] PASS | Route verified |
| **12** | Harvest Moonleaf node in Grove | Receive Moonleaf x2; total count in bag = 4 | [x] PASS | Count = 4 |
| **13** | Walk to customer counter & face Lina | Prompt `[E] Talk` appears across counter | [x] PASS | Prompt responsive |
| **14** | Try talking to Lina through exterior wall | Prompt does NOT appear; interaction blocked | [x] PASS | Occlusion check passed |
| **15** | Select "Give 3 Moonleaf" to Lina | Gold increases 40 -> 50; 1 Moonleaf remains | [x] PASS | Economy validated |
| **16** | Talk to Lina again immediately | Option cannot be repeated; no extra gold granted | [x] PASS | Single-reward enforced |
| **17** | Walk to Market & talk to Rowan | Dialogue opens, choices 1-4 work via keys/mouse | [x] PASS | Text auto-sizes cleanly |
| **18** | Press `Esc` during any dialogue | Dialogue closes cleanly; movement restored | [x] PASS | Locomotion unlocked |
| **19** | Press `E` on Alchemy Workbench | Camera zooms to table view; note displayed | [x] PASS | Workstation view active |
| **20** | Press `Tab` to open Bag and press `W` | Character does NOT move while bag UI is open | [x] PASS | Modal input locked |
