<!-- retired-notice:start -->
> **Archived.** No longer maintained; kept public for reference.
<!-- retired-notice:end -->

# 🎮 Centralized Game Assets Repository

A comprehensive collection of procedurally generated textures and assets for multiple HTML5/WebGL games. All assets are optimized for GitHub CDN hosting.

## 🏗️ Repository Structure

```
.
├── textures/           # All game textures organized by game
│   ├── snake/         # Snake game textures
│   ├── doom/          # DOOM shooter textures
│   ├── racing/        # Racing game textures
│   ├── space/         # Space invaders textures
│   ├── puzzle/        # Puzzle game textures
│   ├── tower/         # Tower defense textures
│   ├── common/        # Shared textures
│   ├── skybox/        # Skybox textures for all games
│   ├── particles/     # Particle effect textures
│   └── ui/           # UI element textures
├── models/            # 3D models (OBJ format)
├── audio/             # Sound effects and music
│   ├── music/        # Background music
│   └── sfx/          # Sound effects
├── games/             # Game catalog and metadata
├── data/              # Configuration and data files
├── fonts/             # Web fonts
└── sprites/           # 2D sprite sheets
```

## 🎮 Supported Games

1. **3D Snake** - Classic snake with modern 3D graphics
2. **DOOM Shooter** - Intense FPS action game
3. **Space Invaders 3D** - Retro classic reimagined
4. **Racing Fury** - High-speed racing game
5. **Puzzle Master** - Mind-bending 3D puzzles
6. **Tower Defense 3D** - Strategic tower defense

## 🚀 Usage

### As a CDN

Access any asset directly via GitHub raw URLs:

```javascript
const ASSET_BASE = 'https://raw.githubusercontent.com/[USERNAME]/[REPO]/main';
const texture = `${ASSET_BASE}/textures/snake/snake-scales.jpg`;
```

### In Three.js

```javascript
const textureLoader = new THREE.TextureLoader();
textureLoader.crossOrigin = 'anonymous';

// Load texture
const snakeTexture = textureLoader.load(
    `${ASSET_BASE}/textures/snake/snake-scales.jpg`
);

// Apply to material
const material = new THREE.MeshPhongMaterial({ 
    map: snakeTexture 
});
```

### Game Catalog

Load the game catalog to get all available games:

```javascript
fetch(`${ASSET_BASE}/games/catalog.json`)
    .then(res => res.json())
    .then(catalog => {
        console.log('Available games:', catalog.games);
    });
```

## 📊 Asset Statistics

- **Total Textures**: 100+
- **Texture Resolutions**: 256x256 to 1024x1024
- **File Formats**: JPG (textures), PNG (UI/particles)
- **Total Size**: ~50MB (optimized)
- **Games Supported**: 6+

## 🎨 Texture Categories

### Game-Specific
- Snake skins and food items
- DOOM walls, floors, and demons
- Racing tracks and vehicles
- Space backgrounds and ships
- Puzzle tiles and gems
- Tower defense terrain and towers

### Shared Assets
- Skyboxes (day, night, hell)
- Particle effects (fire, smoke, explosions)
- UI elements (buttons, bars, icons)
- Common materials (metal, wood, stone)

## 🔧 Generation

All textures are procedurally generated using ImageMagick:

```bash
bash generate-assets.sh
```

### Requirements
- ImageMagick 7.0+
- Bash 4.0+
- 100MB free disk space

## 📈 Performance

Assets are optimized for web delivery:
- Compressed JPG for textures (90% quality)
- PNG for transparency (UI/particles)
- Mipmapping recommended for 3D textures
- Lazy loading supported

## 🤝 Contributing

1. Fork the repository
2. Add new textures to appropriate directories
3. Update `games/catalog.json`
4. Submit a pull request

## 📜 License

MIT License - Free to use in personal and commercial projects

## 🔗 Links

- [Game Hub Platform](#)
- [Documentation](#)
- [Discord Community](#)

## 💡 Tips

### Caching
Enable browser caching for better performance:

```javascript
const textureCache = new Map();

function loadTexture(path) {
    if (textureCache.has(path)) {
        return textureCache.get(path);
    }
    const texture = textureLoader.load(path);
    textureCache.set(path, texture);
    return texture;
}
```

### Quality Settings
Adjust texture resolution based on device:

```javascript
const isMobile = /Mobile/.test(navigator.userAgent);
const quality = isMobile ? 'low' : 'high';
const texturePath = `textures/${quality}/texture.jpg`;
```

## 🎮 Example Game Integration

```html
<!DOCTYPE html>
<html>
<head>
    <title>My Game</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
</head>
<body>
    <script>
        const ASSETS = 'https://raw.githubusercontent.com/USER/REPO/main';
        
        // Load game catalog
        fetch(`${ASSETS}/games/catalog.json`)
            .then(res => res.json())
            .then(catalog => {
                const game = catalog.games.find(g => g.id === 'snake3d');
                loadGameAssets(game);
            });
        
        function loadGameAssets(game) {
            const loader = new THREE.TextureLoader();
            game.assets.textures.forEach(texture => {
                loader.load(`${ASSETS}/${texture}`);
            });
        }
    </script>
</body>
</html>
```

---

Made with ❤️ for the gaming community
