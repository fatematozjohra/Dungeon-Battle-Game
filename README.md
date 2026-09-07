# Dungeon-Battle-Game
A turn-based AI dungeon battle game developed using Godot 4 and GDScript.
# 🛡️ Dungeon Battle Game

A turn-based strategic AI dungeon crawler game developed using **Godot 4** and **GDScript**. 

---

## 🎮 Game Overview
The game operates on a strict **128x128 pixel grid system**. It is a turn-based loop where the Player takes an action, and the Enemy follows up with its AI decision logic. The objective is to survive, collect healing resources (fruit), and defeat or outsmart the enemy AI.

---

## ⚙️ Core Architecture & Scripts
The entire game logic is controlled by 5 main modules:

1. **`main.gd` (Game Controller):** Manages game startup, random obstacle generation, entity spawning, and item respawning loops.
2. **`dungeon_grid.gd` (Pathfinding):** Integrates `AStarGrid2D` and TileMapLayer scanning to block out walls and provide valid navigation paths.
3. **`player.gd` (Player Control):** Detects WASD/arrow key inputs, handles grid collision, deals damage to enemies (10 HP), and consumes fruit (+20 HP).
4. **`enemy_ai.gd` (Enemy Intelligence):** State-machine AI that utilizes Manhattan distance and priority loops to hunt, heal, or flee.
5. **`ui_manager.gd` (User Interface):** CanvasLayer-based UI that tracks live health stats, displays combat proximity alerts, and manages the game-over restart loop.

---

## 🤖 Enemy AI Logic & Priorities
The AI evaluates its current health, player position, and fruit location using Manhattan Distance ($|X_1 - X_2| + |Y_1 - Y_2|$) under these strict priorities:
1. **Immediate Consumption:** Eats adjacent fruit instantly to heal (+20 HP).
2. **Self-Preservation:** Runs toward fruit if its health is lower than the player's.
3. **Attack:** Deals 11 damage when adjacent to the player.
4. **Resource Gathering:** Prioritizes closer fruit over fighting.
5. **Aggression:** Uses A* pathfinding to hunt down the player aggressively.

---

## 🚀 How to Run
1. Download and install [Godot 4](https://godotengine.org/).
2. Clone or download this repository to your local machine.
3. Open Godot Engine, click **Import**, and select the `project.godot` file from this project folder.
4. Press **F5** to run the game!
