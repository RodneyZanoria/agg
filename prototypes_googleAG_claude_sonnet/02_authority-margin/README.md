# README — Direction 02: Authority Margin

## Design Thesis
A site that earns premium positioning through extreme restraint — generous margins, exacting typography, and a three-value color palette so confident it never needs to shout. The single-column content thread mirrors a well-designed book: one idea per scroll unit, never competing for attention.

---

## Typography Pairings + Scale

| Role | Font | Weight | Size (desktop) | Size (mobile) |
|------|------|--------|----------------|---------------|
| Display / H1 | DM Serif Display | 400 (italic available) | 96px / 6rem | 48px / 3rem |
| H2 Section Heading | DM Serif Display | 400 | 52px / 3.25rem | 32px / 2rem |
| H3 Subheading | DM Sans | 600 | 22px / 1.375rem | 20px / 1.25rem |
| Body | DM Sans | 400 | 17px / 1.0625rem | 16px / 1rem |
| Label / Caption | DM Sans | 500 | 12px / 0.75rem | 12px |
| CTA Button | DM Sans | 600 | 15px / 0.9375rem | 15px |

**Scale ratio:** 1.414 (augmented fourth — more dramatic contrast than perfect fourth)
**Line heights:** headings 1.02, body 1.7
**Letter spacing:** headings +0.01em (Serif — slightly open), body 0

**Rationale:** DM Serif Display and DM Sans are purpose-built partners. The serif carries authority and warmth; the sans maintains legibility and modernity. No third font needed.

**Google Fonts import:** `DM+Serif+Display:ital@0;1` + `DM+Sans:wght@400;500;600;700`

---

## Color Tokens

```css
/* Base */
--color-bg:           #F8F5F0;   /* Bone white — warm, premium, paper-like */
--color-surface:      #EEEBE6;   /* Slightly deeper warm gray for alternating sections */
--color-border:       #DDD8D1;   /* Subtle warm divider */

/* Text */
--color-heading:      #141414;   /* Near-black ink */
--color-body:         #3C3C3C;   /* Dark charcoal — readable, not harsh */
--color-muted:        #7A7570;   /* Warm gray for captions */

/* Accent — Pine Green */
--color-accent:       #1B4332;   /* Deep pine green — CTAs, nav bar, key interactive states */
--color-accent-mid:   #2D6A4F;   /* Secondary state */
--color-accent-light: #D8EDDB;   /* Tinted surface for highlight chips */
--color-accent-text:  #0B2A1F;   /* Text on accent-light */

/* Neutrals */
--color-white:        #FFFFFF;
--color-ink:          #141414;
```

**Why pine green:** No competitor uses this color. It signals stability, growth, and authority — the emotional territory of resilience — without the cliches of corporate blue or speaker-circuit orange. Against bone white, it reads as quietly confident.

---

## Section-by-Section Homepage Structure

