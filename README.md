# 3D Snake Game Assets

A collection of procedurally generated textures and assets for a Three.js-based 3D Snake Game.

## Repository Structure

```
.
├── textures/           # All game textures
│   ├── skybox/        # Skybox cube map textures
│   └── ...           # Various game textures
├── models/            # 3D models (placeholder)
├── audio/             # Sound effects (placeholder)
└── generate-textures.sh  # Script to regenerate textures
```

## Setup

1. Clone this repository
2. Ensure ImageMagick is installed: `sudo apt-get install imagemagick` (Linux) or `brew install imagemagick` (Mac)
3. Run `bash generate-textures.sh` to generate all textures
4. Push to GitHub to use as a CDN

## Using as a CDN

Once pushed to GitHub, access textures via:
```
https://raw.githubusercontent.com/[YOUR-USERNAME]/[REPO-NAME]/main/textures/[TEXTURE-NAME]
```

## Game Repository

The main game code is available at: [Your Game Repo URL]

## License

MIT License - Feel free to use these assets in your projects!
