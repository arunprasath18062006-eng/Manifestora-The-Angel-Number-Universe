# 🌌 MANIFESTORA — The Angel Number Universe

A fully animated, creative React frontend for manifestation + angel numbers.
Your hero image is baked in, everything runs client-side with `localStorage` —
no backend needed.

## Features

**Original set**
- **Cosmic hero** — your uploaded galaxy image, shimmering title, slow parallax drift, and mouse-move 3D parallax layers
- **Today's Universe** — a date-seeded daily angel number draw + a real moon-phase widget
- **Manifestation Portal** — pick an intention (wealth, love, career...) and get routed to its angel number
- **Angel Number Galaxy** — 8 core numbers as glowing star cards, each opens a full "universe" modal with meaning, intention, a journal textarea, mood tagging, text-to-speech, a guided breathing timer, and a downloadable share card (canvas-generated PNG)
- **Future Vision Pathway** — 111 → 333 → 555 → 888 visual journey
- **Custom Number Themes** — add your own number + affirmation; shows as a dashed "your number" tile
- **Manifestation Wheel** — a spinning cosmic fortune wheel across all 8 numbers
- **My Manifestation Galaxy (Constellation Map)** — add goals as stars on a canvas; raise their progress and watch them evolve small star → glowing star → supernova → and finally connect into **Your Dream Constellation** once complete
- **Compatibility Checker** — type two numbers, get a resonance % ring + reading
- **Cosmic Dashboard** — "I Saw This Number" tracker with bar chart, most-seen number, manifestation streak, and a 7-day weekly reflection strip
- **Sound Toggle** — ambient cosmic drone generated live with the Web Audio API (no audio files)
- **Dark / Light mode**
- **Multi-Profile** — switch or create profiles from the nav; each profile has its own galaxy, journal, goals, and tracker history (all scoped in `localStorage`)

**New in this round**
- **Cosmic Profile** — Life Path Number + Name Numerology calculator, plus a Zodiac reading with a mini procedural constellation
- **Daily Tarot** — a flip-card cosmic draw, one per day
- **Achievement Badges** — 11 unlockable badges tied to real activity (streaks, goals, journaling, etc.)
- **XP & Levels** — a level bar in the nav that fills as you journal, spin, draw cards, and complete goals
- **Daily Challenges** — a rotating checklist with its own XP rewards
- **Journal Timeline** — every journal entry across every number, in one chronological feed, with mood emoji
- **Export Panel** — download a full JSON backup, or a proper PDF summary (via `jspdf`)
- **Share Universe** — generates a read-only link (state encoded in the URL, no server) showing your goals, badges, and level; opening it renders a dedicated read-only view
- **Community Pulse** — a simulated "trending numbers this week" feed
- **Daily Reminder** — opt-in browser notification with today's number
- **Tamil / English toggle** — flip the whole UI's language from the nav
- **PWA support** — installable, with a manifest, icons, and an offline app-shell service worker

**Latest round: Sound, Calendar, Deeper Goals, Multiplayer & Mobile**
- **Ambient scene picker** — choose Deep Space drone, Rain, or Ocean (all generated live, no audio files), switchable from a popover on the sound icon
- **Number-specific tones** — each angel number plays its own solfeggio-style frequency when you open its universe
- **Manifestation Calendar** — a real month view highlighting days you journaled or visited, with goal target dates marked
- **Export to Calendar (.ics)** — download your goal deadlines as a calendar file, or export a single goal's date from its row
- **Goal Milestones** — expand any goal-star to add a checklist of sub-steps
- **Urgency glow** — goals with a target date within 7 days pulse with a warning glow until completed
- **Vision Board Mode** — a toggle next to the constellation view that lays goals out as a photo-collage-style grid with progress rings
- **Manifestation Buddy** — a simulated daily message from someone else "manifesting" alongside you, matched to one of your goal types
- **Compare Constellations** — pick any two profiles on this device and see their goals, level, and badges side by side
- **Mobile polish** — swipe-to-browse star cards on small screens, swipe-down-to-close on the number modal, and haptic vibration on wheel spins and goal completions (where supported)

**Latest: Login Screen & Entrance Transition**
- **Login / entrance screen** — the very first thing you see. A fully animated galaxy (rotating spiral arms, drifting nebula clouds, twinkling stars, orbiting ringed planets, occasional shooting stars — all live canvas, no static image) sits behind a sign-in card
- Type a name to create a new profile, or tap an existing profile chip to continue theirs
- **"Flying through clouds" transition** — tapping "Enter the Universe" plays a full-screen warp: streaking light lines + soft glowing cloud puffs rushing past the camera, then fades straight into the app

## Getting started

```bash
npm install
npm run dev
```

Then open the printed local URL (usually `http://localhost:5173`).

To build for production:

```bash
npm run build
npm run preview
```

## Tech

Plain React 18 + Vite. No UI framework — almost every animation is hand-written
CSS (`@keyframes`) or Canvas/Web Audio/Web Speech, so there's very little to
install: just `react`, `react-dom`, and `jspdf` (only used for the optional PDF
export). All state persists per-profile in `localStorage`; nothing leaves the
browser except the one PDF/JSON export the person triggers themselves, and the
optional share link (which only ever encodes goals/badges/level — never
journal text).

## Project structure

```
src/
  App.jsx                Wires all sections + global state together
  App.css                All component styling
  index.css               Design tokens, resets, shared keyframes
  assets/hero.jpg          Your uploaded hero image
  data/angelNumbers.js     Number meanings, goal → number mapping
  utils/                   storage, moon phase, ambient audio, persistence hook
  components/              One component per section
```

Enjoy your universe ✦
