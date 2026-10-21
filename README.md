# 🧹 Kiki's Store

![Java](https://img.shields.io/badge/Java-17+-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![JavaFX](https://img.shields.io/badge/JavaFX-17+-4285F4?style=flat-square&logo=java&logoColor=white)
![Gradle](https://img.shields.io/badge/Gradle-02303A?style=flat-square&logo=gradle&logoColor=white)
![Architecture](https://img.shields.io/badge/Architecture-MVC%20%2B%20State%20Pattern-blueviolet?style=flat-square)
![Testing](https://img.shields.io/badge/Tests-JUnit%205-25A162?style=flat-square&logo=junit5&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)

> *A 2D pixel art adventure and potion-crafting game inspired by Studio Ghibli's Kiki's Delivery Service, built with Java and JavaFX.*

## 🌟 Key Highlights

- **Custom Game Engine & Loop:** Driven by JavaFX `AnimationTimer` with decoupled update, clear, and render phases.
- **State Pattern with Stack Navigation:** Multi-context lifecycle management (`pushState`, `popState`, `pause`, `resume`) to preserve world state across minigames and menus.
- **Data-Driven Alchemy Engine:** Ingredient catalogs, recipes, and potion variations dynamically loaded and validated from external JSON datasets via Gson.
- **Dynamic Item Spawner:** Autonomous terrain-aware item spawning strictly constrained to walkable tiles using safe iterator-based collections.
- **Integrated Minigames:** Built-in secondary gameplay loops, including a broomstick flying obstacle course and a potion-matching Memory game.

## ℹ️ Overview

**Kiki's Store** is a 2D desktop adventure game where you play as a young witch opening her potion shop in a fantasy village. Players can explore the map, collect ingredients, brew potions, and play fun minigames. The project is built in Java and JavaFX, using OOP principles and MVC architecture.

## 🎮 Gameplay & Features

- **Exploration:** Roam through the village map to collect dynamically spawned plants, roots, and flowers.
- **Interactive Magic Book:** A unified book interface featuring page-turning animations to view the inventory and browse unlocked recipes.
- **Cauldron Brewing (Crafting):** Combine collected ingredients to brew potions. Invalid ingredient combinations will result in failed potions.
- **Energy & Economy System:** Every successful brewing attempt impacts stamina, requiring players to balance resources and rewards.
- **Interactive Minigames:**
  - **Broom Flight:** A side-scrolling obstacle avoidance session.
  - **Potion Memory:** A tile-matching puzzle game with turn limits and stamina/coin rewards.

## 🛠️ Architecture & Design Patterns

The codebase adheres to the **Model-View-Controller (MVC)** architectural paradigm:

- **State Pattern (Stack-Based):** `GameStateManager` manages active gameplay screens (`VillageState`, `CraftingState`, `BookState`, `MemoryState`) on a deque. Sub-states can be paused and stacked without unloading assets.
- **Strategy Pattern:**
  - Applied to the magic book (`BookSection`), allowing dynamic switching between inventory views and recipe index pages.
  - Employed in inventory mutations using functional interfaces (`Supplier<T>`, `Consumer<T>`).
- **Passive View with Immutable Projections:** The view never mutates internal game state directly; it renders frames consuming read-only DTO records (`RenderData`).

## 🕹️ Controls

| Key | Action |
| :--- | :--- |
| **W, A, S, D** / **Arrow Keys** | Move character (Up, Left, Down, Right) |
| **E** | Interact / Confirm selection |
| **I** | Open Magic Book (Inventory & Recipes) |
| **C** | Open Cauldron (Crafting) |
| **ESC** | Pause game / Close overlay screens |

## 💻 Developer Setup

### Prerequisites
- **Java Development Kit (JDK) 17** or higher
- **Gradle 7+** (or use the included wrapper)

### Installation & Execution

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Leon7-cmd/OOP25-Kiki-Store.git
   ```

2. **Enter the directory:**
   ```bash
   cd OOP25-Kiki-Store
   ```

3. **Build the project:**
   ```bash
   ./gradlew build
   ```

4. **Run the game:**
   ```bash
   ./gradlew run
   ```

## 👥 Contributors

- **Leonardo Galimi** ([@Leon7-cmd](https://github.com/Leon7-cmd)) – Game Engine, State Machine, World & Collision Physics, Dynamic Item Spawner.
- **Hafsa Nouij** ([@Haffy03](https://github.com/Haffy03)) – Inventory & Recipe Management, Crafting Engine, Memory Minigame.

## 🎨 Asset Credits

- **Terrain & Map Sprites:** Open-source sprites from the [LPC Terrain Repack (OpenGameArt)](https://opengameart.org/content/lpc-terrain-repack).
- **Potion & UI Assets:** [CraftPix Animated Magic Book Pixel Art Asset Pack](https://craftpix.net/freebies/free-animated-magic-book-pixel-art-asset-pack/). 

## 📄 License

Distributed under the MIT License. See [LICENSE](LICENSE) for more information.
