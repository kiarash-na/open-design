# Kiarash

> Category: Personal Brand
> Adventurer & Entrepreneur. Dark, bold, minimal personal brand built on
> high-contrast typography, a signature "K" lettermark, and restrained
> accent color usage. Designed for social carousels, slide decks, and
> presentation artifacts.

## 1. Visual Theme & Atmosphere

Kiarash carries the energy of someone who builds and explores — a personal
brand that feels sharp, intentional, and quietly confident. The visual system
is built on a near-black canvas with white and orange as the primary voice,
allowing content to land with impact without visual noise.

The signature element is the **"K" lettermark** — a bold geometric K in
**Orbitron** that appears as a watermark, logo mark, and structural accent.
It is never decorative; it is the brand's fingerprint. The K must always
render in Orbitron — never in Geist or any other typeface.

A **thin left vertical border line** (1px) runs as a structural spine on
slide layouts — a quiet editorial device that grounds the composition without
competing for attention.

**Key Characteristics:**
- Dark-first canvas (`#121212` Dark Coal) with white type and orange accents
- Orbitron (geometric, futuristic display) for headlines and brand moments
- Geist (clean, modern sans) for body, labels, and UI text
- Sharp Orange (`#F85028`) as the single energetic accent — used sparingly
- Army Green (`#6F8557`) as a quiet secondary accent for depth and contrast
- "K" lettermark watermark at low opacity on dark backgrounds
- Left-edge vertical hairline as a compositional anchor
- High contrast, generous whitespace, zero decorative clutter

## 2. Color Palette & Roles

### Primary
- **Dark Coal** (`#121212`): The default canvas. Used for slide backgrounds,
  dark sections, and hero panels. True near-black — not pure `#000000`.
- **Bright White** (`#ffffff`): Primary text on dark, card backgrounds on
  light surfaces, and inverse elements.
- **Sharp Orange** (`#F85028`): The brand's energetic accent. Used for the
  "K" logo, eyebrow labels, CTAs, and single focal points per slide.
  Never as a background fill. Never more than one orange element per
  ~800×800px viewport.

### Secondary & Accent
- **Army Green** (`#6F8557`): Quiet secondary accent. Used for the
  "Entrepreneur" word in the lockup, watermark tints, and subtle
  compositional depth. Never competes with Sharp Orange.
- **Basic Beige** (`#F7DF9B`): Warm tertiary accent. Used sparingly for
  highlight badges, tag backgrounds, or warm contrast moments. Jewelry,
  not structural.
- **Elite Blue** (`#28367B`): Deep accent for data callouts, stat panels,
  or night-themed slides. Used rarely — once per deck at most.

### Neutral Scale
- **Charcoal** (`#1f1f1f`): Slightly lifted dark for card surfaces on
  the Dark Coal canvas.
- **Smoke** (`#2a2a2a`): Elevated surface for nested elements.
- **Body Gray** (`#b0b0b0`): Secondary body text on dark backgrounds.
- **Mute Gray** (`#6b6b6b`): Captions, metadata, timestamps.
- **Hairline** (`#333333`): 1px divider and border color on dark surfaces.

### Surface Modes
- **Dark canvas**: `#121212` — the default. Every slide starts here.
- **Light canvas**: `#ffffff` — used for contrast slides only (e.g., a
  single white slide in a dark deck for emphasis).
- **Card surface (dark)**: `#1f1f1f` — cards, stat blocks, quote panels
  on the dark canvas.
- **Card surface (light)**: `#f5f5f5` — cards on white surfaces.

### Color Rules
- One **Sharp Orange** moment per slide. If a slide has an orange CTA,
  the eyebrow stays white or Army Green.
- Army Green is a companion, not a competitor. It never shares a slide
  with Sharp Orange as an equal-weight element.
- Pure black (`#000000`) is forbidden. Dark Coal (`#121212`) is the floor.
- No gradients on backgrounds or text. Solid blocks only.

## 3. Typography Rules

### Font Families
- **Display / Brand:** `Orbitron` — geometric, futuristic sans-serif.
  Weights 600 (H1), 700 (brand/display). Fallback: `'Exo 2', 'Eurostile', sans-serif`.
- **Body / UI:** `Geist` — clean, modern sans-serif. Weights 400 (body),
  500 (lead, buttons, labels), 600 (H2–H4). Fallback: `'Inter', -apple-system, sans-serif`.
- **Mono:** `Geist Mono` or `JetBrains Mono` — code spans, stats, coordinates.

### Hierarchy

| Role | Font | Size (D/M) | Weight | Line Height | Letter Spacing | Notes |
|---|---|---|---|---|---|---|
| Brand Display | Orbitron | 64px / 36px | 700 | 1.05 | -0.02em | Hero name / lockup |
| H1 | Orbitron | 48px / 32px | 600 | 1.10 | -0.01em | Section headlines |
| H2 | Geist | 32px / 24px | 600 | 1.15 | -0.01em | Sub-section heads |
| H3 | Geist | 24px / 24px | 600 | 1.20 | 0 | Card titles, module heads |
| H4 | Geist | 20px / 20px | 500 | 1.25 | 0 | Labels, small headers |
| Lead | Geist | 18px / 18px | 500 | 1.40 | 0 | Intro paragraphs, deck text |
| Body | Geist | 16px / 15px | 400 | 1.50 | 0 | Standard reading text |
| Button / Label | Geist | 14px / 14px | 500 | 1.25 | 0.02em | CTAs, tags, pills |
| Caption | Geist | 12px / 12px | 400 | 1.40 | 0.01em | Metadata, footnotes |

