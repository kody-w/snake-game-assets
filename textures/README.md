# 3D Snake Game Textures

This directory contains procedurally generated textures for the 3D Snake Game.

## Texture List

### Snake Textures
- `snake-scales.jpg` - Default green snake skin
- `snake-scales-blue.jpg` - Blue snake skin variant
- `snake-scales-red.jpg` - Red snake skin variant
- `snake-scales-gold.jpg` - Gold snake skin variant
- `snake-scales-normal.jpg` - Normal map for snake scales

### Food Textures
- `apple.png` - Red apple food item
- `food-green.png` - Green food variant
- `food-gold.png` - Golden food variant

### Environment Textures
- `grid.png` - Grid pattern for game board
- `grass.jpg` - Grass texture
- `stone-floor.jpg` - Stone floor texture
- `brick.jpg` - Brick wall texture
- `brick-normal.jpg` - Normal map for bricks
- `metal.jpg` - Metal surface texture
- `wood.jpg` - Wood texture

### Power-up Textures
- `powerup-speed.png` - Speed boost power-up
- `powerup-slow.png` - Slow-down power-up
- `powerup-invincible.png` - Invincibility power-up

### Skybox Textures
- `skybox/px.jpg` - Positive X face
- `skybox/nx.jpg` - Negative X face
- `skybox/py.jpg` - Positive Y face
- `skybox/ny.jpg` - Negative Y face
- `skybox/pz.jpg` - Positive Z face
- `skybox/nz.jpg` - Negative Z face

### Particle Effects
- `particle.png` - Basic particle
- `particle-star.png` - Star particle

## Usage

These textures are designed to be loaded via Three.js TextureLoader:

```javascript
const textureLoader = new THREE.TextureLoader();
const snakeTexture = textureLoader.load('textures/snake-scales.jpg');
```

For GitHub hosting, use raw URLs:
```javascript
const ASSET_URL = 'https://raw.githubusercontent.com/USERNAME/REPO/main';
const texture = textureLoader.load(`${ASSET_URL}/textures/snake-scales.jpg`);
```

## Generation

These textures were procedurally generated using ImageMagick.
To regenerate, run: `bash generate-textures.sh`
