# Car Animation

A 3D car animation web application built with React and Three.js, featuring interactive scenes and realistic models.

## Technologies Used

- React (Create React App)
- Three.js (for 3D rendering)
- GLTF Models (car.glb, ford.glb, modern_garage.glb)
- JavaScript
- CSS

## Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/deekshithgowda85/car-animation.git
   cd car-animation/my-app
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm start
   ```
   Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

## Project Structure

- `public/assets/` — 3D model files (`car.glb`, `ford.glb`, `modern_garage.glb`)
- `src/pages/` — Main scene and homepage components
- `src/` — App entry point and styles

## Three.js 3D Scene Features

- Uses Three.js for 3D rendering and scene management.
- Loads 3D models (`ford.glb` for the car, `modern_garage.glb` for the garage) using GLTFLoader.
- Implements cinematic camera shots for dynamic scene transitions.
- Adds dramatic lighting effects (directional, ambient, point, and spotlights).
- Creates a tire smoke effect using Three.js sprites and animated opacity.
- Animates car tires and smoke for realism.
- Handles window resizing for responsive 3D rendering.

### Example Code Snippet (Three.js setup and model loading)

```js
import * as THREE from 'three';
import { GLTFLoader } from 'three/examples/jsm/loaders/GLTFLoader';

const scene = new THREE.Scene();
scene.background = new THREE.Color(0x111111);

const camera = new THREE.PerspectiveCamera(
  60,
  window.innerWidth / window.innerHeight,
  0.1,
  100
);
camera.position.set(3, 2, 3);

const renderer = new THREE.WebGLRenderer({ alpha: true, antialias: true });
renderer.setSize(window.innerWidth, window.innerHeight);
container.appendChild(renderer.domElement);

// Lighting
const dirLight = new THREE.DirectionalLight(0xffffff, 2);
dirLight.position.set(5, 10, 5);
scene.add(dirLight);
scene.add(new THREE.AmbientLight(0x888888));

// Load Car Model
const loader = new GLTFLoader();
loader.load(
  '/assets/ford.glb',
  (gltf) => {
    const car = gltf.scene;
    car.position.set(0, 0.5, 0);
    car.scale.set(85, 85, 85);
    scene.add(car);
  }
);
```

## How to Add a Video to Your README

You can add a demo video to your README in two ways:

1. **Embed a YouTube Video (recommended):**
   ```markdown
   [![Demo Video](https://img.youtube.com/vi/YOUTUBE_VIDEO_ID/0.jpg)](https://www.youtube.com/watch?v=YOUTUBE_VIDEO_ID)
   ```
   Replace `YOUTUBE_VIDEO_ID` with your actual YouTube video ID.

2. **Add a Local Video (not supported by GitHub preview):**
   You can link to a video file in your repo, but GitHub will only show it as a link, not an embedded player:
   ```markdown
   [Download Demo Video](./path/to/video.mp4)
   ```

## License

This project is open source and available under the MIT License.
