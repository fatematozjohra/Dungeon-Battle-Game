# 🎮 Dungeon Battle Game

A turn-based dungeon battle game developed using **Godot 4 and GDScript**, featuring grid-based movement, enemy AI, A* pathfinding, combat, resource management, and dynamic gameplay.

> **Group Project** — developed collaboratively as a team, with contributions across the game's core systems and gameplay logic.

---

## 🧠 Project Overview

Dungeon Battle Game is a **turn-based grid-based battle game** where the player competes against an AI-controlled enemy in a randomly generated dungeon.

Each turn follows a simple loop:

**Player Action → Enemy AI Decision → Enemy Action → Next Turn**

The enemy dynamically evaluates the player's position, its own health, and the location of healing resources before deciding what to do.

---

## 🤖 AI & Pathfinding

The game uses **AStarGrid2D (A*)** for obstacle-aware navigation.

### A* Pathfinding

* Grid-based navigation
* Obstacles are detected from the dungeon TileMap
* Blocked cells are marked as solid
* Diagonal movement is disabled
* Entities navigate using valid paths around obstacles
* The next movement step is selected from the calculated path

### Manhattan Distance

The AI uses Manhattan Distance to evaluate grid-based proximity:

```text
Distance = |X₁ - X₂| + |Y₁ - Y₂|
```

This allows the enemy to compare distances to the player and healing fruit.

### Enemy Decision System

The enemy follows a priority-based decision-making system:

1. 🍎 Consume nearby fruit
2. ❤️ Seek fruit when health is low
3. ⚔️ Attack the player when adjacent
4. 🍎 Move toward a closer healing resource
5. 🎯 Chase the player using A*

This creates an adaptive enemy that can switch between **healing, resource gathering, attacking, and pursuing the player**.

---

## 🎮 Gameplay Features

* 128×128 grid-based environment
* Turn-based combat
* Randomly generated obstacles
* Random player, enemy, and fruit placement
* WASD / Arrow-key movement
* Player attack system
* AI enemy combat
* Healing fruit system
* Dynamic fruit respawning
* A* obstacle-aware navigation
* Manhattan-distance radar
* Live player and enemy health display
* Win/Loss detection
* Restart / Play Again functionality

---

## ⚔️ Game Mechanics

| Element          | Behavior                               |
| ---------------- | -------------------------------------- |
| 🧑 Player        | Moves, attacks and collects fruit      |
| 🤖 Enemy         | Uses AI to make decisions and navigate |
| 🍎 Fruit         | Restores 20 HP and respawns            |
| ⚔️ Player Attack | Deals 10 damage                        |
| ⚔️ Enemy Attack  | Deals 11 damage                        |
| 🧱 Obstacles     | Block movement and navigation          |
| ❤️ Health        | Determines combat survival             |

---

## 🧩 Core Modules

The game logic is organized into five main scripts:

### `main.gd`

Game controller responsible for:

* Initializing the game
* Generating random obstacles
* Updating A* navigation
* Spawning entities
* Randomizing player, enemy and fruit positions
* Respawning collected fruit

### `dungeon_grid.gd`

Handles:

* Grid initialization
* TileMap obstacle detection
* AStarGrid2D configuration
* Blocking obstacle cells for pathfinding

### `enemy_ai.gd`

Controls enemy intelligence:

* Health evaluation
* Player and fruit distance calculation
* Decision-making
* Combat behavior
* Fruit-seeking behavior
* A* based movement

### `player.gd`

Handles:

* Keyboard input
* Grid movement
* Player attacks
* Fruit collection
* Health interactions
* Turn progression

### `ui_manager.gd`

Manages:

* Player health display
* Enemy health display
* Radar information
* Combat status
* Win/Loss messages
* Restart / Play Again functionality

---

## 🛠️ Technologies Used

* **Godot 4**
* **GDScript**
* **AStarGrid2D**
* **A* Pathfinding**
* **Manhattan Distance**
* **Grid-based Game Development**
* **Rule-based AI**
* **Turn-based Game Logic**

---

## 👥 Team Project & Contribution

This was developed as a **collaborative group project**.

Contributions were made across the game's core systems, including:

* Game controller and gameplay flow
* Grid and dungeon management
* Enemy AI and decision-making
* A* pathfinding and navigation
* Player movement and combat
* Health and healing mechanics
* User interface and game-state management
* Testing and gameplay refinement

The project provided practical experience in combining **AI decision-making, pathfinding algorithms, game logic, and interactive system design**.

---

## 📚 What I Learned

Through this project, I gained practical experience with:

* Implementing A* pathfinding in a game environment
* Designing rule-based AI behavior
* Using heuristic distance calculations
* Building turn-based game loops
* Working with grid-based environments
* Structuring game logic across multiple scripts
* Managing interactions between AI, player, environment, and UI
* Developing with the Godot game engine and GDScript

---

## 🚀 How to Run

1. Install **Godot 4**.
2. Clone or download this repository.
3. Open Godot Project Manager.
4. Import the project using `project.godot`.
5. Open the project.
6. Run the main scene.

---

## 🔗 Project Repository

**GitHub:**
https://github.com/fatematozjohra/Dungeon-Battle-Game

