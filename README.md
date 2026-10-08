# 📜 Memory Lane — Personal Digital Memory Book & Keepsake

> *"Some moments become memories. Some memories become treasures."*

**Memory Lane** is an emotional, nostalgic, and premium digital memory book built to preserve, organize, and relive life's most cherished moments — through photographs, motion videos, handwritten reflections, and chronological milestones.

---

## ✨ Features Overview

### 1. 🎞️ Cinematic First-Time Experience
- **Opening the Memory Box**: On first launch, users are greeted by an ethereal memory box animation with floating polaroids, evocative titles, and a transition into their digital keepsake.
- **Replay anytime**: The memory box sequence can be re-experienced anytime from the navigation menu.

### 2. 🎨 8 Radical Immersive Themes
Change the entire sensory atmosphere of the application with one click:
1. **Vintage Memories**: Warm cream, sepia tones, paper textures, polaroid frames, and classic serif storytelling.
2. **Modern Minimal**: Architectural white & jet black, generous whitespace, razor-thin strokes, and clean typography.
3. **Dark Cinema**: Midnight obsidian and glowing amber neon, widescreen letterbox aspect ratios, and moody backdrop blurs.
4. **Physical Scrapbook**: Craft notebook paper, tilted polaroid cards (`rotate(-1.4deg)`, `rotate(1.2deg)`), washi tape strips, doodle stickers, and handwritten cursive fonts (*Caveat* & *Kalam*).
5. **Dreamy Horizon**: Ethereal pastel gradients (lavender, rose, celestial blue), frosted glassmorphism (`backdrop-filter: blur(14px)`), and glowing accents.
6. **Analog Film Roll**: 35mm film strip sprockets, darkroom charcoal, retro orange date stamp counters (`'22 10 14`), and typewriter monospace.
7. **Royalty & Luxury**: Regal onyx black, brushed metallic champagne gold foil borders, and high-fashion Roman serif typography (*Cinzel*).
8. **Nature & Solitude**: Organic curved cards, forest moss green, sage tones, and earthy terracotta warmth.

*All themes persist in `localStorage` across page reloads and browser sessions.*

### 3. 📅 Interactive Vertical Timeline
- Chronological timeline spanning 2018–2025+ with central glowing year nodes.
- **Year Jump Bar**: Quick jump pills (`2018`, `2020`, `2022`, `2024`, etc.) with smooth scrolling directly to that era.
- Detailed story cards with date badges, media thumbnails, and pull-quotes.

### 4. 🕯️ "On This Day" Time Capsule
- Dynamic anniversary engine that matches today's date against previous years (e.g. *"On this day, 5 years ago..."*).
- Displays evocative quotes, location, and a quick-action button to relive the memory.

### 5. 🔍 Multi-Facet Search & Dynamic Filtering
- Full-text search across **Title**, **Description**, **Location**, **Tags**, and **People**.
- Filter pills by category: *Childhood*, *School*, *College*, *Friends*, *Family*, *Travel*, *Festivals*, *Birthdays*, *Achievements*, *Special Moments*.
- Filter by media type: *All Media*, *Photos only*, *Videos only*.
- Filter by *Favorites* and specific *Albums*.

### 6. 🖼️ Full-Screen Memory Viewer & Slideshow
- High-resolution photo and video presentation stage.
- **Photo Controls**: Zoom In, Zoom Out, Download, and Fullscreen.
- **Slideshow Mode**: Auto-advances across photos and memories with smooth transitions.
- Story drawer with tagged companions, tags, dates, and locations.
- **Safe Delete Confirmation Modal** & direct editing.

### 7. 📖 Memory Storyteller Mode & Keepsake Export
- Reads like a chapter in a personal memoir.
- Large hero photography with pull-quotes, complete narratives, and companion credits.
- **Print Keepsake**: One-click print-optimized digital keepsake export to PDF or physical paper.

### 8. 🎥 Dedicated Video Vault
- Custom cinema video player cards featuring:
  - Play / Pause with center play overlay
  - Custom progress seek bar and live timecode
  - Volume mute/unmute
  - Native fullscreen trigger

