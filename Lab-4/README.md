# Defender Repair Lab (Lab 4: Vibe Coding)

**Student Name:** Dilipan Y  
**SRN:** PES1UG24AM092  
**Original Lab Repository:** [SETAPESU26/28_defender](https://github.com/SETAPESU26/28_defender)  
**Submission Repository:** [Dilipan-Y-8488/SE-Lab](https://github.com/Dilipan-Y-8488/SE-Lab)

---

## Deliverables Summary

| Deliverable | Location / File | Status |
| :--- | :--- | :--- |
| **Before Video** | `Lab-4/Before.mp4` | Uploaded & committed |
| **After Video** | `Lab-4/After.mp4` | Recorded after fixes & features |
| **Updated Code** | `Lab-4/game.py` | Complete with per-task commits |
| **Chat History** | `Lab-4/chat_history.pdf` | Exported and formatted |

---

## Completed Tasks

### Task 1: Fix the Radar Bug
- **Issue:** The radar plotted blips using screen-space coordinates relative to the player (`screen_x(x) % VIEW_W`), causing all entities to cluster artificially around the center.
- **Fix:** Mapped absolute world coordinates directly to the radar width: `rx = int((x % WORLD_W) / WORLD_W * VIEW_W)`. Added a camera viewport indicator box showing the currently visible section of the world.
- **Commit:** `62661d7` - `Lab 4: Task 1 - Fix radar blip positioning to world-space coordinates and add scanner viewport indicator`

### Task 2: Implement `sky_color(wave)`
- **Issue:** The sky color function was an empty stub (`pass`), causing the game to retain the static default background.
- **Fix:** Implemented dynamic atmospheric cycling colors (deep midnight navy, alien violet, twilight magenta, crimson nebula, toxic emerald, arctic dusk) that shift with each advancing wave while preserving high entity contrast.
- **Commit:** `9071c51` - `Lab 4: Task 2 - Implement sky_color(wave) with dynamic atmospheric color shifting per wave`

### Task 3: Implement `on_humanoid_rescued(humanoid)`
- **Issue:** Rescuing a falling humanoid mid-air previously gave score without visual celebration or safety mechanics.
- **Fix:** Added floating animated `+500 RESCUED!` celebration popups at the rescue coordinate and awarded a 2.5-second energy shield / invulnerability ring protecting the player from surrounding hazards upon landing a rescue.
- **Commit:** `b532705` - `Lab 4: Task 3 - Implement on_humanoid_rescued with floating celebration popup and shield boost`

### Task 4: Implement `bonus_life_threshold()`
- **Issue:** The bonus life threshold was unimplemented (`pass`), preventing players from earning extra lives during gameplay.
- **Fix:** Implemented `bonus_life_threshold()` returning `10000`, automatically awarding an extra life each time the player's score crosses a multiple of 10,000 points.
- **Commit:** `cc88409` - `Lab 4: Task 4 - Implement bonus_life_threshold to grant extra life every 10,000 points`

---

## How to Run the Game

1. Double-click `run_game.bat`, or run from terminal:
   ```bash
   uv run --python 3.12 --with pygame python game.py
   ```

2. **Controls:**
   - **Arrow Keys:** Left/Right to thrust, Up/Down to ascend/descend
   - **Spacebar:** Fire lasers
   - **R:** Reset / Restart game
