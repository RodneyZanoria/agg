# README — Direction 03: Signal + Space

## Design Thesis
A visually distinctive premium design that uses radical negative space and editorial type scale to make each proof element feel like a featured article — letting Anne's photography and credentials do the work without visual noise. The mauve accent is the only color decision that matters: deliberate, unusual, and unmistakably personal.

---

## Typography Pairings + Scale

| Role | Font | Weight | Size (desktop) | Size (mobile) |
|------|------|--------|----------------|---------------|
| Display / H1 | Cormorant Garamond | 700 | 100px / 6.25rem | 52px / 3.25rem |
| H2 Section Heading | Cormorant Garamond | 600 | 56px / 3.5rem | 34px / 2.125rem |
| H3 Subheading | Satoshi | 600 | 20px / 1.25rem | 18px / 1.125rem |
| Body | Satoshi | 400 | 17px / 1.0625rem | 16px / 1rem |
| Label / Eyebrow | Satoshi | 600 | 11px / 0.6875rem | 11px |
| CTA Button | Satoshi | 700 | 14px / 0.875rem | 14px |

**Scale ratio:** 1.414 (augmented fourth)
**Line heights:** headings 0.98–1.05 (very tight — display serif needs this), body 1.72
**Letter spacing:** headings -0.02em, body 0, labels +0.14em

**Rationale:** Cormorant Garamond is a high-drama serif designed for large display sizes — at 100px it reads like a headline from Vogue or Monocle. Satoshi is a refined geometric sans that grounds it. The pairing reads as "thought leader / doer" — exactly Anne's positioning.

**Fonts source:** Cormorant Garamond via Google Fonts. Satoshi via Fontshare CDN (free, high quality).

**Google Fonts import:** `Cormorant+Garamond:ital,wght@0,600;0,700;1,600;1,700`
**Fontshare:** `https://api.fontshare.com/v2/css?f[]=satoshi@400,500,600,700&display=swap`

---

## Color Tokens

```css
/* Base */
--color-bg:           #F9F6F1;   /* Bone white — warm and premium */
--color-surface:      #F0EBE3;   /* Slightly browner for alternating sections */
--color-border:       #E0D8CF;   /* Warm tan divider */

/* Text */
--color-heading:      #1E1E1E;   /* Soft black — not pure, more ink-like */
--color-body:         #3D3A36;   /* Warm dark gray */
--color-muted:        #8A847C;   /* Warm gray for labels */

/* Accent — Dusty Mauve */
--color-accent:       #B5607A;   /* Dusty rose / mauve — CTAs, decorative marks */
--color-accent-dark:  #8F3F59;   /* Hover state */
--color-accent-light: #F5E4EA;   /* Tinted pill backgrounds */
--color-accent-text:  #6B2F44;   /* Text on light backgrounds */

/* Dark */
--color-dark:         #1E1E1E;
--color-dark-mid:     #2C2826;

/* Neutrals */
--color-white:        #FFFFFF;
```

**Why mauve:** No keynote speaker uses mauve. It reads as warmth + strength — not soft, not aggressive. Against bone white, it creates instant visual fingerprint. At the size of a CTA button, it commands without shouting — aligns with "less is more."

---

## Section-by-Section Homepage Structure

### 1. Global Navigation
- Ultra-minimal: logo left, nav center, CTA far right
- No background on initial load — transparent over hero zone
- Scrolls to white + thin border on sticky
- Mobile: hamburger with animated slide-down

### 2. Hero Section
**Layout:** Asymmetric 60/40 — serif headline at massive scale left column, portrait floats right column**

- Eyebrow (11px all-caps): RESILIENCE — LEADERSHIP — CHANGE — KEYNOTE SPEAKER
- H1 (Cormorant, 100px): "Build organizations that bend but never break."
- One-line sub: role + proof stat inline: "Anne Grady — 1,200+ engagements across Fortune 100 organizations"
- Two CTAs: "Check Availability" (mauve) / "See Speaking Topics" (ghost)
- Portrait: 2025 headshot, natural crop, floats with slight top-margin offset from text baseline

### 3. Editorial Stats Band
**Treatment: large numbers as typographic art, not boxed stats**

- 3 stat columns across full width
- Each stat: number at 72px Cormorant bold + 2-word label at 13px Satoshi
- No background fill — just numbers floating on bone-white
- Thin top + bottom border rules

### 4. Speaking Topics
**Layout: alternating left-right row pairs — image/text, text/image — editorial magazine feel**

- 4 programs, each as a full-width row taking one screen of scroll
- Text half: program number (01–04), title (Cormorant 48px), outcome para, CTA
- Visual half: abstract background or solid color block (mauve, bone, or ink-dark) — avoids relying on images for topics

