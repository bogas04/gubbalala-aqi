# index.html Structure Documentation

Quick reference for navigating and editing the main HTML file (~1627 lines).

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

- **Total Lines:** ~1627 (will change with edits)
- **Language:** HTML with embedded CSS and JavaScript
- **Bilingual:** English + Kannada (ಕನ್ನಡ)
- **Framework:** Tailwind CSS (CDN)
- **Fonts:** Crimson Pro (serif), IBM Plex Sans/Mono, Noto Sans Kannada

## Document Structure with Markers

### Head Section (Lines 1-254)

No markers - contains meta tags, SEO, structured data, CSS

**Key CSS Classes:**

- `.data-card` - Gradient cards with border
- `.aqi-badge` - Color-coded AQI indicators (good/moderate/poor/hazardous)
- `.timeline-item` - Timeline with left border and circle marker
- `.sticky-header` - Sticky section headers with backdrop blur
- `.modal-*` - Image modal styling

### Body Content

---

#### `<!-- COMPONENT:IMAGE-MODAL:START -->`

Full-screen modal for image zoom

- Close button (top-right)
- Click-to-zoom functionality (2x scale)
- Escape key support
- IDs: `imageModal`, `modalImage`

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

**Figures:** None (just statistics)

**Find it:** `grep -n "SECTION:KEY-FINDINGS" index.html`

---

#### `<!-- SECTION:DOCUMENTED-PATTERN:START -->`

**Purpose:** Four-stage timeline of garbage burning cycle

**Structure:** Timeline with 4 stages (see below)

**Find it:** `grep -n "SECTION:DOCUMENTED-PATTERN" index.html`

##### `<!-- STAGE:1-WASTE-ACCUMULATION:START -->`

- Description + Kannada translation
- Grid layout with 2 images
- **Figures:** 1.1, 1.2
- **Images:**
  - `garbage pile in gubbalala.jpg`
  - `gubbalala-road-30-jan-2026-optimized.jpg`

##### `<!-- STAGE:2-BURNING-ACTIVITY:START -->`

- Description + Kannada translation
- Single image with caption
- **Figure:** 2
- **Images:** `garbage burning at night.jpg`

##### `<!-- STAGE:3-SMOKE-DISPERSION:START -->`

- Multi-image grid (6 photos)
- Smoke plume documentation
- **Figures:** 3.1-3.6
- **Images:** Multiple `smoke plume circled in red [1-5].jpg` + `smoke plume visible.png`

##### `<!-- STAGE:4-EVENING-NIGHT:START -->`

- Description + single image
- Community intervention example
- **Figure:** 4
- **Images:** `a tea vendor putting off fire after being asked.jpg`

---

#### `<!-- SECTION:ENVIRONMENTAL-CONTEXT:START -->`

**Purpose:** Explain winter inversion effect

**Content:**

- Scientific explanation of temperature inversion
- Two comparison cards: winter months vs other months
- Bilingual descriptions

**Figures:** None

**Find it:** `grep -n "SECTION:ENVIRONMENTAL-CONTEXT" index.html`

---

#### `<!-- SECTION:VISUAL-EVIDENCE-BEFORE-AFTER:START -->`

**Purpose:** Interactive before/after comparison

**Content:**

- Interactive comparison slider (December vs July)
- Slider implementation with mouse + touch events
- Two comparison info cards below slider

**Figures:** 5.1, 5.2

**Images:**

- `aqi 180 a smoggy day with visible smoke plumes.png` (December/polluted)
- `aqi 30 a clean day with bright sky and clouds.jpg` (July/clean)

**Component IDs:**

- `comparison-container`
- `comparison-slider`
- `comparison-overlay`

**Find it:** `grep -n "SECTION:VISUAL-EVIDENCE" index.html`

---

#### `<!-- SECTION:HEALTH-IMPACT:START -->`

**Purpose:** Document health effects and equivalencies

**Content:**

- Health equivalencies (cigarettes per day)
- Risk factors for vulnerable groups
- Two info cards + warning box
- Bilingual text

**Figures:** None

**Find it:** `grep -n "SECTION:HEALTH-IMPACT" index.html`

---

#### `<!-- SECTION:GEOLOCATION-EVIDENCE:START -->`

**Purpose:** GPS verification and location proof

**Content:**

- GPS coordinates display (12.8811°N, 77.5144°E)
- Location details card
- Embedded Google Maps iframe

**Figures:** None (embedded map)

**Find it:** `grep -n "SECTION:GEOLOCATION-EVIDENCE" index.html`

---

#### `<!-- SECTION:GOOGLE-MAPS-EVIDENCE:START -->`

**Purpose:** Third-party mapping verification

**Content:**

- Desktop AQI layer screenshots (2 images)
- Mobile screenshots (2 images: Google Maps + Apple Maps)
- Satellite overview image

**Figures:** 6.1, 6.2, 6.3, 6.4, 6.5

**Images:**

- `google maps aqi layer showing gubbala in red.png` (desktop)
- `google maps aqi layer showing gubbala in red 2.png` (desktop detail)
- `google-maps-aqi-layer-optimized.jpg` (mobile)
- `apple-maps-optimized.jpg` (mobile)
- `google maps screenshot of area.jpg` (satellite overview)

**Find it:** `grep -n "SECTION:GOOGLE-MAPS-EVIDENCE" index.html`

---

#### `<!-- SECTION:COMMUNITY-DOCUMENTATION:START -->`

