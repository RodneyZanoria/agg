# README — Direction 01: Proof Architecture

## Design Thesis
A conversion-first keynote speaker homepage that makes booking Anne feel as structured and low-risk as hiring a senior executive — by building an unbroken chain of evidence from the first viewport to the final call to action.

---

## Typography Pairings + Scale

| Role | Font | Weight | Size (desktop) | Size (mobile) |
|------|------|--------|----------------|---------------|
| Display / H1 | Syne | 800 | 88px / 5.5rem | 44px / 2.75rem |
| H2 Section Heading | Syne | 700 | 52px / 3.25rem | 32px / 2rem |
| H3 Subheading | Syne | 600 | 28px / 1.75rem | 22px / 1.375rem |
| Body | Instrument Sans | 400 | 17px / 1.0625rem | 16px / 1rem |
| Caption / Label | Instrument Sans | 500 | 13px / 0.8125rem | 13px |
| CTA Button | Instrument Sans | 600 | 15px / 0.9375rem | 15px |

**Scale ratio:** 1.333 (perfect fourth)
**Line heights:** headings 1.05, body 1.65
**Letter spacing:** headings -0.02em, body 0

**Google Fonts import:** `Syne:wght@400;600;700;800` + `Instrument+Sans:wght@400;500;600`

---

## Color Tokens

```css
/* Base */
--color-bg:          #FAFAF8;   /* Near-white, warm */
--color-surface:     #F2EFEB;   /* Soft card/section fill */
--color-border:      #E4E0DA;   /* Subtle dividers */

/* Text */
--color-heading:     #0F1923;   /* Deep slate — authority */
--color-body:        #3A3A3A;   /* Dark gray — readable */
--color-muted:       #7A756E;   /* Labels, captions */

/* Accent */
--color-accent:      #C4501A;   /* Terracotta / burnt orange */
--color-accent-dark: #9E3E0F;   /* Hover state */
--color-accent-light:#F5E6DE;   /* Tinted backgrounds */

/* Neutrals */
--color-white:       #FFFFFF;
--color-ink:         #0F1923;
```

---

## Section-by-Section Homepage Structure

### 1. Global Navigation
- Logo left (white-transparent PNG at 1x, 200px wide)
- Nav links: Speaking Topics / About / Books / Resources / Testimonials
- CTA button: "Check Availability" — terracotta, always visible on desktop
- Mobile: hamburger with slide-down drawer; sticky CTA pill persists below nav

### 2. Hero Section
**Layout:** 55% left column (text) / 45% right column (portrait photograph)

- Label above headline: "KEYNOTE SPEAKER — RESILIENCE — LEADERSHIP — CHANGE"
- H1: "Build the capacity to withstand anything, and lead through it."
- Subheadline: "Anne Grady equips organizations with the mindset and skills to adapt, recover, and grow under pressure."
- Primary CTA: "Check Availability" — terracotta button, large
- Secondary CTA: "Download Speaking Topics" — text link with arrow
- Right column: 2025 portrait (retouched), no background removal, natural crop

**Proof Signal Below Headline (inside hero):**
- 3 inline stat chips: "1,200+ Engagements" / "Fortune 100 Clients" / "4 Published Books"

