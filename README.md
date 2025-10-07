# 🐍 Snake Game with AI Opponent and Mobile Controls

## Overview

This project implements a modern **Snake Game** in pure HTML, CSS, and JavaScript, featuring both a **human-controlled player snake** and an **AI-controlled opponent**.  
The game runs entirely in the browser with no dependencies or backend services required.

In addition to keyboard controls for desktop play, the interface includes **touch-friendly directional buttons**, making it fully playable on **mobile devices and tablets**.

---

## 🎮 Features

| Category | Description |
|-----------|-------------|
| **Gameplay** | Classic snake movement with growth mechanics, grid boundaries, and collision detection. |
| **AI Opponent** | A simple rule-based AI that seeks the reward using Manhattan distance while avoiding collisions. |
| **Reward System** | Randomly spawned “food” blocks that cause the snake to grow and increase the score. |
| **Game End Conditions** | Player wins, loses, or ties depending on collisions. |
| **Mobile-Friendly Controls** | Large, symmetric directional buttons positioned below the canvas for easy thumb access. |
| **Responsive Design** | Canvas and controls scale smoothly across screen sizes (desktop, tablet, mobile). |
| **Accessibility** | ARIA labels and mirrored score display for screen readers. |

---

## 🧠 Game Logic Overview

### Player Snake
- Moves one grid cell per frame in the current direction.
- Controlled via keyboard (`WASD` / arrow keys) or on-screen buttons.
- Grows by one cell when consuming a reward.
- Loses if it collides with itself, a wall, or the AI snake.

### AI Snake
- Evaluates four possible directions every frame.
- Avoids moving into:
  - Its own body
  - The player’s body
  - The grid boundaries
- Chooses the direction minimizing **Manhattan distance** to the reward.

### Reward Generation
- The reward appears at a random location not occupied by either snake.
- When eaten, it respawns in another valid position.

---

## 🧩 Code Structure

| Section | Purpose |
|----------|----------|
| **HTML** | Defines the canvas, score area, and mobile control buttons. |
| **CSS** | Styles the layout, colors, button design, and responsive behavior. |
| **JavaScript** | Implements all game logic: rendering, movement, AI, scoring, and input handling. |

### Key JavaScript Functions
- `moveSnake()` – advances a snake by one cell.
- `collision()` – detects wall and self-collisions.
- `aiChooseDirection()` – AI chooses next direction based on reward proximity.
- `update()` – main game loop (every 100 ms).
- `draw()` – draws everything on the canvas.
- `endGame()` – displays a message and restarts the game.

---

## 🕹️ Controls

### Desktop
| Action | Keys |
|---------|------|
| Move Up | `ArrowUp` or `W` |
| Move Down | `ArrowDown` or `S` |
| Move Left | `ArrowLeft` or `A` |
| Move Right | `ArrowRight` or `D` |

### Mobile / Tablet
Large on-screen buttons appear below the game canvas.
Each button triggers the same movement as the corresponding keyboard key.

---

## ⚙️ Installation & Usage

1. **Clone or download** the repository:
   ```bash
   git clone https://github.com/yourusername/snake-ai-game.git
   ```
  
2. **Open** the index.html file in any modern web browser.

3. **Play** using keyboard or on-screen controls.

No build tools or servers are required.
