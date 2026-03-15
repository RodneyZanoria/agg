# WordPress Implementation Checklist
## Anne Grady Group — Redesign Build Notes
## March 2026

---

## Overview

Three design directions have been prototyped. This document covers WordPress implementation guidance for all three, with direction-specific notes where approaches diverge. All three directions are designed for native WordPress block editor (Full Site Editing). No page builder required.

---

## Pre-Build Setup

### WordPress Configuration
- [ ] Install WordPress (latest stable version — 6.x or later required for FSE)
- [ ] Set permalink structure: `/%postname%/`
- [ ] Set timezone to match client's location
- [ ] Disable comments site-wide (speakers don't need comment threads)
- [ ] Configure media upload settings: JPEG quality 85%, generate WebP copies on upload

### Theme Selection
**Recommended base:** Blocksy (lightweight, FSE-compatible, excellent Global Styles support)
**Alternative:** Generate Press Pro (most stable for block patterns)
**Avoid:** Divi, Elementor Hello, OceanWP — incompatible with the clean block approach required

- [ ] Install parent theme
- [ ] Create child theme for customizations
- [ ] Upload brand Green stripe (Direction 02) as site-wide accent element via Global Styles

---

## Font Setup (All Three Directions)

### Direction 01: Proof Architecture
**Fonts:** Syne + Instrument Sans

Both available on Google Fonts. For WordPress:
- [ ] Download fonts from Google Fonts and self-host for GDPR compliance
- [ ] Add via `@font-face` in `functions.php` using `wp_enqueue_style` with `font-display: swap`
- [ ] Alternative: use the "Fonts" panel in WordPress 6.5+ if your host supports Google API proxy

### Direction 02: Authority Margin
**Fonts:** DM Serif Display + DM Sans

Both available on Google Fonts.
- [ ] Same self-hosting process as above
- [ ] DM Serif Display: load only weights `400` (roman) and `400 italic` — all you need
- [ ] DM Sans: load weights `400, 500, 600, 700` via variable font axis

### Direction 03: Signal + Space
**Fonts:** Cormorant Garamond + Satoshi

- Cormorant Garamond: Google Fonts (`600`, `700`, `600 italic`, `700 italic`)
- Satoshi: Download from Fontshare (free, commercial license). Self-host.
- [ ] Add both via `functions.php` self-hosted `@font-face` declarations
- [ ] Do NOT load Satoshi from Fontshare CDN in production — self-host to eliminate third-party DNS lookup

---

## Global Styles (theme.json)

Map all CSS custom properties from each prototype's `styles.css` to `theme.json`. This allows the client to use Gutenberg's Global Styles panel to make color/typography edits safely.

### Minimum theme.json structure (example for Direction 01):
```json
{
  "$schema": "https://schemas.wp.org/trunk/theme.json",
  "version": 2,
  "settings": {
    "appearanceTools": true,
    "color": {
      "custom": false,
      "customDuotone": false,
      "customGradient": false,
      "defaultDuotone": false,
      "defaultGradients": false,
      "defaultPalette": false,
      "palette": [
        { "color": "#FAFAF8", "name": "Background", "slug": "bg" },
        { "color": "#F2EFEB", "name": "Surface", "slug": "surface" },
        { "color": "#0F1923", "name": "Heading / Ink", "slug": "heading" },
        { "color": "#C4501A", "name": "Accent / Terracotta", "slug": "accent" },
        { "color": "#FFFFFF", "name": "White", "slug": "white" }
      ]
    },
    "typography": {
      "customFontSize": false,
      "fontSizes": [
        { "size": "0.8125rem", "name": "XS", "slug": "xs" },
        { "size": "1.0625rem", "name": "Base", "slug": "base" },
        { "size": "1.25rem", "name": "Medium", "slug": "md" },
        { "size": "2rem", "name": "XL", "slug": "xl" },
        { "size": "3.25rem", "name": "2XL", "slug": "2xl" },
        { "size": "5.5rem", "name": "Hero", "slug": "hero" }
      ],
      "fontFamilies": [
        { "fontFamily": "Syne, sans-serif", "name": "Syne (Display)", "slug": "display" },
        { "fontFamily": "Instrument Sans, sans-serif", "name": "Instrument Sans (Body)", "slug": "body" }
      ]
    },
    "spacing": {
      "units": ["px", "rem", "%", "vw"]
    }
  }
}
```

> Repeat the palette and font configuration pattern for Directions 02 and 03 with their respective color and font values.

---

## Block Patterns to Build

Block patterns are the key reusable building blocks. Create each as a registered PHP pattern or via the Patterns manager in WordPress 6.4+.

### All Directions — Shared Patterns Needed
| Pattern Name | Description |
|---|---|
| `agg/hero-*` | Direction-specific hero layout |
| `agg/proof-bar` | Client logos + testimonial snippet combo |
| `agg/topic-grid` or `agg/topic-list` | Speaking programs (cards or list format) |
| `agg/testimonial-pair` | 2-column testimonial section |
| `agg/book-featured` | EvolvAbility 3D cover + info + CTA |
| `agg/about-authority` | Authority block — not biography-first |
| `agg/cta-final` | Section-wide final CTA with accent background |
| `agg/site-footer` | Footer with nav, logo, badges |

### Direction-Specific Patterns
| Direction | Unique Patterns |
|---|---|
| 01 Proof Architecture | `agg/hero-split-left` (55/45 grid), `agg/outcomes-3col`, `agg/testimonials-dark-panel` |
| 02 Authority Margin | `agg/hero-single-column-deep`, `agg/featured-pullquote`, `agg/topics-numbered-list`, `agg/outcomes-pine-green`, `agg/cta-dark-panel` |
| 03 Signal + Space | `agg/hero-editorial-asymmetric`, `agg/stats-typographic-band`, `agg/topic-alternating-rows`, `agg/quote-dark-full`, `agg/books-tilted` |

> Register patterns in `functions.php` using `register_block_pattern()` or by placing PHP files in `patterns/` directory (WordPress 6.0+).

---

## Asset Pipeline

### Logo
- [ ] Use SVG version from `/AGG Logos (Master)/AGG Logos (Master)/Logos AGG - Format SVG/`
- [ ] Upload: "AGG Logo - Color (SVG)" for light backgrounds
- [ ] Upload: "AGG Logo - White (SVG)" for dark backgrounds
- [ ] Set as Site Logo in WordPress Customizer / Global Styles
- [ ] Ensure `width` and `height` attributes set in block editor to prevent CLS

### Headshots
- [ ] Primary hero portrait: `2025 Headshots - Retouched-9151.jpg` (or -9376.jpg)
- [ ] About section portrait: `2025 Headshots - Retouched-0109.jpg` or `-0476.jpg`
- [ ] Convert all JPG headshots to WebP before upload using ShortPixel or Squoosh
- [ ] Target sizes: hero portrait at 900px × 1125px WebP, about portrait at 800px × 1000px WebP
- [ ] Set `loading="eager"` and `fetchpriority="high"` on hero images only; all others `loading="lazy"`

### Book Covers
- [ ] EvolvAbility 3D: Use the `.webp` version from `/Book Covers 5 - EvolvAbility/`
- [ ] Best size for featured display: `Book Covers - EvolvAbility 3D Medium (803x1381).webp`
- [ ] Earlier titles: Use the FLAT webp versions from `/Book Covers 0 - All Large/`
- [ ] Do not upload the 1800px or larger versions — use the Medium variants

### Client Logos
- [ ] Source logos from `/uploads/client_logos/` directory
- [ ] Preferred format: SVG. If only PNG available: scale to 200px wide max, WebP convert
- [ ] Render logos in grayscale using CSS `filter: grayscale(100%)` — hover reveals color (Direction 01 only)
- [ ] Direction 03: render all logos at uniform mid-gray opacity for editorial consistency

---

## Plugin Stack (Minimal by Design)

| Category | Plugin | Notes |
|---|---|---|
| SEO | Yoast SEO | Adds Person + Organization schema automatically; configure in plugin settings |
| Forms | WPForms Lite | Single "Speaking Inquiry" form on Contact page and modal; do not use Gravity Forms unless already licensed |
| Performance | WP Rocket | Configure: JS defer, CSS minification, lazy load, preload critical CSS |
| Images | ShortPixel | WebP conversion on upload; bulk convert existing media library |
| Security | Wordfence (free) | Basic firewall only; do not install additional security plugins |
| Analytics | GA4 via gtag.js | Inject via Code Snippets plugin or wp_head hook; avoid MonsterInsights for performance |

**Do not install:**
- Slider Revolution or any slider plugin
- Elementor, Divi, or WPBakery
- Multiple caching plugins (WP Rocket alone is sufficient)
- Social proof plugins (testimonials are hardcoded patterns — no plugin needed)

---

## SEO Implementation

### Schema (JSON-LD)
Yoast SEO handles most schema automatically. Supplement with:
- [ ] Configure "Anne Grady" as the Person entity in Yoast Knowledge Graph settings
- [ ] Add Organization schema via Yoast or via a Code Snippets plugin entry
- [ ] Verify schema output at schema.org/validator before launch
- [ ] Reference JSON-LD comment blocks in each `index.html` prototype for field mapping

### On-Page SEO Checklist (Homepage)
- [ ] Title tag: `Anne Grady | Resilience Keynote Speaker | Anne Grady Group`
- [ ] Meta description: 150–160 chars, includes "resilience keynote speaker", "Fortune 100", CTA verb
- [ ] H1: Exactly one H1 per page — matches the hero headline
- [ ] H2s: Speaking Topics heading, Outcomes heading, About heading, Final CTA heading — all H2
- [ ] H3s: Individual topic names, testimonial pull headings — all H3
- [ ] Alt text on hero portrait: "Anne Grady resilience keynote speaker [city/event optional]"
- [ ] Alt text on book covers: "[Book title] by Anne Grady — book cover"
- [ ] Alt text on client logos: "[Company name]" — no "logo" in alt text (redundant)
- [ ] Internal links: "Speaking Topics" from hero CTA links to topics section (or dedicated page)
- [ ] Canonical URL set to `https://www.annegradygroup.com/`
- [ ] No duplicate H1s in header area or footer

### Core Web Vitals Targets
| Metric | Target | Key Actions |
|---|---|---|
| LCP | < 2.5s | Hero portrait: WebP, 900px, preloaded with `fetchpriority="high"` |
| CLS | 0.0 | All images with explicit width/height; no layout shifting fonts |
| FID/INP | < 200ms | No heavy JS libraries; sticky CTA via IntersectionObserver only |
| TTFB | < 600ms | WP Rocket + server-side caching; CDN for static assets |

---

## Mobile Implementation Checklist

- [ ] Sticky CTA pill: 48px height, full-width, mauve/terracotta/green per direction, bottom-fixed
- [ ] Sticky CTA activates via IntersectionObserver on hero section exit
- [ ] Sticky CTA hides when final CTA section (#contact) enters view
- [ ] Mobile nav: hamburger opens full-screen overlay (not a dropdown)
- [ ] Touch targets: all tappable elements minimum 48 × 48px
- [ ] Font sizes at mobile: H1 minimum 2.5rem, body minimum 1rem — never smaller
- [ ] Section padding at mobile: use 56px–64px (not the desktop 80–96px values)
- [ ] Images: object-fit: cover with explicit aspect-ratio to prevent layout shift
- [ ] Book cover row: scrollable on mobile (overflow-x: auto with scroll-snap)
- [ ] Logo bar on mobile: 2-column grid max (not 3-column)

---

## Pre-Launch Verification Checklist

### Design QA
- [ ] Compare hero clarity against all 5 competitor sites — is offer clear in < 4 seconds?
- [ ] Confirm proof bar visible above fold without scroll on 1280px desktop
- [ ] Confirm CTAs visible at every scroll unit — no more than 2 scroll units between CTAs
- [ ] Confirm sticky mobile CTA works correctly on iPhone Safari + Chrome Android
- [ ] Test dark section readability: minimum contrast ratio 4.5:1 (WCAG AA)

### Technical QA
- [ ] Run Google PageSpeed Insights — achieve 90+ mobile, 95+ desktop
- [ ] Run schema validator — confirm Person + Organization entities
- [ ] Check Core Web Vitals in Chrome DevTools > Performance > LCP, CLS, FID
- [ ] Validate HTML via validator.w3.org — no structural errors
- [ ] Test all CTA links — contact form, email link, book links
- [ ] Test mobile nav on real device (not emulator) on iOS Safari 16+
- [ ] Verify `rel="noopener noreferrer"` on all external links

### Content QA
- [ ] Replace all lorem ipsum / placeholder content with real copy
- [ ] Replace logo placeholder text items with actual client logo images
- [ ] Confirm EvolvAbility book link points to live Amazon or publisher page
- [ ] Confirm contact form submission goes to the correct email address
- [ ] Update copyright year in footer to current year

---

## Direction-Specific WordPress Notes

### Direction 01: Proof Architecture (Slate + Terracotta)
- Hero split (55/45) achievable with Gutenberg Columns block + custom column widths via `style.scss`
- Portrait frame's rounded top corners: add inline `border-radius: 16px 16px 0 0` via block's advanced CSS
- Proof bar (testimonial + divider + logos): build as a 3-column Columns block with custom width (auto / 1px / auto)
- Dark testimonials section: use a Cover block with dark overlay + inner Columns for the 2-card grid
- Terracotta final CTA: Group block with `backgroundColor: accent` global style token

### Direction 02: Authority Margin (Ink + Pine Green)
- Green brand stripe at top: add as a site-level element in the Header template, not per-page
- Numbered topic list: use a custom `agg/topics-list-numbered` block pattern — avoid the Gutenberg Table block
- Green outcomes section: Group block with pine green background + inner Columns (3 cols, inner border via outline)
- Left-border credentials list: styled via custom CSS class on List block

### Direction 03: Signal + Space (Bone White + Mauve)
- Alternating topic rows (full-bleed half-image): use `media-text` block in full-width alignment, alternated manually
- Book cover tilt effect: CSS `transform: rotate(-3deg)` applied via block custom CSS field — will survive editor
- Dark quote section: Cover block with dark (`#1E1E1E`) color, inner Quote block at display size
- Stat band: 4-column Columns block with center-aligned number (Heading block at `hero` size) + label (Paragraph block)

---

## Handoff File Locations

| File | Path |
|---|---|
| Direction 01 Prototype | `prototypes_googleAG_claude_sonnet/01_proof-architecture/index.html` |
| Direction 02 Prototype | `prototypes_googleAG_claude_sonnet/02_authority-margin/index.html` |
| Direction 03 Prototype | `prototypes_googleAG_claude_sonnet/03_signal-and-space/index.html` |
| Benchmark Report | `prototypes_googleAG_claude_sonnet/00_benchmark.md` |
| Scoring Document | `prototypes_googleAG_claude_sonnet/00_scoring.md` |
| Build Notes (this file) | `prototypes_googleAG_claude_sonnet/00_build-notes.md` |
| Logo Assets | `AGG Logos (Master)/AGG Logos (Master)/Logos AGG - Format SVG/` |
| Hero Portraits | `2025 Headshots (Retouched)/2025 Headshots (Retouched)/` |
| Book Covers | `Book Covers/Book Covers/Book Covers 5 - EvolvAbility/` |
