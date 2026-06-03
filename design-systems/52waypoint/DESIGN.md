# 52Waypoint Design System

> Category: Brutalist · Editorial
> A monochrome dark system with a single high-energy orange. Sharp corners
> only, hairline borders, flat surfaces, and a colophon-style discipline
> borrowed from printed manuals. Interactions are mostly **ghost → orange**
> color shifts on hover.
> One-liner: *52 steps to build and launch your idea.*
> Moto: *This community is your capital.*

**Canonical visual reference:** Always cross-check against the live site
[**52waypoint.com**](https://52waypoint.com). The brand docs are the
written intent; the live site is the calibrated execution. When the two
disagree, the live site wins (see Buttons, where the brand doc describes
a filled-orange primary but the deployed product uses ghost CTAs that
transition border + text to orange on hover).

I-Lang resolution (for downstream agents):

```
[PLAN:@DESIGN|type=52waypoint]
  |palette=monochrome_dark_custom|accent=waypoint_orange
  |typography=ibm_plex_sans|display=bebas_neue|mono=ibm_plex_mono
  |layout=single_column|max_width=1400px
  |mood=brutalist
  |density=spacious|section_gap=128px|content_padding=32px
  |motion=minimal_elegant|gsap_scrolltrigger=true|lenis_smooth=true
  |exclude=shadows,gradients,rounded_corners,additional_accents,filled_primary_buttons
  |responsive=mobile_first
```

## 1. Visual Theme & Atmosphere

- **Mood:** brutalist with editorial discipline — exposed structure, raw
  typography, colophon-style metadata.
- **Feel:** direct, encouraging, practical, honest. A printed founder's
  manual that happens to deploy. Confident, restrained, signal-over-noise.
- **Reference:** [52waypoint.com](https://52waypoint.com) — the canonical
  source. Open it before any visual decision; it shows the calibrated
  spacing, typography weights, motion timing, and the ghost-CTA pattern
  that the brand tokens alone do not capture.
- **Posture:** left-aligned by default; hero headlines centered only.
- **Reading rhythm:** uppercase Bebas Neue display walks the eye like
  printed chapter heads; mono-spaced labels mark every section like a
  field manual.
- **Color ratio:** **60% black** (Void Black backgrounds) ·
  **30% gray** (Deep Gray surfaces, Signal White text, Muted Text labels) ·
  **10% orange** (Waypoint Orange — used as an *interaction signal*, not
  as a fill: borders, active states, text on hover, dot-nav, selection).

## 2. Color Palette & Roles

All values are tokens. Do not invent new hex.

### Dark mode (primary surface)

- **Background — Void Black:** `#0A0A0A` — page canvas, hero, dark mode base.
- **Surface — Deep Gray:** `#141414` — card backgrounds, elevated surfaces.
- **Surface alt — Surface Gray:** `#1E1E1E` — input fields, secondary cards,
  hover states.
- **Text primary — Signal White:** `#F0F0F0` — headings, body, hero type.
- **Text secondary — Muted Text:** `#555555` — labels, timestamps, captions.
  Use **at 12px+ only** (smaller sizes fail WCAG AA on Void Black).
- **Border — Border Gray:** `#333333` — dividers, hairline rules, grid lines,
  scrollbar thumb, inactive dot-nav. In Tailwind use `border-foreground/20`
  for ghost CTAs (the live convention).
- **Accent — Waypoint Orange:** `#E8783A` — interactions, active states,
  selection, dot-nav active, the `52` mark in the wordmark. The hover
  *target* color, not a fill color.
- **Selection:** background `#E8783A`, text `#0A0A0A`.

### Light mode (print, fallback)

- **Background — Warm White:** `#FAF8F6` — light backgrounds, print materials.
- **Text primary — Ink Black:** `#1A1A1A` — body, headings on light surfaces.
- **Border — Soft Gray:** `#E0E0E0` — hairlines on light surfaces.
- **Accent stays:** `#E8783A` (orange behaves the same in both modes).

### Contrast best practices (override unsafe brand defaults)

Best practice trumps the literal brand token table when the table
produces unreadable combinations. The following minimums are enforced:

| Combination | Ratio | Verdict | Rule |
|---|---|---|---|
| `#F0F0F0` Signal White on `#0A0A0A` Void Black | ~18.4:1 | AAA | Use freely for body and headings. |
| `#F0F0F0` Signal White on `#141414` Deep Gray | ~16.0:1 | AAA | Use freely on cards. |
| `#CCCCCC` on `#0A0A0A` | ~13.5:1 | AAA | Recommended for community-card body text. |
| `#888888` on `#0A0A0A` | ~6.4:1 | AA | **Preferred for small (10–12px) muted labels** instead of `#555555`. |
| `#555555` on `#0A0A0A` | ~4.04:1 | AA Large only | Allowed only at 18pt+ regular or 14pt+ bold. **Do NOT use for body, helper text, captions under 18pt.** |
| `#555555` on `#FAF8F6` | ~7.6:1 | AAA | Safe on the light mode surface. |
| `#E8783A` on `#0A0A0A` | ~6.85:1 | AA | Safe for labels and interactive text. |
| `#0A0A0A` on `#E8783A` (orange fill) | ~6.85:1 | AA | Reserved — see Buttons; ghost is preferred. |

### Color rules

- Waypoint Orange is **an interaction signal** — ghost borders, text on
  hover, selection, dot-nav active. Never a background fill except in
  the rare jewelry case (selection highlight, dot-nav dot, the `52`
  glyph). Maximum ≤10% of surface per viewport.
- Never introduce additional accent colors beyond the defined palette.
- Pure white is forbidden — Signal White `#F0F0F0` is the brightest value.
- Pure black is forbidden — Void Black `#0A0A0A` is the darkest value.
- For any muted text under 18pt, **promote `#555555` to `#888888`** to
  meet AA. The original `#555555` token survives for 18pt+ labels only.

## 3. Typography Rules

### Font stack

| Role | Family | Fallbacks | Use |
|---|---|---|---|
| **Display** | Bebas Neue | DejaVu Sans Condensed, Arial Narrow, Impact, sans-serif | Headlines, section heads, step numbers — uppercase only |
| **Body** | IBM Plex Sans | DejaVu Sans, Liberation Sans, Arial, sans-serif | Paragraph copy, UI text, descriptions (300/400/500/600) |
| **Mono** | IBM Plex Mono | DejaVu Sans Mono, Liberation Mono, Courier, monospace | Labels, captions, metadata, button text, code (400/500) |

Loaded in `src/app/layout.tsx` via `next/font/google` as `--font-ibm-plex-sans`,
`--font-ibm-plex-mono`, and `--font-bebas`. Body class applies
`font-sans antialiased`. Always include `font-display: swap` and the
full fallback stack — Bebas Neue especially benefits from a condensed
fallback (`Arial Narrow`, `Impact`) so layout doesn't reflow when the
font arrives.

### Type scale

| Level | Size | Family | Weight | Case | Tracking | Line height |
|---|---|---|---|---|---|---|
| Display XL | `clamp(3rem, 8vw, 5.5rem)` (48–88px) | Bebas Neue | 400 | UPPERCASE | +0.04em | 0.95 |
| Display | `clamp(2.5rem, 5vw, 4.5rem)` | Bebas Neue | 400 | UPPERCASE | -0.01em | 1.0 |
| Heading | `clamp(1.5rem, 3vw, 3rem)` | Bebas Neue | 400 | UPPERCASE | -0.01em | 1.05 |
| Subheading | `clamp(1rem, 3vw, 2rem)` | Bebas Neue | 400 | UPPERCASE | +0.04em | 1.2 |
| Body | 14–16px (`text-sm` / `text-base`) | IBM Plex Sans | 400 | — | — | 1.65 |
| Caption / Helper | 12–13px (`text-xs`) | IBM Plex Mono | 400 | — | +0.05em | 1.5 |
| Eyebrow / Label | 10–11px | IBM Plex Mono | 400 | UPPERCASE | +0.30em | 1.4 |
| Micro | 9–10px | IBM Plex Mono | 400 | UPPERCASE | +0.20em | 1.4 |

> **Note:** The brand-tokens.json scale uses pt values
> (`8pt`, `7pt`) which render too small on web. The table above translates
> to web px and respects 12px-minimum-for-Muted-Text. Use these values,
> not the raw brand-tokens.json.

### Microcopy conventions (live in the wild)

- **Eyebrow / section label:** `font-mono text-[10px] uppercase tracking-[0.3em] text-accent` — orange, +0.30em tracking. Always opens a section.
- **Nav links:** `font-mono text-xs uppercase tracking-[0.3em] text-muted-foreground hover:text-accent transition-colors`.
- **Step labels:** `font-mono text-[10px] uppercase tracking-[0.3em] text-muted-foreground`.
- **CTA text:** `font-mono text-xs uppercase tracking-widest text-foreground`.

### Voice

Direct, encouraging, practical, honest — *knowledgeable friend who's
been there*. Speaks in "Step X" not "Phase Two, Subsection B".
Use **build** not develop, **ship** not deploy, **validate** not verify,
**launch** not go live, **community** not network. Forbidden: synergy,
leverage, disruption, revolutionary, empower, game-changer,
best-in-class, unlock your potential, AI-powered (unless literally true).

## 4. Component Stylings

### Buttons — the live pattern

**Primary CTA is GHOST, not filled.** The brand-tokens.json describes a
filled-orange primary, but the deployed product uses a ghost button that
transitions border + text to orange on hover — because on a Void Black
canvas, the orange border + orange text reads *as* the orange button,
and the canvas does the work of the fill. This is the canonical CTA.

```html
<a class="group inline-flex items-center gap-3 border border-foreground/20
          px-6 py-3 font-mono text-xs uppercase tracking-widest
          text-foreground transition-all duration-200
          hover:border-accent hover:text-accent">
  <span>Start Step 1</span>
  <BitmapChevron class="transition-transform duration-[400ms] ease-in-out
                        group-hover:rotate-45" />
</a>
```

- Background: transparent
- Border: `1px solid rgba(240,240,240,0.2)` (= `border-foreground/20`)
- Text: `#F0F0F0` (Signal White)
- Font: IBM Plex Mono, 12px (`text-xs`), UPPERCASE, +0.10em (`tracking-widest`)
- Border-radius: `0` (inherits global `--radius: 0rem`)
- Padding: `px-6 py-3` (24px × 12px)
- Transition: `transition-all duration-200`
- **Hover:** border → `#E8783A`, text → `#E8783A`. *Both shift together.*
- Optional decoration: a `BitmapChevron` icon that rotates 45° on
  group-hover; optional `ScrambleTextOnHover` on the label.

**Secondary CTA (text-only link):** `font-mono text-xs uppercase tracking-widest text-muted-foreground hover:text-foreground transition-colors`. No border. Used for `Learn More`, `Cancel`, etc.

**Filled-orange button (rare, intentional):** reserved for the *single*
strongest action per page if a higher-emphasis button is truly needed
(e.g. a paid CTA, a destructive confirm). When used: bg `#E8783A`, text
`#0A0A0A`, 1px solid `#E8783A`, 0 radius, no shadow, no hover darken —
the page rarely needs this and the ghost button is correct ~95% of the
time.

### Step Card

- Background: `#141414`
- Border: `1px solid #333333`
- Border-radius: `0px`
- Step number: 24pt IBM Plex Mono, `#F0F0F0` at 5% opacity, right-aligned
- Step label: 10px IBM Plex Mono, `#E8783A`, UPPERCASE, +0.30em
- Title: Bebas Neue clamp(1.25rem, 3vw, 2rem), UPPERCASE
- Description: 13–14px IBM Plex Sans, `#CCCCCC` (NOT `#555555` — too low contrast at this size)
- Meta: 10px IBM Plex Mono, `#888888`, UPPERCASE (lifted from `#555555` for AA)

### Community Post Card

- Background: `#0A0A0A`
- Border: `1px solid #333333`
- Avatar: 24px square (never circular), `#E8783A` background, initials in `#0A0A0A`
- Username: 13–14px IBM Plex Sans, `#F0F0F0`, weight 500
- Meta line: 11px IBM Plex Mono, `#888888`
- Body text: 13–14px IBM Plex Sans, `#CCCCCC`
- Footer: 10px IBM Plex Mono, `#888888`, UPPERCASE

### Input (from `NewsletterSignup` in the live repo)

```html
<input class="rounded-none border-foreground/20 bg-transparent
              font-mono text-sm placeholder:text-muted-foreground/50
              focus-visible:border-accent focus-visible:ring-accent/20" />
```

- Background: transparent (on dark canvas) or `#1E1E1E` on cards
- Text: `#F0F0F0`
- Placeholder: `#555555` at 50% opacity → effectively `#888888`-equivalent
- Border: `1px solid rgba(240,240,240,0.2)` (`border-foreground/20`)
- Border-radius: `0`
- Font: IBM Plex Mono, 14px (`text-sm`)
- Focus: border → `#E8783A`, ring `accent/20` (no glow elsewhere)

### Dot Navigation

- Position: vertical, left viewport edge, one dot per section
- Size: 5–6px circles
- Inactive: `#333333`
- Active: `#E8783A`
- Spacing: 12–16px between dots

### Scrollbar

- Width: 10px
- Track: `#0A0A0A`
- Thumb: `#333333`
- Thumb hover: `#555555`
- Border-radius: `0px`

## 5. Layout Principles

- **Max content width:** `1400px`
- **Horizontal padding:** desktop uses `pl-6 md:pl-28 pr-6 md:pr-12`
  (24px mobile, 112px-left / 48px-right desktop) — the asymmetric
  padding reserves room for the left-edge dot-nav.
- **Section spacing:** `py-32` desktop = 128px; `py-24` for tighter sections.
- **Grid:** flexible, content-driven; CSS Grid with task-specific column ratios.
- **Alignment:** mostly left-aligned; alternating left/right alignment
  in principle lists for editorial rhythm.
- **Side rails:** vertical dot-nav fixed on the left viewport edge (≥1024px),
  via `<SideNav />`.
- **Hero canvas:** Void Black `#0A0A0A` with `60px` grid pattern overlay
  via `.grid-bg` (fixed inset-0, opacity 0.3), plus a fixed full-viewport
  SVG noise overlay at 3% opacity via `.noise-overlay`. Both are required
  on every page.

### Grid pattern (from `globals.css`)

```css
.grid-bg {
  background-image:
    linear-gradient(to right,  oklch(0.2 0 0) 1px, transparent 1px),
    linear-gradient(to bottom, oklch(0.2 0 0) 1px, transparent 1px);
  background-size: 60px 60px;
}
```

### Noise overlay (from `globals.css`)

Fixed, `pointer-events: none`, `z-index: 1000`, `opacity: 0.03`, SVG
`feTurbulence type="fractalNoise"` at `baseFrequency=0.9`, 4 octaves.

## 6. Depth & Elevation

- **Shadows:** **none.** Flat design only. Depth comes from borders and
  background layers (`#0A0A0A` → `#141414` → `#1E1E1E`), never from shadow.
- **Borders:** hairline `1px` only.
  - Dark surfaces: `#333333` or `border-foreground/20`
  - Light surfaces: `#E0E0E0`
  - Accent emphasis: `#E8783A`
- **Elevation strategy:** swap the background fill, never add a shadow.
  - Base: `#0A0A0A`
  - Card: `#141414`
  - Card-on-card / input: `#1E1E1E`
- **Border-radius:** **`0px` on everything.** No exceptions — not buttons,
  not cards, not inputs, not images, not avatars. Tailwind: never use
  `rounded-*`; the `--radius` CSS var is `0rem`.

## 7. Motion & Interaction

Motion is **minimal, elegant, and load-bearing** — never decorative.
Every animation either reveals content on scroll, gives feedback on
hover, or sets a slow ambient mood (smooth scrolling, drifting noise).

### Stack

- **GSAP + ScrollTrigger** — page-section reveals and scroll-tied parallax.
- **Lenis** — page-level smooth scroll (attached globally via
  `<SmoothScrollAttach />`).
- **Motion** (Framer Motion) — small UI transitions where GSAP is heavy.
- **Tailwind transitions** — micro-interactions on hover/focus.

### Canonical patterns (live in `_components/`)

**Slide-in-from-side on scroll** — headers and section blocks:

```ts
gsap.from(el, {
  x: -60,           // or x: -80/+80 for alternating
  opacity: 0,
  duration: 1,
  ease: "power3.out",
  scrollTrigger: {
    trigger: el,
    start: "top 85%",
    toggleActions: "play none none reverse",
  },
});
```

**Alternating L/R slide-in** — used in PrinciplesSection where each
item's `align` is `left` or `right`; matching elements come in from
their aligned side at `x: ±80`, `opacity: 0`, `duration: 1`.

**Scroll-tied parallax / fade-out** — Hero content fades and lifts as
the user scrolls past it (scrub-based, no toggle):

```ts
gsap.to(contentRef.current, {
  y: -100, opacity: 0,
  scrollTrigger: { trigger: section, start: "top top", end: "bottom top", scrub: 1 },
});
```

**Cursor follower** — SignalsSection has a cursor element that gsap-lerps to mouse position with `duration: 0.5`.

**Stagger cards in** — `gsap.fromTo(cards, { x: -100, opacity: 0 }, { ... stagger: 0.1 })`.

### Text effects (custom components)

- `<SplitFlapText speed={80} />` — split-flap mechanical letter reveal,
  used for the `52` and `WAYPOINT` wordmarks.
- `<ScrambleTextOnHover duration={0.6} />` — wraps CTA labels; characters
  scramble on hover then settle.
- `<HighlightText parallaxSpeed={0.6}>` — accent highlight that drifts
  with scroll inside Bebas headlines.
- `<BitmapChevron>` — pixel chevron icon used in CTAs; rotates 45° on
  group-hover via `group-hover:rotate-45` + `duration-[400ms]`.
- `<AnimatedNoise>` — animated grain in hero / large dark sections.
- `<ScrambleText>` and `<DrawText>` — additional reveal effects in
  `_components/draw-text.tsx` and `signals-section.tsx`.

### Timing

- Hover transitions: **200ms**, `ease` default (Tailwind `duration-200`).
- Chevron rotate: **400ms**, ease-in-out.
- Scroll reveals: **1s**, `power3.out`.
- Lenis smooth-scroll default tuning (no aggressive scroll-jacking).

### Do / Don't

- DO use scroll-triggered reveals for first-impression sections; once
  revealed, they should stay revealed unless the user scrolls back up
  past the trigger.
- DO keep hover transitions to color + border only; no scale, no glow.
- DO let the noise overlay and grid sit *still* — they are texture, not
  motion.
- DON'T add bounce, elastic, or back easing — easing is `power3.out` /
  `ease`. Bouncy motion is off-brand.
- DON'T scroll-jack. Lenis is for smoothing wheel input, not for
  trapping the user inside a section.
- DON'T animate above 1.2 seconds for any single element.
- DON'T fire scroll reveals below the first viewport — they should be
  triggered by entering, not preloaded.

## 8. Do's and Don'ts

### Do

- DO use the declared color tokens exclusively.
- DO keep the 60% black / 30% gray / 10% orange ratio per viewport.
- DO maintain `py-32` (128px) between top-level sections.
- DO uppercase every Bebas Neue rendering — it is a display face for UPPERCASE only.
- DO ensure all text meets WCAG AA. Promote `#555555` to `#888888` for any text under 18pt.
- DO use the noise overlay and 60px grid pattern on dark canvases.
- DO ship CTAs as ghost buttons that transition border + text to orange
  on hover — that is the canonical pattern.
- DO check [52waypoint.com](https://52waypoint.com) before introducing
  a new pattern; this design system is calibrated against the deployed
  product, not the brand PDF alone.

### Don't

- DON'T invent colors outside the palette (no new accents, no off-tokens).
- DON'T fill primary buttons with Waypoint Orange by default — use the
  ghost pattern. Filled-orange is the exception, not the rule.
- DON'T use `#555555` Muted Text under 18pt; it fails AA on Void Black.
- DON'T round corners. `border-radius: 0px` is enforced globally.
- DON'T add `box-shadow` or `drop-shadow-*`. Depth comes from layered
  backgrounds.
- DON'T introduce gradients on type, fills, or borders.
- DON'T use more than 2 display/body typefaces. IBM Plex Mono is a
  utility face for labels and code; it does not count toward this limit.
- DON'T use pure white or pure black — Signal White and Void Black are the extremes.
- DON'T animate decoratively. Every animation must serve reveal,
  feedback, or ambient mood — never ornament.
- DON'T use bouncy easings (`back`, `elastic`, `bounce`) — stick with
  `power3.out` / default `ease`.

## 9. Responsive Behavior

- **Strategy:** mobile-first (Tailwind defaults).
- **Breakpoints:** `640px (sm) · 768px (md) · 1024px (lg) · 1280px (xl)`.
- **Mobile (< 640px):** single column, all sections stack vertically.
  Section spacing `py-20` (80px). Side dot-nav hidden. Horizontal padding
  `pl-6 pr-6`. Hero headline `clamp(2.25rem, 9vw, 3.5rem)`.
- **Tablet (640–1023px):** allow 2-column feature grids. Side dot-nav
  hidden. Section spacing `py-24` (96px). Padding `pl-6 pr-6`.
- **Desktop (≥ 1024px):** full layout with `max-width: 1400px`, side
  dot-nav visible, section spacing `py-32` (128px), padding
  `pl-28 pr-12` (asymmetric — left padding reserves space for dot-nav).
- **Images:** fluid, `max-width: 100%`, never upscale; preserve aspect
  ratio; serve via Next.js `<Image>` with appropriate `sizes`.
- **Overflow:** `body { overflow-x: hidden; max-width: 100vw }` is
  required globally to prevent horizontal scroll from grid/noise overlays.

## 10. Agent Prompt Guide

When building or editing 52Waypoint pages, components, or assets:

- **Canonical reference:** check [52waypoint.com](https://52waypoint.com)
  before introducing a pattern or doubting a token. The live site is the
  source of truth; the brand PDF is intent.
- **Palette discipline:** the only colors are
  `#0A0A0A · #141414 · #1E1E1E · #F0F0F0 · #CCCCCC · #888888 · #555555 · #333333 · #E8783A`
  (plus `#FAF8F6 / #1A1A1A / #E0E0E0` for light mode). Do NOT invent new
  hex. Do NOT pull colors from Tailwind defaults (`bg-blue-500`, etc.).
- **Accent rule:** Waypoint Orange is an interaction signal. Use it for
  borders + text on hover, dot-nav active, selection, the `52` glyph,
  and small jewelry — **not** as a background fill. Max 3 orange
  moments per viewport.
- **Buttons are ghost:** default CTA is a transparent button with a
  `border-foreground/20` border that transitions border + text to
  `#E8783A` on hover. Use the snippet in Section 4. Do NOT default to
  filled orange.
- **Sharp corners only:** every element has `border-radius: 0`. Never
  use `rounded-*` Tailwind utilities. The `--radius` token is `0rem`.
- **No shadows:** never apply `box-shadow` or `drop-shadow-*`. Use
  background-layer elevation (`#0A0A0A → #141414 → #1E1E1E`) for depth.
- **No gradients** of any kind — solid fills only.
- **Contrast minimums:** any text under 18pt that sits on Void Black
  uses `#888888` or lighter. `#555555` is allowed only at 18pt+.
- **Typography:** Bebas Neue is **uppercase only**, used for display.
  IBM Plex Sans is the body face. IBM Plex Mono carries labels and
  metadata with letter-spacing — never use it for paragraph copy.
- **Microcopy pattern:** every section opens with an orange Plex Mono
  uppercase eyebrow at ~10px, +0.30em tracking — `font-mono text-[10px]
  uppercase tracking-[0.3em] text-accent`.
- **Logo lockup:** `52` in `#E8783A`, `WAYPOINT` in `#F0F0F0` (dark) or
  `#1A1A1A` (light). Always set in Bebas Neue. Never recreate in other
  fonts. Minimum digital width 120px.
- **Dot navigation:** vertical, left-edge, on every long page. Inactive
  dots `#333333`, active `#E8783A`, 5–6px circles. Reserve left padding
  (`pl-28` desktop) so content doesn't collide with it.
- **Noise + grid:** any full-page background that uses `#0A0A0A` must
  also layer the 60px grid at 4% opacity and the fixed SVG noise at 3%
  opacity. They are part of the canvas, not optional decoration.
- **Motion:** use GSAP + ScrollTrigger for section reveals (1s
  `power3.out`, slide-in from side with opacity 0 → 1). Lenis for
  smooth scroll. Tailwind `transition-all duration-200` for hover.
  See Section 7 for the canonical snippets.
- **Focus:** every interactive element must have a visible
  `:focus-visible` outline — use the `--ring` token (`#E8783A`).
- **Voice:** direct, encouraging, practical, honest. Prefer the Say-This
  column: build / ship / validate / community / steps / launch /
  bootstrap / founder. Avoid: synergy, disruption, revolutionary,
  empower, game-changer, best-in-class, unlock your potential.
- **Anti-patterns:** no rounded corners, no shadows, no gradients,
  no second accent color, no decorative or bouncy animations, no
  carousels for primary content, no stock founder photos, no
  glassmorphism, no neon, no pure white, no pure black, no scroll-
  jacking, no filled-orange primary buttons by default.