### 9. 🎵 Nostalgic Ambient Audio Synthesizer
- Built using browser-native **Web Audio API** (zero heavy external audio files needed).
- Plays gentle, soothing, warm arpeggiated piano/celesta chords in pentatonic major.
- Can be toggled on/off in the header or inside Story Mode.

### 10. ✨ Surprise Random Memory
- "Show Me a Random Memory" button in the top bar.
- Triggers a celebratory confetti explosion and presents a forgotten memory to relive.

---

## 🛠️ Project Architecture

```
MEMORY PROJECT/
├── client/                     # Frontend (Vite + React 19)
│   ├── src/
│   │   ├── components/         # Modular React components
│   │   │   ├── Navbar.jsx
│   │   │   ├── HeroExperience.jsx
│   │   │   ├── StatsBar.jsx
│   │   │   ├── OnThisDayBanner.jsx
│   │   │   ├── FilterBar.jsx
│   │   │   ├── MemoryCard.jsx
│   │   │   ├── MemoryViewerModal.jsx
│   │   │   ├── MemoryDetailModal.jsx
│   │   │   ├── AddMemoryModal.jsx
│   │   │   ├── TimelineView.jsx
│   │   │   ├── AlbumsView.jsx
│   │   │   ├── VideosView.jsx
│   │   │   ├── ThemeGalleryModal.jsx
│   │   │   ├── StoryModeModal.jsx
│   │   │   ├── RandomMemoryModal.jsx
│   │   │   ├── ConfirmDialog.jsx
│   │   │   ├── Toast.jsx
│   │   │   └── Footer.jsx
│   │   ├── styles/
│   │   │   ├── index.css       # Core layout, reset, animations
│   │   │   └── themes.css      # Complete 8 physical theme systems
│   │   ├── services/
│   │   │   ├── api.js          # REST client with offline caching
│   │   │   └── audio.js        # Web Audio ambient chord synth
│   │   ├── App.jsx             # Main application orchestrator
│   │   └── main.jsx
│   ├── index.html
│   ├── vite.config.js          # Vite config + Express proxy
│   └── package.json
│
├── server/                     # Backend (Node.js + Express + Multer)
│   ├── data/                   # JSON persistence directory
│   │   ├── memories.json       # Seed & user saved memories
│   │   └── albums.json         # Seed & user saved albums
│   ├── uploads/                # Disk directory for uploaded media files
│   ├── db.js                   # Database layer & rich seed data
│   ├── index.js                # Express REST API & static file server
│   └── package.json
│
├── package.json                # Root package scripts
├── start-dev.js                # Unified concurrent runner
└── README.md                   # Documentation
```

---

## 🚀 Getting Started

### 1. Prerequisites
- **Node.js** v18+ (verified with Node.js v20)
- **npm** v9+

### 2. Quick Start (Run Both Frontend & Backend)

From the project root:
```bash
npm run dev
```
This automatically starts:
- **Backend API**: `http://localhost:5001`
- **Frontend App**: `http://localhost:3000`

Open `http://localhost:3000` in your browser.

---

### 3. Running Services Independently

#### Start Backend Only:
```bash
npm run server
# or: cd server && npm start
```

#### Start Frontend Only:
```bash
npm run client
# or: cd client && npm run dev
```

---

## 💾 Uploading Media & Data Persistence

1. **Local File Uploads**: Click `+ Add Memory` and drop your photos/videos into the upload box. Files are uploaded via `Multer` to `server/uploads/` and served as `/uploads/<timestamp>-<filename>`.
2. **Web URL Uploads**: You can also paste public image/video links (e.g. Unsplash, Cloudinary, YouTube mp4 streams).
3. **Database**: Memories and albums are persisted in `server/data/memories.json` and `server/data/albums.json`. Any addition, edit, or deletion is immediately saved to disk and will remain intact across restarts.
4. **Offline Resilience**: The client stores a fallback snapshot in `localStorage` so memories remain accessible even if the server is temporarily stopped.

---

## 🌐 Production Deployment

### Build the Frontend Bundle:
```bash
npm run build
```
This produces optimized production assets in `client/dist/`.

### Serve in Production:
You can serve the static frontend directly with the Express backend by adding static serving of `client/dist` in `server/index.js`, or deploy the frontend to Vercel/Netlify and the backend to Render, Railway, or AWS.
