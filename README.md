# Long Drive

Long Drive is a standalone HTML5 Canvas pseudo-3D driving game with a synthwave AI-copilot aesthetic. It runs directly in a current desktop or mobile browser: no build step, framework, or server is required.

## Features

- Three-car procedural Canvas garage:
  - BMW 7 Series / i7: illuminated kidney grille, ambient trim, high acceleration, smooth handling, 200 KM/H maximum.
  - Toyota Fortuner GR Sport: lifted SUV body, roof rails, rugged bumper, high traction, 180 KM/H maximum.
  - Bugatti-inspired hypercar: horseshoe treatment, active spoiler, wide diffuser and continuous rear LED strip, 260 KM/H maximum.
- Car-specific acceleration curves, top speeds, steering response, grip, and body rendering.
- Multi-layer synthwave twilight sky with animated gradient clouds, horizon sun, skyline silhouettes, and horizon glow.
- High-speed perspective road grid, neon roadside pillars/palms, moving lane markers, and speed particle trails.
- Selectable Neon Cyber, BMW Pro Driver, and AI Synth Bot operator profiles.
- Live AI/ML telemetry for precision, driver link, and adaptive-drive multiplier.
- Keyboard and full touch steering, brake, and throttle controls.
- Pause/resume support and optional looping music from `song.mp3`.

## Run

1. Keep these files in the same directory:
   - `index.html`
   - `style.css`
   - `game.js`
   - `song.mp3`
2. Open `index.html` in a modern browser.
3. Choose a driver, browse the Garage with the left/right controls, and select **Initialize Drive**.

Audio begins after the launch click because browsers require a user interaction before playback. The game remains playable if `song.mp3` is absent.

## Controls

| Action | Desktop | Touch |
| --- | --- | --- |
| Steer | Left/Right arrows or A/D | Drag the steering wheel around its center, or hold the on-screen left/right arrows |
| Accelerate | Up arrow or W | Hold GAS |
| Brake / reverse | Down arrow or S | Hold BRAKE |
| Pause | Escape or pause button | Pause button |

## Project structure

```text
long-drive/
├── index.html   # Garage, driver selector, HUD, controls, and audio integration
├── style.css    # Responsive cyberpunk UI and garage carousel styling
├── game.js      # Canvas rendering, vehicle physics, telemetry, and input
├── song.mp3     # Optional background track
└── README.md
```

## Notes

All vehicle and environment art is drawn with Canvas 2D; no image assets are required. Rendering is resolution-aware and limits canvas pixel density to 2x for smooth high-DPI performance.
