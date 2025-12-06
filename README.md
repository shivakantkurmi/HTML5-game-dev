# 🧟 Resident Raver

A classic side-scrolling platformer built using the **ImpactJS Game Engine** for an academic project. This game is based on the tutorial series from a professional game development guide.

## 🕹️ Game Overview

**Resident Raver** puts the player in control of an unnamed hero trying to escape a college dorm overrun by raver zombies. The game requires the hero to navigate platform-based obstacles while utilizing various weapons to survive.

### Core Mechanics

* **Platform Physics:** Features character movement with acceleration on the ground (`accelGround: 400`) and in the air (`accelAir: 200`), jump strength (`jump: 200`), and friction (`friction: {x: 600, y: 0}`).
* **Weapon System:** The hero can switch between two weapons:
    * **Gun (EntityBullet):** Fires fast-moving projectiles (Damage: 3).
    * **Grenade (EntityGrenade):** Thrown with an arc, bounces up to 3 times, and explodes on contact or limit (Damage: 10).
* **Collision Model:** Uses ImpactJS entity types: Player is **TYPE.A** (Friendly), and Zombies are **TYPE.B** (Hostile).
* **Death & Respawn:** Player death triggers an `EntityDeathExplosion` (particle system) and respawns the player at their `startPosition` with a 2-second period of invincibility.

---

## 💻 Tech Stack & Setup

### Prerequisites

1.  **ImpactJS Engine:** The foundation of the project.
2.  **Local Web Server:** Must be running and configured to support **PHP** (e.g., MAMP, XAMPP, or equivalent) to use the Weltmeister editor's save functionality.
3.  **Game Assets:** The contents of the `media` folder (sprites, map tiles, and sounds) from the book's example files must be copied into the project's `media/` directory.

### Running the Game

1.  Ensure your local web server is running.
2.  Open your web browser.
3.  Navigate to the project's entry point: `http://localhost/[your-impact-directory]/index.html`.

### 🛠️ Editor (Weltmeister)

The **Weltmeister** editor is used for map design and entity placement.

1.  Open the editor in your browser: `http://localhost/[your-impact-directory]/weltmeister.html`
2.  Maps (`dorm1.js`, `dorm2.js`, etc.) are saved automatically to `lib/game/levels/`.

---

## ⌨️ Controls

The input bindings are set in `lib/game/main.js`:

| Action | Key Binding | Purpose |
| :--- | :--- | :--- |
| **Move Left** | Left Arrow | Horizontal movement |
| **Move Right** | Right Arrow | Horizontal movement |
| **Jump** | SPACE Key | Vertical jump |
| **Shoot** | F Key | Fire the active weapon (Bullet or Grenade) |
| **Switch Weapon** | TAB Key | Cycles between the two available weapons |

---

## 📜 Repository File Structure

* `index.html`: The main file to run the game.
* `lib/game/main.js`: The game entry point. Holds gravity, key bindings, camera logic, and initial level loading (`LevelDorm1`).
* `lib/game/entities/player.js`: Contains `EntityPlayer` and all inner classes for weapons (`EntityBullet`, `EntityGrenade`) and particle effects (`EntityDeathExplosion`, `EntityGrenadeParticle`).
* `lib/game/entities/zombie.js`: Defines the enemy logic (AI, movement, collisions).
* `lib/game/entities/levelexit.js`: An invisible trigger used to load the next map (`dorm2`).
* `lib/game/levels/dorm1.js`: Level data for the first map.

---

## 📝 Credits

* **Game Engine:** ImpactJS
* **Developer:** Arrow-sudo531
