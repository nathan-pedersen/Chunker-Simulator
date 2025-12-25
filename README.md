# 100% VIBE CODED :)

`javascript` `osrs` `oldschool-runescape` `simulation` `chunk-locked` `pathfinding` `monte-carlo`

# OSRS Chunk Picker (Web Edition)

A high-performance, browser-based tool for simulating **Chunk-Locked Ironmen** accounts in Old School RuneScape. This tool allows you to interactively "unlock" the world map chunk-by-chunk using procedural rolling mechanics.

## 🚀 How to Run
* https://github.com/nathan-pedersen/Chunker-Simulator/deployments/github-pages

## 🎮 Controls & Interface

### **Navigation**
* **Pan:** Click and **Hold Left Mouse** to drag the map.
* **Zoom:** Use the **Scroll Wheel** to zoom in/out relative to your cursor.
* **Recenter:** Click the **Recenter View** button to jump to your unlocked territory.

### **Map Interactions**
* **Unlock/Lock Chunk:** **Left Click** on a tile.
* **Force Rollable:** **Right Click** a tile to manually mark it as "Rollable" (Cyan).
* **Set Target:** **Middle Click** (or Shift+Left Click) a tile to cycle through target states:
    1.  **Target (Red/Purple):** A standard goal chunk.
    2.  **Transport (Green):** A chunk reachable via teleport (Spirit Tree, Fairy Ring, etc).
    3.  **Off:** Removes the target.

### **Simulation Tools**
* **Roll Fate:** Randomly selects **one** valid chunk (Cyan, Purple, or Green) to unlock.
* **Simulate (Race):** Calculates the average rolls to reach **ANY ONE** of your active targets.
* **Simulate (Clear):** Calculates the average rolls to unlock **ALL** active targets.

### **Save & Load**
* **Save:** Downloads a `.json` file containing your current progress.
* **Load:** Restores your grid state from a previously saved JSON file.
* *Note: Your browser may cache the map image, but grid progress is not auto-saved to local storage. Always save before closing.*
