# Site Redesign — Design Spec
**Date:** 2026-04-19  
**Project:** gamify-with-octalysis  
**Status:** Approved

---

## Overview

Redesign the single-page reference site into two distinct destinations:

- **Learn page** (`/index.html`) — editorial, light, for reading the framework
- **Playground page** (`/playground.html`) — dark, interactive, for experiencing the drives live

Both pages share a nav that links between them. Users self-select based on their goal: understand the theory or feel it in action.

---

## Visual System

### Learn page — Editorial Light
- **Background:** `#F2F5F9` (keep current)
- **Surface:** `#FFFFFF`
- **Font:** Inter or `system-ui, -apple-system, sans-serif`
- **Heading weights:** 800–900, tight tracking (`letter-spacing: -0.03em` to `-0.05em`)
- **Body:** `0.93rem`, `line-height: 1.75`, color `#374151`
- **Drive colors:** used as left-border accents on cards only, not as backgrounds
- **Hat/Brain axes:** inline tags on each drive card header — no separate sections

### Playground page — Dark Gaming
- **Background:** `#0d1117`
- **Surface:** `#161b22`
- **Border:** `#30363d`
- **Font:** same typeface, dark palette
- **Drive colors:** vibrant, full saturation with glow effects (`box-shadow: 0 0 12px color`)
- **Active drive segment:** glows with a ring at full opacity; others dim to 20%

### Drive color palette (unchanged)
| Drive | Color | Light bg | Dark text |
|-------|-------|----------|-----------|
| CD1 Epic Meaning | `#F59E0B` | `#FFFBEB` | `#92400E` |
| CD2 Accomplishment | `#3B82F6` | `#EFF6FF` | `#1E40AF` |
| CD3 Creativity | `#8B5CF6` | `#F5F3FF` | `#4C1D95` |
| CD4 Ownership | `#10B981` | `#ECFDF5` | `#064E3B` |
| CD5 Social | `#EC4899` | `#FDF2F8` | `#831843` |
| CD6 Scarcity | `#F97316` | `#FFF7ED` | `#7C2D12` |
| CD7 Curiosity | `#06B6D4` | `#ECFEFF` | `#0E7490` |
| CD8 Loss | `#EF4444` | `#FEF2F2` | `#7F1D1D` |

---

## Learn Page (`index.html`)

### Navigation
- Sticky, slim, light background
- Left: `Octalysis` logo pill (purple, `#8B5CF6`)
- Center: `Core Drives` · `Apply` · `About` text links, active underline in purple
- Right: `🎮 Playground` dark pill button (links to `/playground.html`)

### Hero Section
- Two-column layout: text left, octagon SVG right
- Gradient title: `The Octalysis Framework` with multi-color gradient on "Octalysis"
- Subtitle: one sentence value prop
- No CTA buttons — the scroll is the journey

### Quick Reference Grid
- Immediately below hero
- 4×2 grid of compact drive tiles
- Each tile: drive color as left border + light tinted background, icon, CD number, short name
- For returners who need a fast reminder without scrolling all 8 cards

### Deep Dive — Drive Cards (scrolling)
- One card per drive, full editorial treatment
- **Card anatomy:**
  - Header: colored left border (4px), CD badge (colored pill), drive name (800 weight), hat + brain inline tags, icon right-aligned
  - Body: description paragraph, 2×2 examples grid (product + technique chip + body text), techniques row, designer tip callout
- Sticky octagon sidebar (right column, `position: sticky`) — click segment to jump to that drive's card, highlights active drive as you scroll
- Hat and Brain axes removed as separate page sections — fully replaced by inline tags

### How to Apply Section
- Kept as-is, 3-step editorial cards

### About / Attribution Section
- Kept as-is

### Footer
- Framework credit, MIT license, GitHub link

---

## Playground Page (`playground.html`)

### Navigation
- Sticky, dark (`#161b22`)
- Left: `Octalysis` logo pill (purple tint on dark)
- Right: `📖 Learn` light pill (links back to `/index.html`) · `🎮 Playground` active label

