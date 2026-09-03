# A Special Voice Adventure 💛

A playful voice-controlled browser game — a five-level surprise adventure made for Rakshita.

## 🎮 How to Play

### Voice Controls (Primary)
- **Gentle/normal voice** → your runner moves forward (louder = faster)
- **Short loud sound ("HA!")** → jump
- **Silence** → the character stops

### Keyboard / Touch (Backup)
- **Space** or **Jump button** → jump
- **P** → pause
- **Enter** → advance through dialogues / confirm overlays

## 🎤 Microphone Calibration

Before playing, the game measures your microphone to set personalized thresholds:
1. **Quiet phase** — measures ambient noise level
2. **Voice phase** — measures your normal talking volume
3. **Loud phase** — detects a short shout to set the jump threshold

This ensures the game works on any device/microphone without hardcoded sensitivity values.

## 🗺️ The 5 Levels

| Level | Theme | New Obstacles |
|-------|-------|---------------|
| 1 | Sunny Meadow 🌻 | Ground crates, overhead spikes |
| 2 | Forest Trouble 🌲 | Moving spike balls, falling rocks (with warning) |
| 3 | Arrow Alley 🏹 | Flying arrows, rotating blades |
| 4 | Chaos Canyon ⚡ | Gaps/pits, all types combined |
| 5 | Final Battlefield 🔥 | Crushers, max intensity |

Each level has distinct visuals (sky, ground, particles, atmosphere) and fair procedural obstacle generation.

## 🏆 The Reward

Complete all 5 levels to reveal the `certificate.png` — the final surprise.

## 📁 Files

- `index.html` — complete self-contained game (HTML + CSS + JS)
- `certificate.png` — the surprise certificate image
- `.github/workflows/deploy.yml` — automatic GitHub Pages deployment

## 🧪 Testing Locally

```bash
# Option 1: Python
cd game
python -m http.server 8000
# Open http://localhost:8000

# Option 2: VS Code Live Server extension
# Right-click index.html → Open with Live Server

# Option 3: Node.js
npx -y serve .
```

> **Note:** Microphone access requires HTTPS or `localhost`. A plain `file://` URL will not grant mic permission.

## 🚀 Deploying to GitHub Pages

1. Create a public repository on GitHub
2. Upload all files (including `.github/` folder) and push to `main`
3. Go to **Settings → Pages → Source** → select **GitHub Actions**
4. The workflow in `.github/workflows/deploy.yml` will automatically deploy
5. Your game will be live at: `https://YOUR-USERNAME.github.io/YOUR-REPO/`

GitHub Pages serves over HTTPS, so microphone access works after the user grants permission.

## 🔧 Technical Details

- **No server required** — 100% static HTML/CSS/JS
- **No external dependencies** — only Google Fonts (Nunito) for typography
- **Web Audio API** — microphone input + generated sound effects
- **Canvas rendering** — smooth 60fps game loop with `requestAnimationFrame`
- **Mobile-first** — responsive layout designed for 320px–430px phone screens
- **Fair obstacles** — procedural generation with minimum spacing, max simultaneous threats, and combo validation rules