### 3. Proof Bar
**Full-width band, warm surface background (#F2EFEB)**

- Left: Single executive testimonial snippet (2 lines max) + name/title/company
- Right: 6 client logos arranged in 2 rows × 3 columns — Google, Microsoft, Johnson & Johnson, General Mills, ADP, AT&T
- WBENC badge, "Top 50 Keynote Speaker" badge shown as small inline trust marks

### 4. Speaking Topics
**Section heading: "Where Anne Grady Creates Impact"**

- 4 topic cards in a 2×2 grid (desktop) / single column (mobile)
- Each card: Topic name / audience outcome statement / 2-line description
- Topics: Resilience Reset / Adaptive Leadership / Change Without Chaos / The Resilient Team
- Card style: white surface, terracotta top border accent, hover lifts with shadow

### 5. Outcomes Section (Event Planner Language)
**Section heading: "What Your Audience Walks Away With"**
**Sub-label: "Designed for meeting planners, HR leaders, and conference organizers"**

- 3-column outcomes grid (desktop) / stacked (mobile)
- Each outcome: Icon (SVG line icon) + headline + 2-sentence description
- Outcomes: Practical resilience skills they use immediately / A changed perspective on pressure and change / Language to lead differently when it matters most

### 6. Testimonials
**Dark slate (#0F1923) background for contrast**

- 2 testimonial cards with pull-quote format
- Each: Quote at 24px / Executive name + title + company / Company name
- Subtle terracotta quotation mark decorative element

### 7. Book Covers
**Section heading: "Thought Leadership in Print"**

- 5 book covers: EvolvAbility (latest, featured large) + 3 earlier titles in a row
- EvolvAbility: 3D cover webp (medium size), title, buy button
- Earlier titles: smaller flat covers, title, inline link

### 8. About / Authority Block
**Layout:** Right-side portrait, left-side copy

- NOT biography-first. Lead with: "Trusted by organizations that can't afford to get resilience wrong."
- 3 credential bullets: 20+ years developing resilience / Certified Mental Health First Aid Instructor / WBENC-certified speaker
- Secondary portrait photograph (different from hero)
- CTA: "Anne's Full Story"

### 9. Final CTA Section
**Terracotta (#C4501A) brand-color background**

- Heading: "Your next event deserves a speaker who changes how people think."
- Sub: "Spots are limited. Check Anne's availability for your date."
- Primary button: "Check Availability" — white
- Secondary: "Or send a brief" (text link) — white underline

### 10. Footer
- Logo (white version)
- Nav links in two columns
- Social icons (LinkedIn, Facebook, Instagram)
- WBENC badge, copyright

---

## Mobile Behaviors

### Navigation
- Logo + hamburger icon only
- Drawer slides down from top (pure CSS preferred, JS fallback)
- All nav links at 18px minimum touch target 48px

### Sticky CTA
- After user scrolls past the hero (IntersectionObserver trigger)
- Pill: "Check Availability" — terracotta, fixed to bottom, full-width on mobile
- Disappears when user is in the final CTA section

### Spacing Rules
- All section padding: 80px desktop / 56px mobile
- Hero section: 120px desktop / 80px mobile
- Card grid gaps: 24px desktop / 16px mobile
- Font sizes at breakpoints: H1 88px (desktop) → 44px (tablet) → 36px (mobile)

### Image Handling
- Hero portrait: object-fit cover, aspect-ratio 4/5 on mobile, fills right half on desktop
- Book covers: responsive widths, lazy loaded
- Logo bar: overflow-x: auto with scroll-snap on mobile

---

## WordPress Mapping Notes

### Theme Architecture
- **Block theme (FSE)** recommended: Twenty Twenty-Four as base, or GeneratePress Pro block theme
- **Global Styles (theme.json):** Map all CSS custom properties above to `settings.custom.*`
- Typography: Use `theme.json` font families + sizes to match scale above

### Block Patterns to Create
1. `agg/hero-split` — Two-column hero with portrait right, text left, proof chips
2. `agg/proof-bar` — Testimonial + logo grid combo
3. `agg/topic-card-grid` — 2×2 topic card grid
4. `agg/testimonial-dark` — Dark-background pull-quote pair
5. `agg/book-covers` — EvolvAbility featured + row of titles
6. `agg/about-authority` — Right-portrait, left-copy block
7. `agg/cta-full-width` — Terracotta section with heading + dual button

### Plugin Assumptions (Minimal)
- **SEO:** Yoast SEO (schema support already built)
- **Forms:** WPForms Lite (single form for speaking inquiry)
- **Performance:** WP Rocket or Perfmatters (no page builder)
- **No page builder needed** — all blocks native or custom Gutenberg patterns

### Image Optimization
- Convert all JPG/PNG assets to WebP at upload (ShortPixel or Imagify)
- Hero portrait: 900px wide @2x = 1800px max, 80% quality WebP
- Logo bar: SVG preferred (available in asset folder), PNG fallback
- Book covers: Medium webp (800px) for display

### Schema Placeholders
- Person schema: Anne Grady (see JSON-LD in index.html)
- Organization schema: Anne Grady Group
- Event schema: Not required on homepage — relevant on individual speaking topic pages
