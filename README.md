
                                                       ░██                                             
                                                                                                       
░████████   ░███████  ░████████   ░████████ ░██    ░██ ░██░████████     ░██░████ ░██    ░██ ░████████  
░██    ░██ ░██    ░██ ░██    ░██ ░██    ░██ ░██    ░██ ░██░██    ░██    ░███     ░██    ░██ ░██    ░██ 
░██    ░██ ░█████████ ░██    ░██ ░██    ░██ ░██    ░██ ░██░██    ░██    ░██      ░██    ░██ ░██    ░██ 
░███   ░██ ░██        ░██    ░██ ░██   ░███ ░██   ░███ ░██░██    ░██    ░██      ░██   ░███ ░██    ░██ 
░██░█████   ░███████  ░██    ░██  ░█████░██  ░█████░██ ░██░██    ░██    ░██       ░█████░██ ░██    ░██ 
░██                                     ░██                                                            
░██                               ░███████                                                             
                                                                                                       


🎮 About
Penguin Run HD is a fully self-contained, single-file browser game. You play as a penguin sprinting across a frozen arctic landscape, leaping over icebergs while a relentless sea lion closes in from behind. The longer you survive, the faster it gets.
No frameworks. No build tools. No server. Just open index.html and play.

✨ Features
Core Gameplay

Endless runner with procedurally generated iceberg obstacles
Double jump mechanic for precise obstacle navigation
Dynamic difficulty — speed and obstacle frequency scale with your score
Sea lion pursuer that appears at score 200 and never stops chasing
Panic vignette — red screen edges pulse as the sea lion gets dangerously close

Progression System

Levelling based on score milestones
XP & Coins earned through gameplay and mission completions
Persistent save data via localStorage — your progress is never lost
Daily login streak with escalating coin bonuses (3-day, 7-day, 14-day, 30-day rewards)

Daily Chest

One free chest per day containing 10–200 random coins
Come back tomorrow for the next one

Missions

4 daily missions (refreshed at midnight) across Bronze, Silver, and Gold tiers
12 long-term achievements that track cumulative stats across all runs
Missions track: score, coins, gems, jumps, dodges, runs played, level reached, and more
Claim rewards directly from the Missions panel with animated popups

Shop

6 penguin skins — Classic, Royal Blue, Shadow, Firebird, Galaxy, and the legendary Gold skin
6 world sceneries — Arctic Night, Lava Run, Jungle Dusk, Deep Space, Candy Land, Ice Desert
3 consumable power-ups:

🧲 Coin Magnet — attracts nearby coins for 8 seconds
🛡 Ice Shield — absorbs one fatal iceberg hit
⚡ Speed Boost — turbo speed for 5 seconds



Visual Polish

Aurora borealis, parallax star fields, and animated snowfall
Procedural mountain backgrounds with scrolling parallax
Per-skin particle effects (Galaxy trails, Firebird embers)
Camera shake on death and level-up
Speed lines at high velocity
Footprint trail on the ground
Full coin collection particle effects and floating score text
Animated sea lion character with whiskers, eyes, and open-mouth expressions


🕹️ Controls
InputActionSpace / ↑ / TapJump (hold for double jump)SOpen ShopMOpen MissionsEscapeClose panels

🚀 Getting Started
No installation required.
bash# Clone the repo
git clone https://github.com/ayuuXploits/penguin-run-hd.git

# Open in your browser
open index.html
Or just download the HTML file and open it directly — it's fully self-contained.

🏗️ Architecture
The entire game is written in vanilla HTML/CSS/JavaScript with zero dependencies.
index.html
├── Inline CSS          — UI, screens, shop, missions, animations
├── Canvas rendering    — Sky, ground, penguin, sea lion, obstacles, coins, particles
├── Game loop           — requestAnimationFrame-based, ~60fps
├── Save system         — localStorage with versioned save key
├── Mission engine      — Daily + long-term with progress tracking
└── Shop system         — Skins, sceneries, consumable power-ups



Key technical details:

Two layered <canvas> elements — main game canvas + speed lines overlay
Procedural iceberg geometry using sine-wave point generation
Skin and scenery preview rendered live onto mini canvases in the shop
All assets (fonts via Google Fonts CDN) loaded inline — no local files required


📸 Screenshots
Arctic NightLava RunDeep Space(default scenery, aurora borealis)(volcanic red sky, glowing ground)(cosmic nebulae, star field)

🔧 Customisation
Everything is data-driven. To add a new skin, append to the SKINS array:
javascript{
  id: 'myskin',
  name: 'My Skin',
  desc: 'A short description shown in the shop.',
  price: 250,
  col1: '#1a003a',   // body colour
  col2: '#ddaaff',   // belly/face patch colour
  scarf: '#ff00cc',  // scarf colour
  beak: '#ffaa00'    // beak colour
}
To add a new scenery, append to the SCENERIES array:
javascript{
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

📄 License
MIT — do whatever you like with it.
