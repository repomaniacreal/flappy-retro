# Flappy Bird — Retro Arcade

A self-contained, single-file recreation of Flappy Bird with a retro pixel-arcade UI: a home screen with your best score and medal progress, a gameplay screen, and a game-over summary with a mock leaderboard. Built with plain HTML, CSS, and JavaScript — no build step, no dependencies to install.

## Features

- Classic flap-to-fly gameplay with procedurally generated pipes
- Retro pixel-art UI (home, gameplay, and game-over screens)
- Best score saved locally between sessions
- Medal tiers (Bronze / Silver / Gold / Platinum) based on your score
- Chiptune-style sound effects generated on the fly with the Web Audio API (no audio files)
- Keyboard (Space / Arrow Up), tap, and on-screen button controls
- Responsive layout with light/dark theme support and safe-area handling for notched phones
- Share button to copy/share your score

## Prerequisites

None. You only need a modern web browser (Chrome, Firefox, Safari, or Edge, recent versions). No Node.js, npm, or build tools are required.

## Installation

There is nothing to install — the whole game lives in a single HTML file (`index.html`) with its CSS and JavaScript inlined.

1. Download `index.html`.
2. Place it anywhere on your computer or inside your project's folder.

That's it — there's no package to `npm install` and no build step to run.

## Running the game

**Option 1 — Open directly**
Double-click `index.html`, or open it from your browser with `File → Open`. This works out of the box for normal play.

**Option 2 — Serve it locally (optional, recommended for sharing/testing)**
Some browser features (like the clipboard fallback used by the Share button) behave more reliably when the page is served over `http://` instead of opened as a local `file://` path. Any static file server works, for example:

```bash
# Python 3
python3 -m http.server 8000

# Node.js (if you have it)
npx serve .
```

Then open `http://localhost:8000/index.html` in your browser.

**Option 3 — Host it anywhere**
Since it's a single static HTML file, you can drop it into any static host (GitHub Pages, Netlify, Vercel, S3, etc.) with no configuration.

## How to play

1. On the home screen, tap **Start Game**.
2. Flap by tapping/clicking the game area, pressing **Space** or **Arrow Up**, or tapping the **Flap** button.
3. Guide the bird through the gaps between the green pipes without hitting them or the ground.
4. Each pipe you clear adds a point. Your best score is saved automatically.
5. On the game-over screen, tap **Play Again** to retry, or **Share** to copy/share your score.

## Project structure

```
index.html   # Everything: markup, styles, and game logic in one file
```

## Configuration

Gameplay feel can be tuned by editing the constants at the top of the `<script>` block in `index.html`:

| Constant       | Description                                  |
|----------------|-----------------------------------------------|
| `GRAVITY`      | How fast the bird accelerates downward        |
| `FLAP_V`       | Upward velocity applied on each flap          |
| `MAX_FALL`     | Terminal falling speed                        |
| `PIPE_SPEED`   | How fast pipes scroll across the screen       |
| `PIPE_GAP`     | Vertical gap between the top and bottom pipe  |
| `PIPE_SPACING` | Horizontal distance between pipe pairs        |
| `TIERS`        | Score thresholds and colors for medal tiers   |

## Data storage

Your best score is stored in the browser's `localStorage` under the key `flappyBestScore`. Clearing your browser's site data (or opening the file in a different browser/profile) will reset it.

## Browser support

Works in any modern evergreen browser with support for CSS custom properties, `flexbox`, and the Web Audio API. Sound effects are silently skipped if the Web Audio API is unavailable.

## Known limitations

- There is currently no in-app button to return to the home screen once you've entered the gameplay or game-over screen — navigate there by reloading the page, or use the **Play Again** button to start a new run.
- The mock leaderboard and rival scores shown after a run are illustrative placeholders, not live/online data.

## License

Add the license of your choice here (e.g., MIT) before distributing this project.
