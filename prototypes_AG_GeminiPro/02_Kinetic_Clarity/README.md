# 02_Kinetic_Clarity

## Design Thesis
An energetic, tech-forward site that makes resilience feel active and modern, by using sharp grid lines, subtle CSS motion, and removing heavy, static background colors.

## Typography Pairings & Scale
- **Display:** Outfit (700, 800) – Tech-forward, highly legible geometric sans.
- **Body:** Satoshi (400, 500) – Clean, balanced, neutral.
- **Scale:** High contrast between massive hero statements and disciplined 1.1rem body copy.

## Color Tokens
- `--color-bg`: `#ffffff` (Pure white)
- `--color-text`: `#050b14` (Deep tech-navy)
- `--color-accent`: `#0f62fe` (Electric/Tech Blue)
- `--color-surface`: `#f9fafb` (Soft tech grey for cards)

## Section Structure
1. **Grid Overlay:** A fixed, subtle CSS-driven geometric grid overlays the background to establish a tech-oriented, structured feel.
2. **Hero:** 2-column layout. The left column features a highly clickable primary CTA paired immediately with a micro-proof element (5 stars + "Trusted by 100+ Global Brands").
3. **Trust Ticker:** An infinite CSS-only scroll of client logos (rendered as text for the prototype).
4. **Authority Grid:** A clean metric/statistic pairing with a strong client quote.
5. **Keynote Architectures:** A structured list format with hover interactions, explicitly tying specific topic names to the ultimate audience outcome.
6. **Books:** An overlapping, pseudo-3D arrangement using CSS `transform` on hover to add kinetic energy without heavy JS plugins.
7. **Final CTA:** An inline email capture field mimicking an application or software onboarding flow, speeding up event planner intent.

## Mobile Behaviors
- The sticky CTA transforms into a fixed bottom-bar on mobile viewports.
- The infinite ticker speeds up slightly, and the side-by-side grids stack naturally with CSS Grid.

## WordPress Mapping Notes
- **FSE implementation:** Map the electric blue to `--wp--preset--color--primary`.
- The hover states and infinite ticker should be placed into the theme's `style.css` (or `theme.json` custom CSS node).
- To reproduce the Book stack, use a Group block with absolute positioning for the secondary image block inside.