### 1. Global Navigation
- Thin green top bar (4px, #1B4332) as a brand stripe above the nav
- Logo centered at mobile / left-aligned at desktop
- Nav links: Speaking / About / Books / Testimonials / Contact
- CTA: "Check Availability" — pine green button, small, far right
- Mobile: logo + hamburger, full-screen overlay menu

### 2. Hero Section
**Layout:** Wide outer margin (160px desktop). Single column. Text-dominant.

- Small credential line above H1: "Resilience Keynote Speaker — Fortune 100 Speaker — 4-Time Bestselling Author"
- H1 (DM Serif Display, italic option): "The capacity to lead through pressure isn't rare. It can be built."
- Body paragraph: one sentence, 20px, describing the core offer
- Two CTA buttons (stacked): "Check Availability" (green, full-width block) / "Explore Speaking Topics" (ghost)
- Hero portrait: positioned to break out of the right margin, partially overlapping the section below

### 3. Featured Testimonial (First Proof Signal)
**Full-width warm surface (#EEEBE6). No heading — just the quote.**

- Single large pull-quote at 36px DM Serif Display italic
- Attribution: name, title, company
- This immediately follows the hero — proof before features

### 4. Speaking Topics
**Section heading: "Programs built around outcomes, not topics"**

- 4 programs listed as a clean vertical stack (not cards)
- Each: number (01–04) / topic name / one-line outcome statement / "Learn more >" link
- Divider lines between each row — editorial, not boxy

### 5. Outcomes Section
**Dark pine green (#1B4332) background for maximum contrast**

- 3 outcome columns in white text
- Section heading: "What changes after Anne speaks"
- Each column: headline + 2-sentence description

### 6. Testimonials
**Bone white background — contrast with the dark section above**

- 2 testimonials in a 2-column grid
- Pull-quote format at 22px — one claim per testimonial
- Clean: just the quote, name, title, company — no card chrome

### 7. Book Covers
**Section heading: "The frameworks behind the keynote"**

- EvolvAbility featured with 3D cover image + title + 2-sentence description + buy button
- 3 earlier titles as a tight horizontal row with just title beneath

### 8. About / Authority Block
**Asymmetric layout: wide empty margin left, content right (desktop)**
**This is the one portrait below the hero**

- Deliberately NOT biography-first
- Lead: "20+ years. 1,200+ engagements. Organizations that moved differently afterward."
- 4 credentials in a clean bulleted list
- Portrait photo positioned at left, extending to page edge

### 9. Final CTA
**Pine green (#1B4332) full-width panel**

- Headline (DM Serif Display italic): "Every great event starts with the right call."
- Sub: "Check Anne's availability for your date — no commitment required."
- White CTA button
- Small print: average response time

### 10. Footer
- Three-column nav links
- Logo top of footer (white version)
- WBENC + NSA badges as SVG trust marks

---

## Mobile Behaviors

### Navigation
- Logo + hamburger only
- Full-screen overlay with nav items at 32px
- Green "Check Availability" pill within overlay

### Sticky CTA
- Appears after hero scrolls out of view
- Slim green bar (48px) pinned to bottom: "Check Availability" full-width
- Disappears when final CTA section enters view

### Spacing Rules
- Section padding: 96px desktop / 64px mobile
- Hero: 128px top, 80px bottom desktop / 80px top, 56px bottom mobile
- Wide outer margin collapses to 24px on mobile
- H1: 96px desktop → 48px tablet → 38px mobile
- Body: 17px desktop / 16px mobile (no change)

### Image Handling
- Portrait in hero: breaks right margin on desktop, full-width on tablet/mobile
- Book covers: lazy loaded, WebP format
- No layout shift from images (explicit width/height attributes)

---

## WordPress Mapping Notes

### Theme Architecture
- **Block theme (FSE):** Preferred. Theme.json maps all tokens exactly.
- Base: GenerateBlocks Pro or Twenty Twenty-Four custom child
- All sections buildable with native Gutenberg blocks + Group containers

### Block Patterns to Create
1. `agg/hero-single-col` — Full-width text hero with credential line + portrait break-out
2. `agg/featured-quote` — Full-width pull-quote section
3. `agg/topics-list` — Vertical numbered list of programs
4. `agg/outcomes-dark` — Dark green 3-column outcome section
5. `agg/testimonial-pair` — Clean 2-column quote pair (no cards)
6. `agg/authority-block` — Asymmetric about section with edge-break portrait
7. `agg/cta-green` — Full-width pine green final CTA

### theme.json Font Mapping
```json
{
  "settings": {
    "typography": {
      "fontFamilies": [
        { "fontFamily": "DM Serif Display, serif", "slug": "display", "name": "Display" },
        { "fontFamily": "DM Sans, sans-serif", "slug": "body", "name": "Body" }
      ],
      "fontSizes": [
        { "size": "0.75rem", "slug": "xs", "name": "XS" },
        { "size": "1.0625rem", "slug": "base", "name": "Base" },
        { "size": "1.375rem", "slug": "md", "name": "Medium" },
        { "size": "2rem", "slug": "xl", "name": "XL" },
        { "size": "3.25rem", "slug": "2xl", "name": "2XL" },
        { "size": "6rem", "slug": "hero", "name": "Hero" }
      ]
    },
    "color": {
      "palette": [
        { "color": "#F8F5F0", "slug": "bg", "name": "Background" },
        { "color": "#141414", "slug": "ink", "name": "Ink" },
        { "color": "#1B4332", "slug": "accent", "name": "Pine Green" }
      ]
    }
  }
}
```

### Plugin Assumptions (Minimal)
- Yoast SEO (Person + Organization schema)
- WPForms Lite (single inquiry form)
- ShortPixel (WebP conversion on upload)
- No page builder — native blocks only

### Performance Notes
- Self-host DM Serif Display + DM Sans using Google Fonts download
- Add `font-display: swap` to @font-face
- All images: explicit width/height, loading="lazy" (except hero portrait: loading="eager" fetchpriority="high")
- Avoid any JS animation library — all transitions are CSS-only
- Target LCP: < 2.5s, CLS: 0
