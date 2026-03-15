# 01_Editorial_Momentum

## Design Thesis
A stark, high-contrast site that makes the speaker's authority feel undeniable, by using oversized sans-serif typography, massive negative space, and removing traditional corporate block layouts.

## Typography Pairings & Scale
- **Display:** Clash Display (600, 700) – highly structured, commanding, editorial.
- **Body:** Satoshi (400, 500) – highly readable, modern geometric sans.
- **Scale:** 1.333 ratio. Huge H1s (`8vw`) that break traditional constraints to force focus on the primary message.

## Color Tokens
- `--color-bg`: `#fdfdfc` (pure stark white)
- `--color-text`: `#111111` (near black for high contrast)
- `--color-accent`: `#005a9c` (Brand Blue derived from AGG logo)
- `--color-dark`: `#1a1a1a` (for the inverse Speaking Topics section)

## Section Structure
1. **Hero:** Asymmetrical split. Left: massive 3-word hook. Right: stark greyscale portrait intersecting with a geometric grey background block. 
2. **Trust Bar:** Immediate grey-scaled logos right below the hero to establish instant credibility.
3. **Authority Block:** A heavily indented lead paragraph with a bold, stripped-down testimonial acting as a structural pillar.
4. **Speaking Topics:** Inverted to dark mode to command attention. Cards focus purely on "What you get" to answer the event planner's immediate needs.
5. **Books:** Large, overlapping 3D product renders with generous whitespace to increase perceived value.
6. **Final CTA:** A friction-reducing form (just email) to start the availability conversation instantly.

## Mobile Behaviors
- The massive typography scales down to fit viewport widths smoothly using `clamp()`.
- The primary CTA ("Check Availability") becomes a full-width sticky button at the bottom of the screen, ensuring the conversion path is never more than a thumb-tap away.

## WordPress Mapping Notes
- **FSE implementation:** Map Clash Display and Satoshi to `theme.json` typography presets. Use the core `Group` block with a custom `.hero-grid` CSS class for the split layout. 
- Avoid any page builder plugins; this layout relies purely on CSS Grid and Flexbox, which native Gutenberg handles perfectly.
