# Roblox-Style Math Quest v4

A mobile-first educational math game featuring a 3D bridge defense scene built with Three.js.

## Features

### Game Mechanics
- **Bridge Defense**: Protect your base from enemies by solving math problems correctly
- **Progressive Difficulty**: Problems scale in difficulty as you level up
- **Weapon System**: Choose from 4 weapons with different difficulty levels:
  - **Fist** (Easy mode) - 10 damage
  - **Pistol** (Mid mode) - 18 damage
  - **AR** (Burst mode) - 14 damage per hit, requires 2 correct answers for full damage
  - **Bomb** (Hard mode) - 30 damage, affects all enemies

### Question Types
1. **BODMAS** - Order of operations problems (brackets, multiplication/division, addition/subtraction)
2. **Find X** - Algebraic equations to solve for x
3. **Physics** (Level 3+) - Speed-distance-time calculations
4. **Coordinates** (Level 5+) - Target lock problems with (x,y) coordinates

### Game Features
- Mobile-first responsive design
- iOS safe area support (notch devices)
- Touch-optimized bottom sheet UI
- WebAudio synthesized sound effects
- Streak bonuses (20% damage boost at 5+ streak)
- Pause/Resume functionality
- Auto-pause when tab is hidden
- Coin rewards that scale with level
- HP bars for enemies with color transitions
- 3D particle effects for coins

### Technical Details
- Built with vanilla JavaScript and Three.js
- Single HTML file (no build process required)
- Delta-time based animation for smooth gameplay
- Mobile viewport optimizations
- Keyboard support (Enter to submit)

## How to Play

1. Open `index.html` in a web browser
2. Click "Start" (or "Start (Muted)" for silent mode)
3. Read the math question displayed
4. Type your answer in the input field
5. Press "Submit" or hit Enter
6. Correct answers attack the closest enemy
7. Wrong answers temporarily speed up all enemies
8. Defend your base and progress through levels!

## Deployment

This game is automatically deployed to GitHub Pages whenever changes are pushed to the `main` branch.

**Live Demo:** The game will be available at `https://ismaelloveexcel.github.io/101225--PASS-SYSTEM/`

### Automatic Deployment

The repository uses GitHub Actions to automatically deploy the game:
- Any push to the `main` branch triggers automatic deployment
- Manual deployment can be triggered from the Actions tab
- No build process required - the game is deployed as-is

## Development

This is a single-file HTML game with no dependencies beyond Three.js (loaded from CDN).

To run locally:
```bash
# Simply open the file in a browser
open index.html

# Or use a local server
python -m http.server 8000
# Then visit http://localhost:8000
```

## Credits

Created as an educational math game for children, combining learning with engaging 3D gameplay.