### Hero
- Centered, minimal
- Headline: "Experience the Drives"
- Subtitle: "Click a segment on the octagon to activate a drive demo"

### 3-Panel Octagon Hub (main UI)
The entire playground interaction lives in one persistent 3-panel layout:

```
[ Description panel ] [ Octagon ] [ Live Demo panel ]
```

**Octagon states:**
- **Default:** all segments at 20% opacity, center label "CLICK"
- **Hover:** hovered segment brightens to 100%, cursor pointer, drive name tooltip
- **Active (clicked):** segment at 100% + glow ring in drive color; all others at 20%; left and right panels fade in with that drive's content

**Left panel — Description:**
- Section label: "FRAMEWORK ITEM"
- CD number (large, drive color)
- Drive name (bold, white)
- 2–3 sentence description connecting the concept to what the demo shows
- Hat + Brain inline tags (dark palette versions)
- Divider + "→ Read full description" link (routes to `/index.html#drive-N`)

**Right panel — Live Demo:**
- Section label: "LIVE DEMO"
- Demo title
- Interactive widget (see demos below)

### The 8 Demos

| Drive | Demo | Key Interaction |
|-------|------|-----------------|
| CD1 Epic Meaning | **Mission Counter** | Globe icon, animated counter of community members by role, "Add Your Voice" increments count with pulse animation |
| CD2 Accomplishment | **XP Level-Up** | Level badge, XP progress bar (gradient, glow), task checklist — check tasks to earn XP, fill bar to 1000 triggers level-up: panel background shifts to purple gradient, level name updates to "Level 4", no separate modal |
| CD3 Creativity | **Combo Builder** | Tag cloud of gamification techniques, pick 2–3 to get instant "combo name + effect" feedback showing different combinations = different outcomes |
| CD4 Ownership | **Passport Stamps** | 4×2 stamp grid, claimed drives show as glowing colored stamps with texture overlay, uncollected are dashed/grey, progress bar tracks 0–8 collected (persists in localStorage) |
| CD5 Social | **Live Pulse** | Simulated scrolling activity feed — animated dots + "12 people exploring CD7", "A designer in Berlin just earned Level 4" style messages |
| CD6 Scarcity | **Event Ticket** | Ticket UI with gradient top border, live countdown timer, filled/empty seat holes (3 of 5 taken), "Claim Spot" fills a hole and confirms |
| CD7 Curiosity | **Scratch Card** | Textured scratch overlay with coin icon, click/scratch to reveal a random Octalysis technique (from pool of ~10), "↺ Scratch another" resets with a new one |
| CD8 Loss Avoidance | **Streak Tracker** | 🔥 fire icon with pulsing "⚠️ At risk" badge, 7-day week grid (5 filled, today dashed-red, tomorrow grey), "Keep My Streak" fills today green and updates warning text |

### Footer (Playground)
- Minimal: framework credit + "📖 Read the full framework →" link

---

## File Structure

```
site/
  index.html        ← Learn page (refactored from current single file)
  playground.html   ← New Playground page
```

No build step. Both files are vanilla HTML/CSS/JS, self-contained. GitHub Pages serves both at their natural paths.

---

## What Gets Removed

- Separate **White Hat / Black Hat section** — replaced by inline tags on each card
- Separate **Left Brain / Right Brain section** — replaced by inline tags on each card
- The existing single-page architecture — replaced by the two-page structure above

---

## What Gets Kept

- All 8 drive descriptions, examples, techniques, and designer tips (content unchanged)
- The attribution / about section (Learn page)
- The How to Apply section (Learn page)
- The sticky octagon sidebar in the deep-dive scroll (Learn page)
- The existing drive color tokens
- GitHub Actions deploy workflow (no changes needed — `./site` directory still deploys)
- `.gitignore`, `CONTRIBUTING.md`, `ATTRIBUTION.md`, `README.md` (unchanged)
