---
name: design-system
description: The expert design-system extractor. Turns a live product into committed design tokens, and if the user supplies no screenshots, goes and gets its own evidence, reading the product's actual CSS before trusting any pixel. Used by interview-harness-builder for the design-system.md file; use directly when the user says "extract the design system", "get the real colors", or a prototype's styling looks off-brand.
---

# Design System: the expert extractor

Here's the thing about design systems in this round: everyone else eyedrops a
screenshot and hopes. You have three better sources, and the order matters.

**The extraction ladder: always climb it top down.**

1. **The product's own CSS.** The single best trick in this file. Most big
   products ship their design tokens as CSS custom properties in their public
   stylesheets. Fetch the page, pull the linked CSS, and grep for variables:

   ```bash
   curl -sL https://www.linkedin.com | grep -o 'href="[^"]*\.css[^"]*"' | head -5
   curl -sL <that-css-url> | grep -oE -- '--[a-z-]+:\s*#[0-9A-Fa-f]{3,8}' | sort -u | head -40
   ```

   A hex read from the product's own stylesheet is the answer, not an
   estimate. Mark these `(from product CSS)`, the highest confidence tag this
   skill produces.

   Two upgrades when curl+grep comes back thin:
   - Chrome's `--dump-dom` (zero install, Chrome is already on the Mac) or
     `npx playwright` to inject `getComputedStyle()` and read the rendered
     values sites compute at runtime.
   - Purpose-built extractors before hand-rolling: `npx` the
     `extract-design-system` / `d-extract` CLIs (Playwright crawlers that
     emit tokens.json), or Project Wallace's `css-analyzer` for a full
     CSS-to-tokens breakdown.

2. **Open-sourced design systems and published brand values.** Shopify ships
   Polaris, IBM ships Carbon, Atlassian and GitHub (Primer) publish exact
   token files, and most consumer brands publish press-kit colors. If the
   target product has one, read it before reading any pixel. Mark these
   `(published tokens)`.

3. **Screenshots.** Now, and only now, the pixels: to verify sources 1 and 2
   and to capture what CSS can't tell you: density, hierarchy, how much
   whitespace the product actually tolerates, what the cards feel like.

## No screenshots? Go get your own.

Do not stall the run waiting for the user to paste images. Get evidence
yourself, in this order of preference:

- **Browser tools available** (Claude in Chrome or similar): open the product,
  screenshot the 3 highest-value screens (the main feed/home, one detail
  view, one compose/action state). Logged-out is fine; chrome beats nothing.
- **Headless, zero install:**

  ```bash
  npx -y playwright screenshot --viewport-size=1440,900 https://open.spotify.com spotify-home.png
  ```

  or Chrome directly if installed:

  ```bash
  "/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" --headless --screenshot=out.png --window-size=1440,900 <url>
  ```

- **Nothing works** (no network, no browser): fall back to sources 1-2 plus
  memory, and tag every memory-derived value `(inferred)` so the candidate
  knows exactly where they are exposed. Never present a remembered color as a
  read one: that is gotcha territory, and interviewers who work at the
  company catch it instantly.

User-supplied screenshots still beat self-captured ones (they show the
logged-in product, the real density, the user's actual locale). If they
arrive later, re-verify the tokens against them and note any corrections.

## Reading pixels like an expert, not a tourist

When you do read from images:

- Sample flat, unshadowed regions: button fills, nav bars, page background.
  Never sample text (antialiasing lies) or gradients' midpoints.
- Cross-check every sampled hex against sources 1-2 before committing. If the
  sample says `#0B67C3` and the CSS says `#0A66C2`, the CSS wins.
- Read the background first. It is the token everyone gets wrong (LinkedIn is
  `#F4F2EE`, not white; Spotify's surfaces are `#121212`/`#181818`, not
  black), and it is the token interviewers notice first.
- One value per token, always. "12-16px" is a shrug, not a token.

## Output contract

Emit into `design-system.md`, per interview-harness-builder's checklist: colors (with
per-token confidence tags), type scale with line-heights, radii, spacing unit,
button styles with hover/pressed/disabled/focus as separate values, elevation
with real rgba+blur+offset, iconography, nav pattern, density notes. Unknown
value → write the token anyway, tag `(inferred)`. Contrast claims → computed
ratio or "contrast not verified", never an estimate.

Close with one line naming your strongest and weakest source: "Tokens from
LinkedIn's own CSS plus 3 screenshots; weakest area is elevation, which came
from pixels only."

Live-round note: all of this happens silently. The candidate narrates one
sentence ("pulling their real tokens so the prototype doesn't look pasted
in"); the extraction itself never prints its ladder to the screen.
