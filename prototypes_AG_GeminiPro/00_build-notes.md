# WordPress Build Notes & Implementation Checklist

These notes are intended for the eventual WordPress block theme (FSE) build, based on the approved design system.

## 1. Foundation
- **Theme:** Block Theme (FSE) – highly recommended to avoid builder bloat and ensure fast CWV.
- **Global Styles (`theme.json`):** 
  - Ensure the sans-serif font stack is implemented natively (e.g., swapping standard Google fonts for system UI stacks or loading highly optimized web fonts via `font-display: swap`).
  - Map core palette variables explicitly: `--wp--preset--color--primary`, `--wp--preset--color--foreground`, `--wp--preset--color--background`.

## 2. Block Patterns Used Throughout Homepage
To maintain the "Less is more" structure, create the following reusable Block Patterns:
- **Hero Statement Pattern:** A 2-column or wide group block. Contains a giant H1, a subhead, and a Row block housing the Primary and Secondary CTAs.
- **Proof Logobar Pattern:** A group block with zero padding, displaying grayscale SVG logos in a flex row (wrap enabled).
- **Speaker Topic Card Pattern:** A highly standardized card pattern outlining: Feature Name -> Audience Outcome -> Small visual cue.
- **Testimonial Block Pattern:** A stark typographic quote block, stripped of unnecessary background boxes or quotation icons.
- **Sticky Mobile CTA Pattern:** Implement via block metadata or a lightweight custom CSS snippet targeting the header/footer on mobile viewports.

## 3. Asset & Speed Discipline
- **Images:** All hero imagery and book covers must be served as WebP, sized to container queries. Avoid massive background images that block main thread.
- **Video Elements:** If used, defer loading until user interaction or after LCP.
- **Animation:** Use the lightweight CSS classes (`.fade-up`, `.reveal`) instead of heavy JS animation libraries. Apply these classes manually to blocks in the editor under "Advanced -> Additional CSS classes".

## 4. Mobile Polish & Accessibility
- Ensure the Mobile Menu is distraction-free, housing primarily the conversion action ("Book Anne").
- Verify touch targets for all CTA buttons are a minimum of 48x48px.
- Use native WP heading blocks sequentially (H1 -> H2 -> H3) to support SEO and screen readers. 
- Ensure high contrast mode support for the stark editorial palettes.
