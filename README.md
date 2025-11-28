# Mesh-Manipulation
A real-time system that simulates cutting of a deformable mesh
An interactive 3D cloth physics simulation built with Three.js that allows you to interact with and cut realistic fabric in real-time.

## Features

- **Realistic Physics**: Position-based dynamics simulation with gravity and constraints
- **Interactive Cloth**: Click and drag to pull and interact with the fabric
- **Cutting Mechanism**: Right-click and drag to cut through the cloth
- **Visual Feedback**: See your cut line in red before releasing
- **Smooth Animation**: 60 FPS physics simulation with constraint solving

## Controls

| Action | Control |
|--------|---------|
| **Pull Cloth** | Left-click and drag near the fabric |
| **Cut Cloth** | Right-click and drag across the fabric |
| **Mouse Hover** | Cloth reacts subtly to cursor position |
| **Reset** | Click the "Reset Cloth" button (or reload page) |

## Working 

### Physics System

The simulation uses a particle-based approach with distance constraints:

- **Particles**: Each vertex in the cloth mesh is a particle with position, velocity, and mass
- **Constraints**: Particles are connected by structural, shear, and bend constraints
- **Solver**: Uses iterative constraint satisfaction (5 iterations per frame)
- **Verlet Integration**: Stable physics integration for cloth dynamics

### Cutting Algorithm

When you right-click and drag:

1. A cut line is drawn from start to end point
2. The system checks all constraints against this line
3. Constraints intersecting the cut line are deactivated
4. The mesh topology is updated to reflect the cut
5. Cut particles receive separation forces for realistic tearing


## Installation

Simply open the HTML file in a modern web browser. No build process or dependencies required.

```bash
# Clone or download the file
# Open in browser
open cloth-simulation.html
```

## Browser Requirements

- Modern browser with WebGL support
- ES6 module support
- Tested on Chrome, Firefox, Safari, and Edge

## Dependencies

- **Three.js r128**: Loaded from CDN (https://cdnjs.cloudflare.com)
- No other dependencies required



## Customization

You can modify these parameters in the code:

```javascript
const width = 10;           // Cloth width
const height = 10;          // Cloth height
const segments = 25;        // Grid resolution
const solverIterations = 5; // Constraint solving accuracy
const gravity = new THREE.Vector3(0, -9.8, 0); // Gravity force
```




---

**Tip**: Try making small cuts first, then pull on the separated pieces for the most dramatic effect!