### Principles
- **Orbitron is the brand voice.** It carries the futuristic, builder
  energy. Use it for the name lockup, hero headlines, and deck title
  slides only. Never for body text.
- **Geist does the work.** All body, labels, captions, and secondary
  hierarchy use Geist. It stays clean and gets out of the way.
- **Weight contrast creates hierarchy.** Display uses 600–700; body uses
  400–500. Avoid middle-weight mush.
- **Letter-spacing is tight on display, neutral on body.** Orbitron at
  large sizes gets `-0.02em` to feel machined and intentional.

## 4. Spacing & Grid

### Spacing Scale
- **Base unit:** 8px.
- **Scale:** 4, 8, 12, 16, 20, 24, 32, 40, 48, 64, 80, 96px.

### Slide Grid (for carousels and decks)
- **Canvas:** 1080×1080px (square social) or 1080×1350px (portrait carousel)
  or 1920×1080px (presentation deck).
- **Safe margin:** 64px from all edges on desktop / 40px on mobile.
- **Left spine:** A 1px vertical hairline at 64px from the left edge
  (desktop) or 40px (mobile), running from top margin to bottom margin.
  Color: `#333333` on dark canvas, `#e5e5e5` on light canvas.
- **Content column:** Starts 32px to the right of the spine line.

### Vertical Rhythm
- Section spacing: 48–64px between major content blocks.
- Headline to subtext: 16–20px.
- Subtext to CTA: 24–32px.
- Card internal padding: 24–32px.

## 5. Layout & Composition

### Slide Types

**Title Slide**
- Dark Coal background.
- Large "K" watermark in Orbitron at ~8% opacity, positioned
  bottom-right or center-right. The K must always be Orbitron.
- Name in Orbitron 700 at Brand Display size, left-aligned above
  the content column.
- Tagline below: "Adventurer & Entrepreneur" — "Adventurer &" in
  Bright White, "Entrepreneur" in Army Green.
- Small "K" logo in Orbitron, Sharp Orange, at bottom-left corner.
- Left spine line present.

**Content Slide**
- Dark Coal background (default) or White background (contrast).
- Section title in Orbitron 600 (H1) or Geist 600 (H2), left-aligned.
- Body content in Geist 400, left-aligned or in a 2-column grid.
- Optional stat callout: large number in Orbitron 700, label in
  Geist 500 Caption.
- Left spine line present.

**Stat / Data Slide**
- Dark Coal background with Charcoal (`#1f1f1f`) card surfaces.
- Large metric in Orbitron 700, 64px, Bright White.
- Label in Geist 500, 14px, Mute Gray.
- Up to 3 stats per slide, evenly distributed.
- Optional Elite Blue (`#28367B`) accent bar behind one stat.

**Quote Slide**
- Dark Coal or Charcoal background.
- Quote text in Geist 500, Lead size, Bright White.
- Attribution in Geist 400, Caption size, Mute Gray.
- Left spine line thicker (2px) in Sharp Orange for emphasis.

**Closing / CTA Slide**
- Dark Coal background.
- "K" watermark in Orbitron, Army Green at low opacity.
- Single CTA text in Orbitron 600, H1 size, Sharp Orange.
- URL or handle in Geist 400, Body size, Body Gray.

### Compositional Rules
- **Top-biased:** Content sits in the upper 60% of the slide. Never
  center-vertically unless it's a single stat or logo.
- **Asymmetric balance:** The left spine creates a strong left anchor;
  counterweight with the K watermark or a large element on the right.
- **One focal point per slide:** Either a headline, a stat, a quote, or
  a CTA — never all four.

## 6. Components

### The "K" Lettermark

The K is always **Orbitron 700**. It is never Geist, never another weight,
and never another typeface. The K is a single glyph — not a custom-drawn
logo — so the font *is* the mark.

- **Watermark:** Large Orbitron 700 K, low-opacity (5–10%), Army Green
  or Charcoal. Used as a background texture on title and closing slides.
- **Logo mark:** Small Orbitron 700 K, Sharp Orange, positioned at
  bottom-left corner of slides. Size: 32–40px.
- **Icon:** Orbitron 700 K in White or Sharp Orange on dark; Dark Coal
  or Sharp Orange on light. Used for profile avatars, favicons, and
  app icons.

### Eyebrow Label
- Geist 500, 14px, uppercase, Sharp Orange.
- Prefixed with a 24px horizontal line in Sharp Orange.
- Used above headlines to denote slide topics or sections.

