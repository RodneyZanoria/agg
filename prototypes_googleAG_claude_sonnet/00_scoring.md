# Design Direction Scoring — Anne Grady Group
## March 2026

---

## Scoring Methodology

Each direction scored 1–10 on five criteria (equal weight):

| Criterion | Description |
|-----------|-------------|
| Offer Clarity | Is the value proposition clear within 10 seconds? |
| Credibility / Proof Density | Trust signals above fold and throughout |
| Conversion Path | Event planner journey: book / inquire / availability |
| Mobile Polish | Spacing, type scale, sticky CTA behavior |
| Speed Discipline | Lightweight layout, minimal JS, fast perceived load |

**Minimum to qualify as "winning": weighted average >= 7.5**

---

## Five Design Directions

### Direction 1: Proof Architecture
*Thesis: A conversion-first site that makes booking Anne feel as structured and low-risk as hiring a senior executive, by building an unbroken chain of evidence from the hero to the final CTA.*

- **Layout Logic:** Left-aligned, asymmetric grid. Hero splits vertically: headline + CTA left, portrait photograph right with a visible stat overlay. Proof bar anchors immediately below — no scroll needed.
- **Typography:** Syne (display, geometric, distinctive) for headlines. Instrument Sans (modern, readable, not Inter) for body. Sizes: H1 80–100px desktop / 48px mobile, body 17px.
- **Color Strategy:** Near-white (#FAFAF8) background system. Deep slate (#0F1923) for headings. Single accent: a terracotta/burnt orange (#C4501A) that differs meaningfully from competitors' teal or yellow. Logo colors inform but don't dominate.
- **Imagery Strategy:** Portrait photograph crops tightly to face + shoulders with negative space to breathe. No overlay treatment — clean, natural light.
- **Trust System:** Stats row immediately below hero. Client logos in a spaced matte grid (not a ticker). Testimonial cards with executive name, title, company in small but legible type. WBENC badge + media logos in an authority strip.

---

### Direction 2: Momentum Signal
*Thesis: A high-energy, motion-aware site that communicates Anne's stage presence through kinetic layout logic — diagonals, stagger, scale — without sacrificing scan-ability or speed.*

- **Layout Logic:** Off-axis hero with angled section transitions. Speaking topics use a staggered card grid with reveal animation. Stats displayed as large numerals with sub-labels — not inside boxes.
- **Typography:** Archivo Black (display) + Outfit (body). Archivo Black has extreme weight contrast — commanding without being aggressive.
- **Color Strategy:** True charcoal (#1C1C1E, near-black) for dominant sections; cream (#FAF6F0) for light sections. Accent: a vibrant amber (#F59E0B) that reads as energy without the aggression of yellow.
- **Imagery Strategy:** Anne on stage — action shots from the provided uploads. Desaturated treatment with amber duotone overlay to unify. One portrait crop for the About block.
- **Trust System:** Credential strip at top of page (one line, small caps). Stats woven into section narrative ("Teams at 1,200+ organizations..."). Testimonial pull-quotes displayed at large type scale against dark panels.

---

### Direction 3: Authority Margin
*Thesis: A site that earns premium positioning through extreme restraint — generous margins, exacting typography, and a color palette so confident it only needs three values to feel complete.*

- **Layout Logic:** Single-column content thread with a deliberately wide outer margin that creates a sense of curated space. Like a well-designed book running on screen.
- **Typography:** DM Serif Display (headings — editorial gravitas, slightly humanist) + DM Sans (body — harmonious pairing). Radical size contrast: H1 at 96px, body at 16px. Every line counts.
- **Color Strategy:** Off-white (#F8F5F0) page. Ink (#141414) text. Single structural accent: a deep pine green (#1B4332) used only for CTAs, active states, and the nav bar strip. Restrained, but memorable.
- **Imagery Strategy:** Portrait photographs with maximum horizontal crop. Anne positioned right-of-center with generous white space left for text. No background removal — real environments, naturally lit.
- **Trust System:** A single large testimonial quote above the fold (below hero) from a Fortune 500 exec. Client logos arranged as a curated grid of 6 — not the full list. One stat per section, displayed as a standalone typographic moment.

---

### Direction 4: Stage Presence
*Thesis: A visually dramatic site that matches the energy of a keynote stage — bold contrast, full-bleed imagery, and type that commands a room — while maintaining fast load and clean IA.*

- **Layout Logic:** Full-bleed hero with portrait photograph at near-full screen height. Bold headline text set against the photograph. Grid breaks below the fold for topic cards. Dark and light sections alternate in a disciplined two-band rhythm.
- **Typography:** Cabinet Grotesk (display, variable weight — compressed to ultra-wide for different sections) + Libre Franklin (body). Type as visual element in the hero — not just informational.
- **Color Strategy:** Deep navy (#060F1E) for all dark sections. Pure white for light sections. Accent: neon-adjacent electric green (#00C896) used sparingly only for interactive states.
- **Imagery Strategy:** Hero uses the most dramatic stage presence shot from the uploads. Highly intentional crops — photographer's eye applied. Section photography alternates portrait and wide.
- **Trust System:** Award / ranking badge overlaid on hero image. Stats as large-format numbers inset into a dark panel. Named testimonials with LinkedIn-style credential chips.

---

### Direction 5: Signal + Space
*Thesis: A premium, airy design that uses dramatic negative space and editorial scale to make each proof element feel like a featured article — letting Anne's photography and credentials do the work without visual noise.*

- **Layout Logic:** Asymmetric two-column hero (60/40 split). Wide gutters throughout — 120px+ on desktop. Section dividers by typography changes, not by background color blocks. Every section floats.
- **Typography:** Cormorant Garamond (large display, character, refined) + Satoshi (body, geometric but warm). The serif/sans contrast creates a "thought leader / doer" duality.
- **Color Strategy:** Bone white (#F9F6F1) dominant. Warm graphite (#2C2C2C) for headings. A single dusty rose/mauve (#B5607A) accent used only for CTA buttons and decorative accents — visually distinctive and feminine without being weak.
- **Imagery Strategy:** Portrait photography treated with a warm filter to unify with bone-white background. Generous vertical portraits in hero zone. Book covers displayed as editorial objects, not product shots.
- **Trust System:** Proof elements treated as editorial pulls: one quote per testimonial section shown at 36px, full-width. Logo grid rendered in mid-gray (no color logos) for visual consistency. Stats embedded in body copy as bolded inline elements.

---

## Detailed Scoring

### Direction 1: Proof Architecture

| Criterion | Score | Justification |
|-----------|-------|---------------|
| Offer Clarity | 9 | Portrait + headline + stat immediately communicate "keynote speaker at this level" |
| Credibility / Proof Density | 10 | Proof bar immediately below hero; this is the only direction that achieves proof above fold without sacrificing hero clarity |
| Conversion Path | 9 | Dual CTA (Check Availability / Download Topics) visible in hero; no scroll required |
| Mobile Polish | 9 | Single-column stacks cleanly; sticky CTA pill defined in mobile variant |
| Speed Discipline | 9 | No animation dependencies; clean CSS, minimal JS |

**Weighted Average: 9.2 — WINNER (Rank 1)**

---

### Direction 2: Momentum Signal

| Criterion | Score | Justification |
|-----------|-------|---------------|
| Offer Clarity | 8 | Headline + energy are clear; stage presence is the signal |
| Credibility / Proof Density | 8 | Stats visible but integrated into narrative rather than block-displayed above fold |
| Conversion Path | 8 | CTAs present throughout; amber accent draws eye well |
| Mobile Polish | 7 | Stagger cards collapse acceptably; diagonal transitions need care at mobile breakpoints |
| Speed Discipline | 7 | Stagger animation adds JS dependency; manageable but not zero-cost |

**Weighted Average: 7.6 — WINNER (Rank 4, after penalty)**

---

### Direction 3: Authority Margin

| Criterion | Score | Justification |
|-----------|-------|---------------|
| Offer Clarity | 9 | Restrained design forces headline to carry full weight; nothing competes |
| Credibility / Proof Density | 8 | Featured testimonial above fold is powerful; fewer logos may feel thin to planners who need bulk proof |
| Conversion Path | 9 | Single-column removes decision paralysis; CTA placement is deliberate |
| Mobile Polish | 10 | Single column is native mobile format; no adaptation overhead |
| Speed Discipline | 10 | Lightest CSS footprint of any direction; fastest load |

**Weighted Average: 9.2 — WINNER (Rank 2, tiebreak: greater mobile advantage)**

---

### Direction 4: Stage Presence

| Criterion | Score | Justification |
|-----------|-------|---------------|
| Offer Clarity | 8 | Dramatic and clear; but full-bleed image risks attention capture over message capture |
| Credibility / Proof Density | 7 | Award badge in hero is strong; rest of proof below fold |
| Conversion Path | 7 | Dark sections can obscure CTA color contrast if not managed carefully |
| Mobile Polish | 7 | Full-bleed hero is challenging at < 400px; requires careful art direction |
| Speed Discipline | 6 | Full-bleed imagery requires significant image optimization work; LCP risk |

**Weighted Average: 7.0 — Near threshold, not selected**

---

### Direction 5: Signal + Space

| Criterion | Score | Justification |
|-----------|-------|---------------|
| Offer Clarity | 8 | Asymmetric layout is distinctive; headline reads clearly |
| Credibility / Proof Density | 7 | Editorial proof is powerful but sparse above fold; planners who scan logos need more |
| Conversion Path | 8 | CTAs are clear; mauve accent is distinctive enough to draw attention |
| Mobile Polish | 8 | Wide-margin editorial works well at mobile scale with reduced margins |
| Speed Discipline | 8 | Minimal dependencies; warm filter CSS-achievable |

**Weighted Average: 7.8 — WINNER (Rank 3)**

---

## Final Ranking Table

| Rank | Direction | Avg Score | Status | Color Identity |
|------|-----------|-----------|--------|----------------|
| 1 | Proof Architecture | 9.2 | WINNER | Slate + Terracotta |
| 2 | Authority Margin | 9.2 | WINNER | Ink + Pine Green |
| 3 | Signal + Space | 7.8 | WINNER | Graphite + Mauve |
| 4 | Momentum Signal | 7.6 | Near threshold |
| 5 | Stage Presence | 7.0 | Not selected |

---

## Top 3 Rationale

### Rank 1: Proof Architecture (9.2)
The only direction that achieves proof above the fold without sacrificing clarity. The left/right hero split positions Anne's portrait as the authority signal while the headline does the persuasion work. The immediate proof bar means a planner who lands on this page gets their three key questions answered (Who is this?, Is she credible?, How do I book?) in a single viewport. Terracotta accent is decisively different from all competitors.

### Rank 2: Authority Margin (9.2)
Tied on score but ranked second because its strength is concentrated in speed, mobile, and restraint — which makes it the safest direction for WordPress implementation and the fastest to load. The green/ink color system is elegant and corporate-premium without being generic. The single-column format will survive any WordPress block editor constraint cleanly. Best choice if the client wants a "less is more" execution that actually means it.

### Rank 3: Signal + Space (7.8)
The most visually distinctive of the three. The Cormorant/Satoshi pairing and mauve accent give AGG a visual identity no competitor has. Marginally lower on proof density above fold, which is the only reason it doesn't rank higher. If the client selects this direction, the proof bar in the hero zone should be strengthened.

---

## Implementation Priority Note

All three directions should be prototyped. Rank 1 is recommended as the primary recommendation to present to the client. Rank 2 is the "safe choice" for conservative clients. Rank 3 is the "distinctive choice" that requires the most design confidence to commit to.