### 5. Featured Testimonial
**Full section — single testimonial displayed at editorial scale**

- Background: dark ink (#1E1E1E)
- Quote at 40px Cormorant italic — full width
- Attribution below in Satoshi 14px
- Decorative: large decorative quotation mark as CSS pseudo-element

### 6. Second Testimonial + Logos
**Two-column split: testimonial left, client logos right**

- Testimonial: standard size, no extra treatment
- Logo grid: 6 logos in 3×2, rendered mid-gray for visual consistency

### 7. Book Covers
**Treatment: books as editorial objects, not product shots**

- EvolvAbility: 3D cover image large, tilted 5deg with CSS transform, shadow — feels tactile
- Book title + 1-line description + buy link
- Earlier titles: minimal row, just covers + titles

### 8. About / Authority Block
**Large portrait bleeds to left page edge (desktop). Content floats right.**

- Lead statement (not biography): "Not a speaker who inspires and disappears."
- Followed by 3-sentence authority paragraph
- Credentials as inline bold runs within paragraph copy (not a list)
- CTA: "Anne's Full Story >"

### 9. Final CTA Section
**Mauve (#B5607A) full-width background**

- H2 (Cormorant italic, 56px): "The right speaker changes everything."
- Sub: "Check Anne's availability — most dates book 6–12 months in advance."
- White CTA button
- Small trust mark: "Average inquiry response: 24 hours"

### 10. Footer
- Bone white footer (versus dark — matches overall light palette)
- Logo in dark version
- 3-column nav
- WBENC, NSA badges as trust identifiers

---

## Mobile Behaviors

### Navigation
- Logo only + hamburger at mobile
- Overlay menu with Cormorant headline links at 40px for dramatic presence
- "Check Availability" button at bottom of overlay menu

### Sticky CTA
- After hero passes out of view: mauve pill (48px tall) fixed to bottom of screen
- Label: "Check Availability"
- Hides when final CTA section is in view

### Spacing Rules
- Section padding: 112px desktop / 64px mobile
- Hero: generous — 140px top, 80px bottom desktop / 80px top mobile
- Column gaps compact on mobile: items stack
- H1: 100px desktop → 52px tablet → 42px mobile
- Wide gutters (80px) collapse to 20px padding at mobile

### Touch Targets
- All interactive elements: minimum 48px touch target
- CTA buttons: full-width at mobile
- Topic rows scroll naturally — no horizontal scroll

---

## WordPress Mapping Notes

### Theme Architecture
- **Block theme (FSE):** Required for editorial layout control
- Cormorant Garamond: Google Fonts (available in WordPress.org fonts)
- Satoshi: self-host via Fontshare download (free license)
- All sections buildable with Gutenberg blocks — Group, Cover, Columns, Quote

### Block Patterns to Create
1. `agg/hero-editorial` — Asymmetric 60/40 hero with large serif + portrait float
2. `agg/stats-typographic` — 3-column stat display with large numeral treatment
3. `agg/topic-alternating` — Full-width alternating topic rows
4. `agg/quote-dark-feature` — Full-screen dark testimonial section
5. `agg/quote-logos-split` — Testimonial + logo grid side by side
6. `agg/books-editorial` — Tilted 3D book cover + editorial row
7. `agg/about-bleed` — Left-bleed portrait with right content column
8. `agg/cta-mauve` — Full-width mauve CTA section

### theme.json Font Mapping
```json
{
  "settings": {
    "typography": {
      "fontFamilies": [
        { "fontFamily": "Cormorant Garamond, serif", "slug": "display", "name": "Display" },
        { "fontFamily": "Satoshi, sans-serif", "slug": "body", "name": "Body" }
      ]
    },
    "color": {
      "palette": [
        { "color": "#F9F6F1", "slug": "bg", "name": "Bone White" },
        { "color": "#1E1E1E", "slug": "ink", "name": "Ink" },
        { "color": "#B5607A", "slug": "accent", "name": "Mauve" }
      ]
    }
  }
}
```

### Plugin Assumptions (Minimal)
- Yoast SEO (schema)
- WPForms Lite (inquiry form)
- ShortPixel (WebP)
- No page builder — all native blocks

### Performance Notes
- Cormorant Garamond is display-only: only load the weights and styles actually used (600, 700, italic 600)
- Satoshi: self-host 4 weights only (400, 500, 600, 700)
- `font-display: optional` for non-critical fonts to prevent render blocking
- Book cover tilt: CSS transform only — no JS
- Target LCP: < 2.5s (hero portrait is LCP element — optimize first)
- No JS animation library needed — IntersectionObserver only for sticky CTA + fade-in
