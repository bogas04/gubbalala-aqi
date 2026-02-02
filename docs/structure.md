# index.html Structure Documentation

Quick reference for navigating and editing the main HTML file (~1900 lines).

## Navigation Strategy

**Use grep to find sections instantly:**

```bash
# Find all section markers
grep -n "<!-- SECTION:" index.html

# Find specific section
grep -n "SECTION:HEALTH-IMPACT" index.html

# Find all stages
grep -n "<!-- STAGE:" index.html

# Find layout elements
grep -n "<!-- LAYOUT:" index.html

# Find components
grep -n "<!-- COMPONENT:" index.html
```

## Marker Convention

All markers follow the pattern: `<!-- TYPE:NAME:START -->`

**Types:**

- `LAYOUT:` - Major page structure (header, main, footer)
- `SECTION:` - Content sections within main
- `STAGE:` - Timeline stages within documented pattern
- `COMPONENT:` - Reusable UI components
- `SCRIPTS:` - JavaScript code block

## File Overview

- **Total Lines:** ~1900 (will change with edits)
- **Language:** HTML with embedded CSS and JavaScript
- **Bilingual:** English + Kannada (ಕನ್ನಡ)
- **Framework:** Tailwind CSS (CDN)
- **Fonts:** Crimson Pro (serif), IBM Plex Sans/Mono, Noto Sans Kannada
- **Interactivity:** View Transitions API for image modals

## Document Structure with Markers

### Head Section

No markers - contains meta tags, SEO, structured data, CSS

**Key CSS Classes:**

- `.data-card` - Gradient cards with border
- `.aqi-badge` - Color-coded AQI indicators (good/moderate/poor/hazardous)
- `.timeline-item` - Timeline with left border and circle marker
- `.sticky-header` - Sticky section headers with backdrop blur
- `::view-transition-*` - View Transitions API configuration for smooth modal animations

### Body Content

---

#### `<!-- COMPONENT:IMAGE-MODAL:START -->`

Full-screen modal for image zoom with View Transitions support

- Close button (top-right)
- Click-to-zoom functionality (2x scale) with `toggleZoom`
- Escape key support
- IDs: `imageModal`, `modalImage`
- Implements `view-transition-name: modal-image` dynamically via JS to avoid duplicate name errors

---

#### `<!-- LAYOUT:HEADER:START -->`

Main page header

- Investigation label + metadata (date, location, GPS)
- H1 title (English + Kannada)
- Summary paragraph with bilingual text

---

#### `<!-- LAYOUT:MAIN:START -->`

Main content container - all sections below are within this

### Content Sections

---

#### `<!-- SECTION:KEY-FINDINGS:START -->`

**Purpose:** Opening statistics and investigation summary

**Content:**

- Three data cards: AQI range (30→200), cigarette equivalent (~6), frequency (daily)
- Investigation summary text (English + Kannada)

**Figures:** None

**Find it:** `grep -n "SECTION:KEY-FINDINGS" index.html`

---

#### `<!-- SECTION:DOCUMENTED-PATTERN:START -->`

**Purpose:** Four-stage timeline of garbage burning cycle

**Structure:** Timeline with 4 stages (see below)

**Find it:** `grep -n "SECTION:DOCUMENTED-PATTERN" index.html`

##### `<!-- STAGE:1-WASTE-ACCUMULATION:START -->`

- Description + Kannada translation
- Grid layout with image
- **Figure:** 1.1
- **Image:** `garbage pile in gubbalala.jpg`

##### `<!-- STAGE:2-BURNING-ACTIVITY:START -->`

- Description + Kannada translation
- Grid layout with 2 images
- **Figures:** 2.1, 2.2
- **Images:**
  - `burnt garbage near mantri tranquil.jpeg`
  - `gubbalala-road-30-jan-2026-optimized.jpg`

##### `<!-- STAGE:3-SMOKE-DISPERSION:START -->`

- Multi-image grid (6 photos)
- **Figures:** 3.1-3.6
- **Dates:** August 2025 – January 2026 (spread to show persistence)
- **Images:** Multiple `smoke plume circled in red [1-5].jpg` + `smoke plume visible.png`

##### `<!-- STAGE:4-EVENING-NIGHT:START -->`

- Night activity documentation
- Grid with image and video
- **Figures:** 4.1, 4.2
- **Media:**
  - Image: `garbage burning at night.jpg`
  - Video: `night burning of garbage with visible fire.mp4`

---

#### `<!-- SECTION:ENVIRONMENTAL-CONTEXT:START -->`

**Purpose:** Explain winter inversion effect

**Content:**

- Scientific explanation (bilingual)
- Comparison cards: Summer vs Winter conditions

---

#### `<!-- SECTION:VISUAL-EVIDENCE-BEFORE-AFTER:START -->`

**Purpose:** Interactive before/after comparison

**Content:**

- Interactive comparison slider (December vs July)
- AQI Comparison info cards (180 vs 30)

---

#### `<!-- SECTION:HEALTH-IMPACT:START -->`

**Purpose:** Document health effects

---

#### `<!-- SECTION:GEOLOCATION-EVIDENCE:START -->`

**Purpose:** GPS verification

---

#### `<!-- SECTION:GOOGLE-MAPS-EVIDENCE:START -->`

**Purpose:** Third-party mapping verification