### Stat Block
- Large number: Orbitron 700, 48–64px, Bright White.
- Label: Geist 500, 14px, Mute Gray.
- Optional: a 4px horizontal accent bar in Sharp Orange or Elite Blue
  beneath the number.

### Quote Block
- Opening quote mark in Sharp Orange, Orbitron 700, 48px.
- Quote text in Geist 500, Lead size, Bright White.
- Attribution in Geist 400, Caption size, Mute Gray, prefixed with
  an em-dash.

### Tag / Pill
- Geist 500, 12–14px, uppercase, 0.02em letter-spacing.
- Background: transparent with 1px `#333333` border (dark) or
  `#e5e5e5` border (light).
- Active/Highlight: Sharp Orange background, Bright White text.
- Radius: 4px (minimal, not pill-shaped — this is a sharp brand).

## 7. Motion & Interaction

- **Transitions:** 150–200ms ease. Keep them subtle and functional.
- **Slide transitions (decks):** A simple fade or a left-to-right wipe
  at 300ms. No bounces, no elastic easing.
- **Text reveals:** Fade-in + translateY(8px → 0) at 200ms ease-out.
  Stagger headline → subtext → CTA by 80ms.
- **Stat count-up:** Numbers animate from 0 to final value over 600ms
  with ease-out. Optional.
- **K watermark:** Subtle pulse or opacity breathe (0.08 → 0.12) on
  title slides, 4s cycle. Optional and minimal.
- **No parallax, no scroll-jacking, no auto-play video.** The brand
  is still and confident.

## 8. Voice & Brand

- **Tone:** Direct, confident, understated. No hype, no filler.
- **Headlines:** Short. One idea per line. Let whitespace speak.
- **Microcopy:** Action-oriented. "Build." "Explore." "Ship." Not
  "Let's get started on your journey."
- **No emoji in brand copy.** The K lettermark is the only symbol.
- **Case:** Title case for headlines. Sentence case for body. UPPERCASE
  only for eyebrow labels and tags.
- **Numbers:** Use real numbers. "12 countries." "8 products." Not
  "a dozen."

## 9. Anti-patterns

- ❌ Do not use pure black (`#000000`). Dark Coal (`#121212`) is the floor.
- ❌ Do not use more than one Sharp Orange element per slide.
- ❌ Do not use Orbitron for body text or captions. It is display-only.
- ❌ Do not add decorative gradients, glows, or shadows. Solid blocks only.
- ❌ Do not center-align body text. Left-align everything except single
  stats and centered CTAs.
- ❌ Do not use rounded corners larger than 8px. This is a sharp brand.
- ❌ Do not place the K watermark at full opacity. It is a texture, not
  a foreground element.
- ❌ Do not render the "K" lettermark in any font other than Orbitron.
  Geist K ≠ brand K.
- ❌ Do not use Army Green and Sharp Orange as equals on the same slide.
  One leads; the other supports.
- ❌ No more than three type sizes per slide.

## 10. Agent Prompt Guide

### Quick Reference
- **Background:** Dark Coal (`#121212`)
- **Text:** Bright White (`#ffffff`)
- **Primary accent:** Sharp Orange (`#F85028`)
- **Secondary accent:** Army Green (`#6F8557`)
- **Display font:** Orbitron 600–700
- **Body font:** Geist 400–600
- **K lettermark:** Orbitron 700 only — never Geist, never another weight
- **Spine line:** 1px `#333333`, 64px from left edge

### Example Prompts
1. *"Create a title slide: Dark Coal background, large K watermark in
   Orbitron 700, Army Green at 8% opacity, bottom-right. 'Kiarash' in
   Orbitron 700 64px Bright White, left-aligned. Below: 'Adventurer &' in
   Bright White Geist 500 18px, 'Entrepreneur' in Army Green Geist 500 18px.
   Small orange K logo in Orbitron 700 32px bottom-left. Left spine line
   1px #333333."*

2. *"Design a 3-stat slide: Dark Coal background. Three Charcoal cards
   with 24px padding. Each card: large number in Orbitron 700 48px
   White, label in Geist 500 14px Mute Gray. First stat has a 4px
   Sharp Orange underline. Left spine line present."*

3. *"Build a quote slide: Dark Coal background. Opening quote mark
   in Sharp Orange Orbitron 48px. Quote in Geist 500 18px White.
   Attribution in Geist 400 12px Mute Gray with em-dash. Left spine
   line 2px Sharp Orange."*

4. *"Create a closing CTA slide: Dark Coal, K watermark in Orbitron
   700, Army Green at 6% opacity, bottom-right. 'Let's build.' in
   Orbitron 600 48px Sharp Orange. '@kiarash' in Geist 400 16px Body
   Gray below. Small orange K in Orbitron 700 32px bottom-left."*

5. *"Design a content slide with 2-column layout: Dark Coal background.
   Left column: eyebrow label 'PHILOSOPHY' in Sharp Orange Geist 500
   14px uppercase with orange line prefix. H2 headline in Geist 600
   32px White. Right column: body text in Geist 400 16px Body Gray.
   Left spine line present."*
