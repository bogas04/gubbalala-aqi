# Gubbalala Garbage Burning Crisis | ಗುಬ್ಬಳಾಳ ಕಸ ಸುಡುವ ಬಿಕ್ಕಟ್ಟು

A documentary-style awareness campaign about illegal garbage burning causing severe air pollution in Gubbalala, Bengaluru. Designed for QR code distribution on physical awareness posters.

**Live Site:** https://bogas04.github.io/gubbalala-aqi

## The Problem

Gubbalala experiences dramatic seasonal air quality variation:

- **Summer/Monsoon (July):** AQI 30 - Clean air
- **Winter (December):** AQI 180-200 - Hazardous (equivalent to smoking 6 cigarettes per day)

The cause: systematic illegal garbage burning in open areas, trapped by winter's cold, dry air.

## Key Features

### Documentary Evidence

- **4-Step Visual Narrative:** Garbage Burn Cycle from accumulation to night operations
- **Photo Documentation:** 10+ evidence photos including smoke plumes, burning sites, and night operations
- **Image Comparison Slider:** Interactive July vs December AQI comparison using clip-path technique
- **Google Maps Verification:** External data showing Gubbalala as red zone
- **Community Response:** Video and photo evidence of local action

### Awareness Focus

**This page is NOT about:**

- Technical AQI monitoring dashboards
- Personal protective measures
- Individual action recommendations

**This page IS about:**

- Documenting the systematic nature of the problem
- Creating undeniable visual proof
- Building community awareness
- Encouraging collective action (reporting to authorities, MLA/MP contact)

## Design Philosophy

"Toxic Industrial Documentary" aesthetic:

- Bold, brutalist typography (Bebas Neue, Space Mono, Oswald, Anton)
- High-contrast color palette (toxic ambers, warning reds, smog grays)
- Film grain overlay animation
- Evidence file numbering system
- Bilingual presentation (English/Kannada)

## Content Sections

1. **Header:** Location coordinates, critical status alert
2. **The Garbage Burn Cycle:** 4-step visual narrative
3. **Winter Trap:** Environmental factors explanation
4. **Health Toll:** AQI 200 = 6 cigarettes messaging
5. **The Proof:** Interactive image comparison (July vs December)
6. **Google Maps Evidence:** External verification
7. **When We Speak Up:** Community response case study
8. **Call to Action:** Document & Share protocol (4 steps including contacting authorities)
9. **WhatsApp Group:** Coming soon section for community organization

## Technical Details

### Built With

- HTML5
- Tailwind CSS (CDN)
- Vanilla JavaScript (image modal, comparison slider)
- Google Fonts: Bebas Neue, Space Mono, Noto Sans Kannada, Anton, Oswald

### SEO Optimization

- Comprehensive meta tags (title, description, keywords)
- Open Graph tags for social sharing
- Twitter Card support
- Structured data (JSON-LD) with Article schema
- Geo-location metadata (12.8811°N, 77.5144°E)
- Canonical URL
- Bilingual language tags

### Interactive Features

- **Image Comparison Slider:** Custom vanilla JS implementation using CSS clip-path (inspired by react-compare-slider)
- **Image Modal:** Click to view full-screen with 2x zoom capability
- **Responsive Design:** Mobile and desktop optimized
- **Film Grain Effect:** Animated SVG noise overlay

### Accessibility

- Minimum 14px font size (text-sm) for readability
- High contrast color schemes
- Semantic HTML structure
- Alt text on all images
- Keyboard navigation support

## Location Information

**Coordinates:** 12.881130165307516, 77.51440570677094  
**Area:** Gubbalala, Bengaluru, Karnataka, India

## Deployment

Currently deployed at: **https://bogas04.github.io/gubbalala-aqi**

### GitHub Pages Setup

1. Push to GitHub repository
2. Settings → Pages
3. Source: `main` branch, root (`/`)
4. Site automatically builds and deploys

### QR Code Generation

Generate QR codes from the live URL for poster distribution.

## Local Development

No build process required:

```bash
# Simply open in browser
open index.html

# Or use any local server
python -m http.server 8000
```

## Image Assets

All evidence photos stored in `/images/` directory:

- Garbage accumulation photos
- Burnt waste evidence
- 6x smoke plume images
- Night burning operations
- AQI comparison photos (July clean vs December smoggy)
- Google Maps screenshots
- Community action photos

Images optimized to 1080p maximum resolution using macOS `sips` command.

## Future Plans

- WhatsApp community group link (coming soon)
- Additional video evidence integration
- Multilingual expansion beyond English/Kannada
- PDF evidence compilation download

## Contributing

This is a community awareness project. Contributions welcome:

- Additional photo evidence
- Translation improvements
- Code optimization
- Accessibility enhancements

## License

This is an awareness campaign project for public benefit.

## Contact

For community involvement and reporting evidence, join the WhatsApp group (link coming soon).
