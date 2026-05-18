# 🐧 Penguin Run HD

[![HTML5](https://img.shields.io/badge/HTML5-Canvas-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![JavaScript](https://img.shields.io/badge/JavaScript-Vanilla%20ES6-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![License](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)](#-license)
[![No Dependencies](https://img.shields.io/badge/Dependencies-Zero-brightgreen?style=for-the-badge)](https://github.com/ayuuXploits/penguin_V3.html)
[![Platform](https://img.shields.io/badge/Platform-Browser%20%7C%20Chrome%20%7C%20Edge-4285F4?style=for-the-badge&logo=googlechrome&logoColor=white)](https://www.google.com/chrome/)

> A penguin sprinting across a frozen arctic landscape, leaping over icebergs while a relentless sea lion closes in from behind. How long can you survive?

---

## 📋 Table of Contents

- [About](#-about)
- [Features](#-features)
- [Controls](#️-controls)
- [Progression System](#-progression-system)
- [Shop](#-shop)
- [Getting Started](#-getting-started)
- [Architecture](#️-architecture)
- [Customisation](#-customisation)
- [Screenshots](#-screenshots)
- [License](#-license)
- [Author](#-author)

---

## 🎮 About

**Penguin Run HD** is a fully self-contained, single-file browser game. You play as a penguin sprinting across a frozen arctic landscape, leaping over icebergs while a relentless sea lion closes in from behind. The longer you survive, the faster it gets.

No frameworks. No build tools. No server. Just open `index.html` and play.

---

## ✨ Features

### 🕹️ Core Gameplay

| Feature | Description |
|---|---|
| ♾️ Endless Runner | Procedurally generated iceberg obstacles that never repeat the same pattern |
| 🦘 Double Jump | Precise two-jump mechanic for navigating tight obstacle windows |
| 📈 Dynamic Difficulty | Speed and obstacle frequency scale continuously with your score |
| 🦭 Sea Lion Pursuer | Appears at score 200 and relentlessly closes the gap the longer you last |
| 🔴 Panic Vignette | Red screen edges pulse as the sea lion gets dangerously close |

### 🏆 Progression System

| Feature | Description |
|---|---|
| ⬆️ Levelling | Score-milestone based level-ups with visual celebration effects |
| 💰 XP & Coins | Earned through gameplay and mission completions |
| 💾 Persistent Saves | `localStorage` save system — your progress is never lost |
| 📅 Daily Login Streak | Escalating coin bonuses at 3-day, 7-day, 14-day, and 30-day milestones |
| 🎁 Daily Chest | One free chest per day containing 10–200 random coins |

### 📋 Missions

| Feature | Description |
|---|---|
| 📆 Daily Missions | 4 missions refreshed at midnight across Bronze, Silver, and Gold tiers |
| 🏅 Achievements | 12 long-term achievements tracking cumulative stats across all runs |
| 📊 Tracked Stats | Score, coins, gems, jumps, dodges, runs played, level reached, and more |
| 🎉 Reward Popups | Claim rewards directly from the Missions panel with animated popups |

### 🎨 Visual Polish

- Aurora borealis, parallax star fields, and animated snowfall
- Procedural mountain backgrounds with scrolling parallax layers
- Per-skin particle effects — Galaxy trails, Firebird embers
- Camera shake on death and level-up events
- Speed lines at high velocity
- Footprint trail on the ground
- Full coin collection particle burst and floating score text
- Animated sea lion with whiskers, eyes, and open-mouth expressions

---

## 🕹️ Controls

| Input | Action |
|---|---|
| `Space` / `↑` / `Tap` | Jump (press again mid-air for double jump) |
| `S` | Open Shop |
| `M` | Open Missions |
| `Escape` | Close panels |

---

## 🛒 Shop

### 🐧 Penguin Skins

| Skin | Price | Description |
|---|---|---|
| Classic | Free | The original arctic explorer |
| Royal Blue | 150 🪙 | Regal blue and gold |
| Shadow | 200 🪙 | Dark stealth operative |
| Firebird | 350 🪙 | Blazing ember trails |
| Galaxy | 500 🪙 | Cosmic particle effects |
| Gold | 1000 🪙 | Legendary — the rarest of all |

### 🌍 World Sceneries

| Scenery | Price | Description |
|---|---|---|
| Arctic Night | Free | Aurora borealis, default landscape |
| Lava Run | 200 🪙 | Volcanic red sky, glowing ground |
| Jungle Dusk | 250 🪙 | Tropical sunset atmosphere |
| Deep Space | 300 🪙 | Cosmic nebulae and star fields |
| Candy Land | 300 🪙 | Pastel skies and sweet terrain |
| Ice Desert | 350 🪙 | Stark frozen tundra |

### ⚡ Consumable Power-Ups

| Power-Up | Effect |
|---|---|
| 🧲 Coin Magnet | Attracts nearby coins for 8 seconds |
| 🛡️ Ice Shield | Absorbs one fatal iceberg hit |
| ⚡ Speed Boost | Turbo speed burst for 5 seconds |

---

## 🚀 Getting Started

No installation required.

### Clone & Play

```bash
# Clone the repository
git clone https://github.com/ayuuXploits/penguin_V3.html.git

# Navigate into the project
cd penguin_V3.html

# Open in your browser (macOS)
open index.html

# Open in your browser (Linux)
xdg-open index.html

# Open in your browser (Windows)
start index.html
```

### Or just download

Download `index.html` directly and open it in any Chromium-based browser — it's fully self-contained with zero external file dependencies.

> ⚠️ **Works best in Chrome or Edge.** Firefox may have minor canvas performance differences.

---

## 🏗️ Architecture

The entire game is written in vanilla HTML / CSS / JavaScript with zero dependencies.

```
index.html
├── Inline CSS            — UI, screens, shop, missions, animations
├── Canvas rendering      — Sky, ground, penguin, sea lion, obstacles, coins, particles
├── Game loop             — requestAnimationFrame-based at ~60 fps
├── Save system           — localStorage with versioned save key
├── Mission engine        — Daily + long-term with progress tracking
└── Shop system           — Skins, sceneries, consumable power-ups
```

**Key technical details:**

- Two layered `<canvas>` elements — main game canvas + speed lines overlay
- Procedural iceberg geometry using sine-wave point generation
- Skin and scenery preview rendered live onto mini canvases in the shop
- All assets loaded inline — Google Fonts via CDN, no local files required

---

## 🔧 Customisation

Everything is data-driven. Adding new content requires only a single array entry.

### Adding a New Skin

```javascript
{
  id: 'myskin',
  name: 'My Skin',
  desc: 'A short description shown in the shop.',
  price: 250,
  col1: '#1a003a',   // body colour
  col2: '#ddaaff',   // belly / face patch colour
  scarf: '#ff00cc',  // scarf colour
  beak: '#ffaa00'    // beak colour
}
```

### Adding a New Scenery

```javascript
{
  id: 'myscene',
  name: 'My World',
  desc: 'Description shown in the shop.',
  price: 300,
  sky1: '#000010',    // sky gradient top
  sky2: '#001030',    // sky gradient bottom
  ground1: '#204080', // ground gradient top
  ground2: '#0a1840', // ground gradient bottom
  aurora: true,       // show aurora borealis
  stars: true         // show star field
}
```

---

## 📸 Screenshots

| Arctic Night | Lava Run | Deep Space |
|:---:|:---:|:---:|
| Default scenery, aurora borealis | Volcanic red sky, glowing ground | Cosmic nebulae, star field |

---

## 📄 License

```
Copyright (c) 2026 Ayush Kumar (ayuuXploits). All rights reserved.
```

---

## 🙌 Author

**ayuuXploits**
- GitHub: [@ayuuXploits](https://github.com/ayuuXploits)

---

> *More features coming soon. Stay fast. Stay ahead of the sea lion.* 🦭
