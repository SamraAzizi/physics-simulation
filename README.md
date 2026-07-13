# 🎯 Physics Ball Launcher

A physics-based ball launching game built with Python, Pygame, and Pymunk. Click to create a ball, drag to aim, and release to launch it at structures — similar to Angry Birds mechanics!

![Python](https://img.shields.io/badge/Python-3.7+-blue.svg)
![Pygame](https://img.shields.io/badge/Pygame-2.0+-green.svg)
![Pymunk](https://img.shields.io/badge/Pymunk-6.0+-red.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

---

## 🎮 Gameplay

- **Click** anywhere to create a red ball
- **Drag** the mouse to set the launch angle and power (longer drag = more force)
- **Release** (click again) to launch the ball
- **Click again** to remove the ball and start over
- Try to knock down the wooden structures and dodge the swinging wrecking ball!

---

## 🚀 Features

- 🧲 **Realistic Physics** — Gravity, collisions, friction, and elasticity simulated using Pymunk
- 🎯 **Aiming System** — Visual aiming line with force proportional to drag distance
- 🏗️ **Destructible Structures** — Wooden pillars and beams with mass and physics properties
- ⚡ **Swinging Obstacle** — A wrecking ball on a rope that adds challenge
- 🖱️ **Intuitive Controls** — Simple mouse-based interaction
- 🎨 **Clean Visuals** — Minimalist design with clear physics visualization

---

## 📋 Requirements

- **Python 3.7 or higher**
- **Pygame 2.0+** — For graphics and event handling
- **Pymunk 6.0+** — For 2D physics simulation

---

## 🛠️ Installation

### Step 1: Clone the Repository
```bash
git clone https://github.com/yourusername/physics-ball-launcher.git
cd physics-ball-launcher
```
### step 2: Create a Virtual Environment (Recommended)
# Windows
python -m venv venv
venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate

### step 3: Install Dependencies

```bash
pip install pygame pymunk
```
Or use the requirements file:
```bash
pip install -r requirements.txt
```
## How to Run 
```bash
python main.py
```

## How it Works

#### physics Engine
The game uses Pymunk (a Python wrapper for Chipmunk2D) to simulate:
- Gravity — Objects fall naturally (981 pixels/s²)
- Collisions — Objects bounce and interact realistically
- Forces — Ball launch uses impulse-based physics
- Joints — The swinging ball uses a PinJoint (acts like a rope)

#### Game Loop
```bash
1. Handle mouse events (create/aim/launch)
2. Calculate force based on drag distance and angle
3. Apply impulse to launch ball
4. Update physics simulation (60 FPS)
5. Draw all objects and aiming line
```

#### Force Calculation
```bash
force = drag_distance × 50
angle = angle between click and release points
fx = cos(angle) × force  # Horizontal component
fy = sin(angle) × force  # Vertical component
```

### Physics Concept
- Impulse: Instant force applied to an object
- Elasticity: How bouncy a collision is (0 = no bounce, 1 = perfect bounce)
- Friction: Resistance when surfaces slide against each other
- Static Body: Doesn't move (walls, anchors)
- Dynamic Body: Moved by physics forces

