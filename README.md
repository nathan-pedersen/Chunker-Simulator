**OSRS Chunk Picker** is a procedural generation simulation tool designed for Old School RuneScape gameplay challenges (such as chunk-locked accounts). It overlays an interactive grid onto the high-resolution world map, allowing players to simulate the "discovery" of the world through RNG rolls.
**Key Features:**
* **Interactive Map:** High-performance viewport rendering engine with smooth pan and zoom (up to 300x).
* **Fog of War:** Start in pitch black and visually unlock chunks as you progress.
* **Fate Rolling:** Randomly selects adjacent "Rollable" chunks or Transport destinations to expand your territory.
* **Statistical Simulation:** Built-in Monte Carlo simulations (1,000+ runs) to calculate the average number of rolls required to reach specific targets or clear map sections.
* **State Management:** Track Targets, Transport links, and Unlocked areas with full Save/Load functionality.

`python` `osrs` `oldschool-runescape` `simulation` `chunk-locked` `pathfinding` `monte-carlo` `tkinter`

*User Guide*

---

# OSRS Chunk Picker (v40) – User Guide

### **1. Setup & Installation**

* **Requirements:** You need Python installed with the `Pillow` library (`pip install pillow`) and `tkinter` (usually included with Python).
* **Map File:** The program looks for a file named **`Old_School_RuneScape_world_map.png`** in the same folder as the script.
* *Note:* The system is calibrated for a map image size of roughly **9216x6528 pixels**.



---

### **2. Interface & Navigation**

The tool uses a **Viewport Rendering Engine**, allowing for smooth zooming and panning over the massive high-resolution world map.

* **Panning:**
* **Drag:** Click and hold **Left Mouse Button** anywhere on the map to drag the view.
* **Scrollbars:** Use the vertical and horizontal scrollbars.


* **Zooming:**
* **Mouse Wheel:** Scroll up/down to zoom in/out. The zoom focuses on your **mouse cursor**.
* **Slider:** Use the slider at the top left for manual control.
* *Note:* Coordinate labels (e.g., `24,18`) appear automatically when zoomed in past level 30.


* **Recenter:** Click the **"Recenter"** button to jump the camera to the center of your currently unlocked area.

---

### **3. Tile Legend (States)**

The grid overlays the map to show the status of each OSRS Chunk:

| Color | State Name | Description |
| --- | --- | --- |
| **Black (Dark Fog)** | **Locked** | The area is undiscovered. The map is visible but darkened. |
| **Transparent** | **Unlocked** | The area is discovered. The map shows through clearly. |
| **Cyan** | **Rollable** | A chunk adjacent to your unlocked area. Valid for rolling. |
| **Red** | **Target (Locked)** | A goal chunk you selected, currently out of reach. |
| **Purple** | **Target (Reachable)** | A goal chunk that is adjacent to unlocked territory. |
| **Bright Green** | **Transport** | A chunk reachable via teleport/transport (e.g., Spirit Tree, Fairy Ring) even if not adjacent. |

---

### **4. Controls & Interaction**

* **Left Click:**
* **Click (Short):** Toggles a tile between **Unlocked** and **Locked**.
* **Hold & Move:** Pans the camera (does not toggle tiles).


* **Right Click:**
* Manually force a Locked tile to become **Rollable (Cyan)**.
* Revert a Rollable tile to **Locked**.


* **Middle Click (Scroll Wheel Click):**
* **Cycle through Target States:**
1. **First Click:** Sets as **Target** (Red/Purple).
2. **Second Click:** Sets as **Transport Target** (Green). *Use this for destination chunks reachable by magic/transport.*
3. **Third Click:** Removes target (Resets to Locked).





---

### **5. Rolling & Simulations**

#### **Manual Play ("Roll Fate")**

* Click **"Roll Fate"** to perform one "turn".
* The system picks **one** random tile from all valid candidates:
* **Cyan (Rollable)**: Neighbors of unlocked chunks.
* **Purple (Target Reachable)**: Targets next to unlocked chunks.
* **Green (Transport)**: Special transport destinations.


* The winner becomes **Unlocked**, and neighbors are automatically updated.

#### **Statistical Simulations**

*(Requires at least one Target and one starting Rollable tile)*

* **"Simulate (Any)" – The Race**
* Calculates the average rolls to hit the **FIRST** available target.
* **Result:** Shows global average and the % chance of hitting specific target coordinates first.


* **"Simulate (All)" – The Full Clear**
* Calculates the average rolls required to unlock **ALL** selected targets on the map.



---

### **6. Saving & Loading**

* **Save:** Exports your grid progress (unlocked chunks and targets) to a `.json` file.
* **Load:** Restores a previous session.
* **Clear:** Resets the grid to a blank state. **Note:** This does *not* reset your camera view, allowing you to easily restart a run in the same specific map region.