**Purpose:** Show research methodology and recent evidence

**Content:**

- Documentation methods card
- Data collection period card
- **Video section:** HTML5 video player with recent footage

**Video:**

- File: `gubbalala 2 feb 2026.mp4` (18 seconds, 2.8MB)
- Caption: "Current conditions (2 Feb 2026)"
- Bilingual description

**Figures:** None (video doesn't use figure numbering)

**Find it:** `grep -n "SECTION:COMMUNITY-DOCUMENTATION" index.html`

---

#### `<!-- SECTION:COMMUNITY-COOPERATION:START -->`

**Purpose:** Local cooperation efforts and WhatsApp community

**Content:**

- Local cooperation description
- Two-column layout with images
- WhatsApp community group CTA (green gradient card)
  - Join button
  - QR code mention

**Images:**

- `burnt garbage near mantri tranquil.jpeg`
- `smoke plume visible.png`

**Find it:** `grep -n "SECTION:COMMUNITY-COOPERATION" index.html`

---

#### `<!-- SECTION:AWARENESS-ACTION:START -->`

**Purpose:** Call to action for raising awareness

**Content:**

- Blue background section
- Centered text layout
- Bilingual awareness message

**Figures:** None

**Find it:** `grep -n "SECTION:AWARENESS-ACTION" index.html`

---

#### `<!-- LAYOUT:FOOTER:START -->`

Project credits and metadata

- Project name (English + Kannada)
- Publication date
- Dark theme (slate-900 background)

---

#### `<!-- SCRIPTS:START -->`

All JavaScript code

**Functions:**

- `openModal(imgSrc, imgAlt)` - Open image in modal
- `closeModal()` - Close modal
- `toggleZoom(event)` - Toggle 2x zoom on modal image
- `updatePosition(clientX)` - Update slider position
- Event listeners for slider (mouse + touch)
- Escape key handler

---

## Figure Numbering System

| Figure Range | Section       | Content Type                 |
| ------------ | ------------- | ---------------------------- |
| 1.1-1.2      | Stage 1       | Waste accumulation photos    |
| 2            | Stage 2       | Burning activity             |
| 3.1-3.6      | Stage 3       | Smoke plume documentation    |
| 4            | Stage 4       | Community intervention       |
| 5.1-5.2      | Before/After  | Comparison images            |
| 6.1-6.5      | Maps Evidence | Desktop + mobile screenshots |
| None         | Community     | Video + general photos       |

## Image Asset Conventions

**Naming:**

- Original files: descriptive names with spaces
- Optimized files: `-optimized.jpg` suffix, kebab-case
- Max dimension: ~1080px
- Formats: JPG (photos), PNG (screenshots), MP4 (video)

**Image Integration Pattern:**

```html
<div class="cursor-pointer" onclick="openModal('path', 'alt')">
  <div class="aspect-[ratio] overflow-hidden rounded border">
    <img src="path" alt="description" class="w-full h-full object-cover" />
  </div>
  <div class="font-mono text-xs text-slate-500 mt-2">Fig. X.Y: Caption</div>
</div>
```

## Adding New Content

### Finding the Right Section

```bash
# List all sections
grep -n "<!-- SECTION:" index.html

# Find specific section to add content
grep -n "SECTION:HEALTH-IMPACT" index.html
```

### Adding New Images

1. **Optimize:** Resize to 1080p, compress
2. **Find section:** Use grep with marker name
3. **Add to grid:** Copy existing image block pattern
4. **Update figure numbers:** Increment sequentially within section
5. **Add onclick:** Include modal functionality `onclick="openModal(src, alt)"`

### Adding New Video

1. **Find marker:** `grep -n "SECTION:COMMUNITY-DOCUMENTATION" index.html`
2. **Format:** HTML5 `<video>` tag with controls
3. **Include:** Source tag, caption, bilingual description
4. **Pattern:**

```html
<video controls class="w-full" preload="metadata">
  <source src="images/filename.mp4" type="video/mp4" />
  Your browser does not support the video tag.
</video>
```

### Adding New Section

1. **Location:** Before `<!-- SECTION:AWARENESS-ACTION:START -->`
2. **Add marker:** `<!-- SECTION:NEW-SECTION-NAME:START -->`
3. **Include:** Sticky header with bilingual titles
4. **Wrapper:** `<section class="mb-20">`
5. **Update this doc:** Add new section to marker list

### Adding New Stage to Timeline

1. **Find:** `grep -n "STAGE:4-EVENING-NIGHT" index.html`
2. **Add after Stage 4:** Before closing of DOCUMENTED-PATTERN section
3. **Marker:** `<!-- STAGE:5-NEW-STAGE:START -->`
4. **Structure:** Copy existing stage pattern
5. **Update figures:** Continue numbering (would be Figure 5)

## Interactive Components

### Image Modal (Global)

- **Activation:** `onclick="openModal(src, alt)"`
- **Features:** Click-to-zoom (2x scale), close button, ESC key
- **IDs:** `imageModal`, `modalImage`
- **Find it:** `grep -n "COMPONENT:IMAGE-MODAL" index.html`

### Comparison Slider

- **Location:** VISUAL-EVIDENCE-BEFORE-AFTER section
- **Features:** Mouse drag, touch support, click-to-jump
- **IDs:** `comparison-container`, `comparison-slider`, `comparison-overlay`
- **Technology:** CSS clip-path on overlay image

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
