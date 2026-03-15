# 03_Structural_Authority

## Design Thesis
A brutalist-lite, commanding site that makes the content feel rigorous and proven, by using heavy borders, high-contrast color blocking, and removing airy, disjointed elements.

## Typography Pairings & Scale
- **Display:** Cabinet Grotesk (800, 900) – Extremely heavy, authoritative, wide-stance sans-serif.
- **Body:** Satoshi (500, 700) – Highly legible with a slightly heavier base weight to match the borders.
- **Scale:** Aggressive scale jump. Headings hit `8vw` with very tight tracking; body copy remains a solid `1.2rem` to `1.5rem` for lead paragraphs. All caps used extensively for institutional feel.

## Color Tokens
- `--color-bg`: `#f4f4f0` (Newsprint / off-white, reduces screen fatigue while feeling premium)
- `--color-text`: `#000000` (Pure black for maximum authority)
- `--color-accent`: `#ffd800` (Industrial safety yellow, forces attention)
- `--color-dark`: `#000000` (Used for massive inverted blocks)

## Section Structure
1. **Nav & Hero:** Rigid grid. A thick top border grounds the site. The hero is split `60/40` with an uncompromising border separating the title from the greyscale multiply-blended portrait.
2. **Institutional Proof:** A black, horizontal stripe housing greyed-out logos. It acts as a structural foundation for the hero.
3. **Authority Statement:** Stripped of all decoration, just massive quote text centered aggressively in the container.
4. **Keynote Modules:** Set against the industrial yellow background, this section breaks the topics into 3 even columns, separated by strict black borders. It forces the eye downward through the "Outcome" paragraphs.
5. **Literature:** A stark grid pitting standard text lists against a massive, 3D rendered book block.
6. **Form / CTA:** Encased entirely inside a thick black border upon a white container, drawing the eye away from the off-white background directly to the input fields.

## Mobile Behaviors
- The borders adapt: vertical borders (`block-border-right`) on desktop naturally become horizontal borders on mobile.
- The sticky CTA becomes a `100%` width solid block pinned directly to the bottom edge of the device screen.
- Layout goes to a pure, stacked sequence of blocks with no overlapping elements.

## WordPress Mapping Notes
- **FSE implementation:** Theme layout needs to disable "gap" at the body level to ensure borders touch perfectly. 
- The thick black borders (`--border-thick: 3px solid #000`) should be set globally via `theme.json` block supports (border attribute) on Group blocks.
- Background colors should be mapped directly in Global Styles, allowing the user to construct this layout purely by stacking Group blocks with different colors and borders.
