# 🏛️ A.K TEMPLE RUNNER

<div align="center">

![Game Banner](https://img.shields.io/badge/A.K-TEMPLE%20RUNNER-f5c518?style=for-the-badge&labelColor=060d05&color=f5c518)
![Version](https://img.shields.io/badge/version-1.0.0-00f2c8?style=for-the-badge&labelColor=060d05)
![HTML5](https://img.shields.io/badge/HTML5-Canvas-e03030?style=for-the-badge&logo=html5&logoColor=white&labelColor=060d05)
![License](https://img.shields.io/badge/license-MIT-f5c518?style=for-the-badge&labelColor=060d05)

**एक jungle-neon ancient aesthetic वाला browser runner game — बिना किसी framework या library के!**

[▶ Live Demo](#) · [🐛 Bug Report](../../issues) · [✨ Feature Request](../../issues)

</div>

---

## 🎮 Game Preview

```
  🌙  ✦  ✦        ✦      ✦   ✦
 🌴🌳      🌴🌳         🌴🌳
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  [AK] ──► 🏛️ ▲▲▲  🦇   🪵
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## ✨ Features

| Feature | Details |
|---|---|
| 🎤 **Voice Control** | "Jump", "Fly", "Up" / "Slide", "Duck", "Down" बोलो — character respond करेगा |
| 🎵 **Procedural Music** | Web Audio API से real-time jungle beats — कोई external file नहीं |
| 🌴 **Parallax Background** | Multi-layer CSS animated jungle — sky, stars, moon, trees, ruins |
| 🏃 **Animated Character** | Pure Canvas 2D से बना stylized runner — arm/leg swing animation के साथ |
| 🦇 **5 Obstacle Types** | Pillar, Spike, Wall, Log, Bat (flying!) — हर obstacle unique drawing |
| 💰 **Coin System** | Arc और straight patterns में coins — particle burst on collect |
| 📱 **Mobile Support** | Touch swipe + on-screen buttons — fully responsive |
| ✨ **Particle Effects** | Jump dust, coin burst, death explosion — सब Canvas पर |
| 💾 **High Score** | `localStorage` में save — browser बंद करो, score रहेगा |
| ⚡ **Speed Scaling** | Game धीरे-धीरे fast होता जाता है — max speed तक |

---

## 🕹️ Controls

| Platform | Jump | Slide |
|---|---|---|
| ⌨️ **Keyboard** | `Space` / `↑` / `W` | `↓` / `S` |
| 📱 **Touch** | Swipe Up | Swipe Down |
| 🔘 **Mobile Buttons** | `⬆ JUMP` button | `⬇ SLIDE` button |
| 🎤 **Voice** | "jump" / "fly" / "up" | "slide" / "duck" / "down" |

> **Double Jump** भी supported है — हवा में एक बार और jump करो!

---

## 🚀 Setup & Run

### Option 1 — Direct Browser (Simplest)

```bash
# Clone karo
git clone https://github.com/YOUR_USERNAME/ak-temple-runner.git

# Folder mein jao
cd ak-temple-runner

# index.html ko browser mein open karo
open index.html       # macOS
start index.html      # Windows
xdg-open index.html   # Linux
```

### Option 2 — Local Server (Recommended for Voice Control)

Voice recognition ke liye `HTTPS` ya `localhost` chahiye hota hai.

```bash
# Python se local server
python3 -m http.server 8080

# Ya Node.js se
npx serve .

# Browser mein open karo
# http://localhost:8080
```

### Option 3 — VS Code Live Server

VS Code mein **Live Server** extension install karo, phir `index.html` pe right-click → *Open with Live Server*.

---

## 📁 Project Structure

```
ak-temple-runner/
│
├── index.html        # Main HTML — screens, HUD, mobile controls
├── style.css         # Jungle-neon aesthetic — parallax, animations, UI
├── game.js           # Game logic — physics, rendering, audio, voice
│
└── README.md         # Yahi file hai 😄
```

> **Zero Dependencies** — koi npm, koi bundler, koi framework नहीं। Pure HTML + CSS + Vanilla JS.

---

## 🏗️ Technical Architecture

### Game Loop
```
requestAnimationFrame
    └── updateGame()    ← physics, collision, scoring
    └── drawGame()      ← canvas rendering
```

### Audio Engine
Web Audio API से **procedural music** — pentatonic melody + drum pattern + bass drone, सब real-time synthesize होता है:
- 🥁 Kick + Snare + Hi-Hat pattern
- 🎵 Triangle wave melody (pentatonic scale)
- 🎸 Sawtooth bass drone
- 🔊 SFX: Jump, Coin, Slide, Death

### Parallax Layers (CSS)
```
Layer 1: Sky gradient          (static)
Layer 2: Stars                 (static)
Layer 3: Moon                  (static)
Layer 4: Far ruins             (22s scroll)
Layer 5: Far trees             (28s scroll)
Layer 6: Near trees            (14s scroll)
Layer 7: Canvas (game)         (JS controlled)
```

### Collision Detection
Forgiving AABB (Axis-Aligned Bounding Box) with 10px margin — gameplay fair रहे इसलिए।

---

## 🎨 Aesthetic

| Element | Choice |
|---|---|
| **Font** | Cinzel Decorative (Google Fonts) |
| **Primary Color** | `#f5c518` Gold |
| **Accent** | `#00f2c8` Neon Cyan |
| **Background** | `#060d05` Deep Jungle Dark |
| **Danger** | `#e03030` Red |
| **Theme** | Jungle-Neon Ancient Temple |

---

## 🔧 Configuration

`game.js` के top पर `CFG` object में सब कुछ tune करो:

```js
const CFG = {
  gravity:      0.55,    // ज़्यादा = heavy feel
  jumpForce:   -13,      // negative = upward (ज़्यादा negative = ऊँची jump)
  slideFrames:  40,      // slide कितने frames तक रहे
  groundFrac:   0.80,    // ground की position (0 = top, 1 = bottom)
  runnerX:      0.18,    // player screen के कितने % पर हो
  baseSpeed:    5.5,     // starting speed
  speedInc:     0.0008,  // हर frame speed कितनी बढ़े
  maxSpeed:     14,      // maximum speed cap
  pipeInterval: 90,      // हर कितने frames पर obstacle आए
  coinInterval: 55,      // हर कितने frames पर coins आएं
};
```

---

## 🛣️ Roadmap

- [ ] 🏆 Online leaderboard (Firebase integration)
- [ ] 🎭 Multiple character skins
- [ ] 🌏 Power-ups (shield, magnet, slow-mo)
- [ ] 🏛️ More obstacle types (traps, moving platforms)
- [ ] 🌙 Day/Night cycle
- [ ] 📊 Stats screen (distance, total coins)
- [ ] 🎮 Gamepad support

---

## 🤝 Contributing

Pull requests welcome हैं!

```bash
# Fork karo → Clone karo → Branch banao
git checkout -b feature/meri-nayi-feature

# Changes karo, commit karo
git commit -m "feat: naya power-up add kiya"

# Push karo
git push origin feature/meri-nayi-feature

# GitHub pe Pull Request open karo
```

---

## 📄 License

MIT License — freely use, modify, distribute. Credit दो तो अच्छा लगेगा! 😊

---

## 👥 Contributors

<div align="center">

<table>
  <tr>
    <td align="center">
      <a href="https://github.com/arushkumar-aiml">
        <img src="https://github.com/arushkumar-aiml.png" width="100px" alt="Arush Kumar" style="border-radius:50%"/><br/>
        <sub><b>Arush Kumar</b></sub>
      </a><br/>
      <sub>🤖 AI / ML · Game Logic · Architecture</sub><br/>
      <a href="https://github.com/arushkumar-aiml">
        <img src="https://img.shields.io/badge/GitHub-arushkumar--aiml-f5c518?style=flat-square&logo=github&logoColor=white&labelColor=060d05"/>
      </a>
    </td>
    <td align="center">
      <a href="https://github.com/ayushishuklaME">
        <img src="https://github.com/ayushishuklaME.png" width="100px" alt="Ayushi Shukla" style="border-radius:50%"/><br/>
        <sub><b>Ayushi Shukla</b></sub>
      </a><br/>
      <sub>🎨 UI / UX · Design · Styling</sub><br/>
      <a href="https://github.com/ayushishuklaME">
        <img src="https://img.shields.io/badge/GitHub-ayushishuklaME-00f2c8?style=flat-square&logo=github&logoColor=white&labelColor=060d05"/>
      </a>
    </td>
  </tr>
</table>

</div>

---

<div align="center">

Made with ❤️ and pure vanilla JavaScript

⭐ **Star karo agar game pasand aaya!** ⭐

</div>