**Figures:** 6.1, 6.2, 6.3, 6.4, 6.5

---

#### `<!-- SECTION:COMMUNITY-DOCUMENTATION:START -->`

**Purpose:** Research methodology documentation

---

#### `<!-- SECTION:ONGOING-EVIDENCE:START -->`

**Purpose:** Live/recent evidence feed (Investigative theme)

**Content:**
- Standalone section with amber theme for active monitoring.
- Field Report cards (e.g., FIELD REPORT #001).
- **Recent Video:** `gubbalala 2 feb 2026.mp4` integrated into the report feed.

**Find it:** `grep -n "SECTION:ONGOING-EVIDENCE" index.html`

---

#### `<!-- SECTION:COMMUNITY-COOPERATION:START -->`

**Purpose:** Local cooperation efforts and community action

**Content:**

- Individual action documentation (Tea vendor)
- Grid with image and video
- **Figures:** 5.1, 5.2
- **Media:**
  - Image: `a tea vendor putting off fire after being asked.jpg`
  - Video: `tea vendor putting off fire upon request.mp4`
- WhatsApp community group CTA

---

#### `<!-- SECTION:AWARENESS-ACTION:START -->`

---

#### `<!-- LAYOUT:FOOTER:START -->`

---

#### `<!-- SCRIPTS:START -->`

All JavaScript code

**Key Functions:**

- `openModal(imgSrc, imgAlt, event)` - Open image with View Transitions and cleanup.
- `closeModal()` - Close modal with View Transitions.
- `toggleZoom(event)` - Toggle 2x zoom.
- `updatePosition(clientX)` - Interactive comparison slider logic.

---

## Figure Numbering System

| Figure Range | Section                | Content Type                    |
| ------------ | ---------------------- | ------------------------------- |
| 1.1          | Stage 1                | Waste accumulation              |
| 2.1-2.2      | Stage 2                | Burning activity evidence       |
| 3.1-3.6      | Stage 3                | Smoke plume (Aug 25 - Jan 26)   |
| 4.1-4.2      | Stage 4                | Evening/Night activity (+Video) |
| 5.1-5.2      | Community Cooperation  | Engagement evidence (+Video)    |
| 6.1-6.5      | Google Maps Evidence   | Third-party verification        |
| FIELD REPORT | Ongoing Evidence       | Field records for new sightings |

## Interactive Components

### Image Modal (Global)

- **Activation:** `onclick="openModal(src, alt, event)"`
- **Animation:** Uses CSS View Transitions API.
- **Cleanup:** Script removes `view-transition-name` after animations to prevent duplicate name errors.

### Comparison Slider

- **Location:** VISUAL-EVIDENCE-BEFORE-AFTER
- **Technology:** CSS `clip-path` and absolute positioning.

## Styles & Theming

- **Primary Colors:** Teal (`#1a5f7a`), Orange (`#d97706`)
- **Ongoing Section:** Amber (`#f59e0b`) background for high importance.
- **Timeline:** Slate borders with teal markers.

## Styling Reference

**Color Variables (in CSS):**

- `--color-primary`: #1a5f7a (teal)
- `--color-accent`: #d97706 (orange)
- `--color-good`: #059669 (green)
- `--color-moderate`: #f59e0b (amber)
- `--color-poor`: #dc2626 (red)

**Responsive:**

- `md:` prefix for tablet/desktop (768px+)
- Mobile-first approach

**Custom Classes:**

- `.data-card` - Stats cards with gradient
- `.aqi-badge` - Color-coded AQI indicators
- `.timeline-item` - Timeline with marker
- `.sticky-header` - Sticky section headers
- `.img-documentary` - Documentary photo styling
- `.img-evidence` - Evidence photo styling

## SEO & Metadata Updates

When changing content, update:

- **Line ~13:** Meta description
- **Line ~18:** Meta keywords
- **Line ~30:** OG title/description
- **Line ~68:** JSON-LD structured data
- **Line ~287:** Publication/modification date in header

**Find metadata:**

```bash
grep -n "meta name=\"description\"" index.html
grep -n "og:description" index.html
grep -n "dateModified" index.html
```

## Common Edit Patterns

### Update AQI Statistics

```bash
grep -n "SECTION:KEY-FINDINGS" index.html
# Edit the data-card divs with new numbers
```

### Add New Timeline Stage

```bash
grep -n "STAGE:4-EVENING-NIGHT" index.html
# Add after this, before section close
```

### Update Video

```bash
grep -n "gubbalala 2 feb 2026.mp4" index.html
# Replace src attribute
```

### Modify WhatsApp Link

```bash
grep -n "WhatsApp Community Group" index.html
# Find the anchor tag below
```

### Change Coordinates

```bash
grep -n "SECTION:GEOLOCATION-EVIDENCE" index.html
# Update GPS coordinate displays
```

## Quick Reference Commands

```bash
# List all markers
grep "<!-- [A-Z]*:" index.html

# Find by marker type
grep "<!-- SECTION:" index.html
grep "<!-- STAGE:" index.html
grep "<!-- LAYOUT:" index.html
grep "<!-- COMPONENT:" index.html

# Count total sections
grep -c "<!-- SECTION:" index.html

# Find images
grep "src=\"images/" index.html

# Find figures
grep "Fig\." index.html

# Find bilingual content
grep "kannada" index.html
```
