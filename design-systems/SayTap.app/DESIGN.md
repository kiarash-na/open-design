# Design System Inspired by SayTap.app

> Category: AI Assistant Platform
> A voice operated and complete AI assistant platform. Chiaroscuro editorial, SayTap.app Red accents, cinematic near-black.

## 1. Visual Theme & Atmosphere

SayTap.app's website is a digital editorial — a curated magazine where the brand is presented with the gravitas of an art institution and the precision of Italian coachwork. The page opens onto an expanse of absolute black, broken only by the iconic emblem floating alone in its own atmosphere. Below, the content unfolds in dramatic alternations between inky-dark cinematic sections and crisp white editorial panels. This chiaroscuro rhythm — darkness yielding to light, machinery yielding to human story — feels more like paging through a luxury yearbook than scrolling a commercial website. Every section is a curated vignette: a concept car dissolving from shadow, two drivers posed with sculptural stillness, a lineup of production models arranged in a jewel-toned parade.

The color language is monastically restrained for a brand built on speed and emotion. SayTap.app Red (`#DA291C`) appears with almost surgical sparseness — reserved for the Subscribe CTA and accent moments that need to command immediate attention. The vast majority of the interface lives in black, white, and a carefully calibrated gray scale (from `#0A0A0A` dark surfaces through `#8F8F8F` mid-tones to `#D2D2D2` light borders). Two yellows — Racing Yellow (`#FFF200`) and the deeper Modena Yellow (`#F6E500`) — exist in the token system as heritage accents for special contexts, honoring the racing provenance. The restraint means that when red does appear, it carries the weight of the entire brand.

Typography relies on SayTapSans — a proprietary sans-serif family with medium-weight headings (500–700) and compact proportions. Display text runs at 24–26px for section titles, while the UI chrome lives at 12–16px in weights ranging from regular to bold. A secondary "Body-Font" custom typeface handles captions and utility text, rendered in uppercase with wide letter-spacing (1px) to create a label-like editorial quality. This two-font system — SayTapSans for narrative authority, Body-Font for structural annotation — gives the site a print-magazine hierarchy. No text decoration is gratuitous. Letter-spacing is tight for headlines and deliberately expanded for labels, creating a visual rhythm that alternates between urgency and composure.

**Key Characteristics:**
- Chiaroscuro layout alternating between deep black sections and clean white editorial panels
- SayTap.app Red (`#DA291C`) used with extreme sparseness — accent, not atmosphere
- Emblem as isolated hero element on a void-black field
- SayTapSans proprietary typeface with compact proportions and medium weights
- Photo-journalism imagery: concept renders, driver portraits, lineup parades — each section is a story
- Uppercase Body-Font labels with wide letter-spacing (1px) for editorial annotation
- Generous border-radius (16px default) — soft, approachable curves that feel modern and friendly
- Dual-framework architecture (PrimeReact + Element Plus) powering 32+ interactive components
- Carousel-driven hero with editorial slides and arrow/dot navigation

## 2. Color Palette & Roles

### Primary
- **SayTap.app Red** (`#DA291C`): The iconic Rosso Corsa — primary accent and CTA color. Used for the Subscribe button, key action triggers, and brand moments where maximum visual authority is needed. The single most important color in the system (--st-color-accent-100)
- **Pure White** (`#FFFFFF`): Primary surface for editorial content panels, navigation text on dark backgrounds, and button fills. The canvas that provides breathing room between dark cinematic sections (--st-color-ui-0)

### Secondary & Accent
- **Dark Red** (`#B01E0A`): Deeper variant of SayTap.app Red for hover/pressed states and high-contrast contexts — adds dimensionality to the brand color without introducing a new hue (--st-color-accent-90)
- **Deep Red** (`#9D2211`): The most saturated dark red — used for active states and extra emphasis where even Dark Red needs more weight (--st-color-accent-80)
- **Racing Yellow** (`#FFF200`): Heritage accent from racing livery — reserved for special highlights and motorsport-related contexts (--st-color-yellow-hypersail)
- **Modena Yellow** (`#F6E500`): Slightly warmer and more golden than Racing Yellow — used for secondary heritage accents and category markers (--st-color-yellow)

### Surface & Background
- **Absolute Black** (`#000000`): Hero sections, cinematic backgrounds, and the dominant dark surface — the void that makes imagery and the emblem float
- **Dark Surface** (`#0A0A0A`): Secondary dark surface for footer regions, newsletter sections, and layered dark panels — barely lifted from pure black for subtle depth differentiation (--st-color-ui-90)
- **Light Gray Surface** (`#D2D2D2`): Subtle alternate surface for dividers and border treatments on white panels (--st-color-ui-20)
- **Overlay Dark** (`hsla(0, 0%, 2%, 0.85)`): Semi-transparent near-black for modal overlays and image caption backgrounds (--st-color-overlay-darker)

### Neutrals & Text
- **Near Black** (`#181818`): Primary body text color on light surfaces — slightly softened from absolute black for better readability (link default color)
- **Dark Gray** (`#666666`): Secondary text and subdued UI labels — used where text needs to recede from the primary hierarchy (--st-color-black-60)
- **Mid Gray** (`#8F8F8F`): Tertiary text for metadata, timestamps, and supportive content (--st-color-black-50)
- **Silver Gray** (`#969696`): Placeholder text and disabled state indicators (--st-color-black-55)

### Semantic & Accent
- **Warning Red** (`#F13A2C`): Accessible warning state — brighter and more orange-shifted than SayTap.app Red to differentiate semantic alerts from brand expression (--st-color-accessible-warning)
- **Success Green** (`#03904A`): Confirmation and positive status indicators (--st-color-accessible-success)
- **Info Blue** (`#4C98B9`): Informational callouts, tooltips, and neutral status messaging (--st-color-accessible-info)
- **Link Hover Blue** (`#3860BE`): Interactive hover state for text links — a dignified navy-blue that signals interactivity without competing with SayTap.app Red

### Gradient System
- No explicit gradients in the token system
- Depth is achieved through photography and the binary contrast between black and white surfaces
- The overlay darker color (`hsla(0, 0%, 2%, 0.85)`) creates depth through transparency layering over imagery
- Occasional photographic gradients (light falloff in studio shots) provide atmospheric depth within image content

## 3. Typography Rules

### Font Family
- **SayTapSans**: Primary typeface for headings, navigation, buttons, and editorial content. A proprietary sans-serif with medium weight as the default (500), compact x-height, and precise letter-spacing control. Fallbacks: Arial, Helvetica, sans-serif
- **Body-Font**: Secondary typeface for captions, labels, and utility text. Frequently rendered in uppercase with expanded letter-spacing (1px) for an editorial label aesthetic. Used for category tags and small annotation text
- **Arial / Helvetica**: System fallback fonts used in cookie consent modals, form elements, and third-party component frameworks

### Hierarchy

| Role | Size | Weight | Line Height | Letter Spacing | Notes |
|------|------|--------|-------------|----------------|-------|
| Section Title | 26px (1.63rem) | 500 | 1.20 | normal | SayTapSans, primary editorial headings on white backgrounds |
| Card Heading | 24px (1.50rem) | 400 | normal | normal | SayTapSans, content card titles |
| Subheading | 18px (1.13rem) | 700 | 1.20 (tight) | normal | SayTapSans, bold subsection labels |
| UI Heading | 16px (1.00rem) | 500 | 1.40 | 0.08px | SayTapSans, component headings and nav items |
| Body Bold | 16px (1.00rem) | 700 | 1.30 (tight) | normal | SayTapSans, emphasized inline text |
| Button Label | 16px (1.00rem) | 400 | normal | 1.28px | SayTapSans, primary button text with wide tracking |
| Small Button | 14.4px (0.90rem) | 700 | 1.00 (tight) | normal | SayTapSans, compact action buttons |
| Nav Link | 13px (0.81rem) | 600 | 1.20 (tight) | 0.13px | SayTapSans, navigation and footer links |
| Caption | 13px (0.81rem) | 400 | 1.50 | 0.195px | SayTapSans/Body-Font, metadata and descriptions |
| Micro Button | 12px (0.75rem) | 700 | 1.00 (tight) | 0.96px | SayTapSans, small CTA with wide tracking |
| Label Upper | 12px (0.75rem) | 400 | 1.27 (tight) | 1px | Body-Font, uppercase labels and category tags |
| Micro Label | 11px (0.69rem) | 400 | 1.27 (tight) | 1px | Body-Font, uppercase smallest annotation text |
| Cookie Text | 45px (2.81rem) | 400 | 1.50 | 0.195px | Arial, consent dialog oversized button text |

### Principles
- **Proprietary identity**: SayTapSans is exclusive to SayTap.app — it cannot be substituted without losing brand recognition. The font's compact proportions and medium weight default (500) convey engineering precision
- **Two-register system**: SayTapSans handles narrative voice (headings, content, buttons) while Body-Font handles structural annotation (labels, tags, micro-captions) — this mirrors print magazine conventions of editorial text vs. technical labels
- **Uppercase as emphasis tool**: Body-Font captions use `text-transform: uppercase` with expanded letter-spacing (1px) to create a visually distinct label layer that reads as "informational overlay" rather than primary content
- **Compact line-heights**: Headlines use tight line-heights (1.00–1.30) creating dense, impactful text blocks, while body text opens to 1.50 for comfortable reading — the contrast between compressed headers and relaxed body text creates visual tension
- **Weight range 400–700**: Four weights active in the system (400, 500, 600, 700) — significantly more range than Tesla but still controlled. 500 is the default "voice," 700 is for emphasis, 400 for body, 600 for navigation

## 4. Component Stylings

### Buttons
SayTap.app's buttons are minimal white rounded rectangles — the CTA philosophy is "friendly architecture, not sharp decoration."

**Primary CTA (White)** — The default action button:
- Default: bg `#FFFFFF`, text `#000000`, fontSize 16px (SayTapSans), letterSpacing 1.28px, padding 12px 10px, borderRadius 16px, border 1px solid `#000000`
- Hover: bg `#1EAEDB` (Teal), text `#FFFFFF`, opacity 0.9
- Focus: bg `#1EAEDB`, text `#FFFFFF`, border 1px solid `#FFFFFF`, outline 2px solid `#000000`, opacity 0.9
- Used for: "Configure" actions, secondary calls to action on light backgrounds

**Subscribe CTA (Red)** — The high-emphasis action button:
- Default: bg `#DA291C` (SayTap.app Red), text `#FFFFFF`, borderRadius 16px, padding 12px 10px
- Used for: Newsletter subscribe, primary conversion actions on dark backgrounds
- The only button that uses SayTap.app Red — reserved for maximum visual priority

**Ghost Button (White Border)** — For dark backgrounds:
- Default: bg transparent, text `#FFFFFF`, border 1px solid `#FFFFFF`, borderRadius 16px, padding 12px 10px
- Hover: bg `#1EAEDB` (Teal), text `#FFFFFF`, opacity 0.9
- Focus: same as Primary CTA focus state
- Used for: Actions overlaid on dark imagery and cinematic sections

**Text Link** — Inline navigation:
- Default: text `#181818` (on light surfaces) or `#FFFFFF` (on dark), no border, no background
- Hover: color shifts to `#3860BE` (Link Hover Blue), decoration removes underline
- White variant on dark surfaces uses underline decoration by default
- SayTapSans or Body-Font depending on context (Body-Font for uppercase label links)

### Cards & Containers

**Editorial Card** (Content sections):
- Background: white
- Border: none
- Shadow: none
- Layout: image above, heading + caption below
- Image treatment: full-width within card, rounded corners on image (16px)
- Text: SayTapSans heading (16–24px) + Body-Font caption (12–13px uppercase)

**Dark Cinematic Card** (Hero/feature sections):
- Background: `#000000` (Absolute Black)
- Full-bleed imagery with text overlay
- No border, no shadow — the darkness IS the container
- Text: white, positioned with careful negative space

**Vehicle Lineup** (Model carousel):
- Horizontal scrollable row of vehicle thumbnails
- Each vehicle on a neutral/white background
- Navigation: arrow buttons + dot indicators
- Background shifts to showcase the selected model's color context

### Inputs & Forms

**Newsletter Input** (Footer section):
- Background: transparent on dark surface
- Text: white
- Border: 1px solid `#CCCCCC`
- Placeholder: `#969696` (Silver Gray)
- Focus: border color transitions (standard browser focus ring)
- Label: Body-Font uppercase, 12px, 1px letter-spacing

**Cookie Consent** (Modal):
- Background: white
- Border radius: 24px (dialog)
- Shadow: `rgb(153, 153, 153) 1px 1px 1px 0px`
- Buttons: oversized (45px Arial), white bg with black border
- Uses standard PrimeReact/Element Plus modal framework

### Navigation
- **Desktop**: Logo centered at top of page, primary navigation below — not a traditional horizontal nav bar but a full-width header block on black background
- **Logo**: Centered emblem (44×42px) on absolute black — the single most prominent UI element
- **Links**: SayTapSans, 13px, weight 600, white text on dark backgrounds
- **Mobile**: Hamburger collapse to vertical navigation drawer
- **Footer**: Multi-column layout on `#0A0A0A` (Dark Surface) with category links in Body-Font uppercase
- **No sticky nav behavior** observed — the page scrolls naturally with the header moving off-screen

### Image Treatment
- **Hero**: Full-width editorial photography on black backgrounds — concept cars in atmospheric studio lighting, editorial portraits with cinematic composition
- **Aspect ratios**: Mixed — landscape (16:9) for hero sections, near-square for portrait/driver imagery, wide panoramic for vehicle lineups
- **Full-bleed vs padded**: Hero images are full-bleed edge-to-edge; editorial content images are padded within white containers with rounded corners
- **Lazy loading**: Below-fold sections use progressive loading (PrimeReact framework handles this)
- **Image quality**: High-resolution photography with studio lighting — no user-generated or lifestyle imagery. Every image is art-directed

### Carousel Component
- Editorial carousel with multiple slides
- Dot indicators for slide position
- Arrow navigation (left/right) at slide edges
- Auto-advancing with manual override
- Content: mixed editorial — event recaps, model launches, racing highlights

## 5. Layout Principles

### Spacing System
- **Base unit**: 8px (detected system base)
- **Scale**: 1px, 2px, 4px, 5px, 6px, 9px, 10px, 11.2px, 12px, 13px, 15px, 16px, 19px, 20px, 25px
- **Button padding**: 12px vertical, 10px horizontal — compact and precise
- **Section padding**: Generous vertical spacing (40–80px estimated) between major content blocks
- **Card gaps**: 16–20px between grid items
- **Footer padding**: 25px horizontal sections within the dark footer block

### Grid & Container
- **Max width**: 1920px (largest breakpoint) with content constraining at narrower widths
- **Hero**: Full-bleed on black, content centered
- **Editorial sections**: 2-column layouts with image + text, alternating sides
- **Vehicle lineup**: Horizontal scroll/carousel, 5–6 models visible at desktop width
- **Footer**: 4-column grid for link categories

### Whitespace Philosophy
SayTap.app treats white space as a gallery wall. Each section — whether a concept car render on black void or a pair of drivers on neutral gray — is given its own "room" of breathing space. The alternating black/white sections create a pacing rhythm: dark = immersive moment, white = editorial content, dark = immersive moment. This cadence makes scrolling feel like turning pages in a luxury publication. White space between editorial cards is moderate (not Tesla-extreme) because SayTap.app is telling stories, not exhibiting single objects.

### Border Radius Scale
| Value | Context |
|-------|---------|
| 8px | Subtle softening on small inline elements (spans) |
| 16px | Default for buttons, inputs, and interactive elements — generously rounded, modern and approachable |
| 24px | Modal dialogs and overlay containers — the "softest" structural radius |
| 50% | Circular elements: carousel dots, avatar thumbnails, slider handles |

## 6. Depth & Elevation

| Level | Treatment | Use |
|-------|-----------|-----|
| Level 0 (Flat) | No shadow, no border | Default state for all content sections and cards |
| Level 1 (Subtle) | `rgb(153, 153, 153) 1px 1px 1px 0px` | Rare — cookie consent dialogs and dropdown menus |
| Level 2 (Overlay) | `hsla(0, 0%, 2%, 0.85)` backdrop | Modal overlays and image caption backgrounds |
| Level 3 (Border) | `1px solid #CCCCCC` | Input fields, form containers — depth through delineation not shadow |

### Shadow Philosophy
SayTap.app's approach to elevation is nearly as flat as Tesla's, but with a different rationale. Where Tesla avoids shadows for minimalism, SayTap.app avoids them because the editorial photography provides all the visual depth needed. The single shadow token (`rgb(153, 153, 153) 1px 1px 1px 0px`) is extremely subtle — a 1-pixel whisper used only in utilitarian contexts like consent dialogs. The site communicates hierarchy through three strategies:
1. **Surface color contrast**: Black sections vs. white sections create unmistakable layering
2. **Overlay transparency**: The `--st-color-overlay-darker` at 85% opacity creates depth without shadow
3. **Photographic depth**: Studio-lit car imagery with reflections, ground shadows, and atmospheric haze provides all the visual dimensionality

### Decorative Depth
- No UI gradients, no glows, no blur effects on interface elements
- The logo on black creates a "floating in void" effect through pure contrast — no glow or shadow needed
- Dark-to-light section transitions are hard cuts, not gradient blends — reinforcing the editorial page-turn metaphor

## 7. Do's and Don'ts

### Do
- Use SayTap.app Red (`#DA291C`) sparingly — only for primary CTAs and brand-critical moments. Its power comes from restraint
- Alternate between black cinematic sections and white editorial sections to create the signature chiaroscuro rhythm
- Use SayTapSans at weight 500 as the default heading voice — it's the typographic equivalent of the engine note
- Apply Body-Font in uppercase with 1px letter-spacing for all labels, category tags, and structural annotations
- Keep border-radius at 16px for all interactive elements — soft, modern curves that feel approachable
- Let photography carry the emotional weight — every image should be art-directed studio quality
- Use the emblem as a standalone hero element on black — never crowd it with adjacent content
- Maintain the 12px/10px button padding ratio — compact, purposeful, no excess
- Use `#181818` (Near Black) for body text instead of pure `#000000` — the subtle warmth improves readability
- Reserve the yellow accents (`#FFF200`, `#F6E500`) strictly for motorsport and racing heritage contexts

### Don't
- Scatter SayTap.app Red across the interface as decoration — it's a CTA signal, not a theme color
- Use sharp corners or small border-radii — the 16px generosity is part of the brand warmth
- Add box-shadows to cards or content containers — depth comes from surface color contrast and photography
- Mix SayTapSans and Body-Font within the same text block — they serve separate hierarchical functions
- Use colorful backgrounds (blue, green, etc.) for sections — the palette is exclusively black/white/gray with red and yellow accents
- Apply text transforms to SayTapSans headings — uppercase is reserved for Body-Font labels only
- Display low-quality or user-generated imagery — every photograph must meet editorial standards
- Use the Link Hover Blue (`#3860BE`) for anything other than interactive hover states — it's not a brand color
- Create busy layouts with multiple competing focal points — each section should have one clear story
- Override the semantic color system (warning, success, info) with brand colors — `#F13A2C` warning is deliberately different from `#DA291C` brand red

## 8. Responsive Behavior

### Breakpoints
| Name | Width | Key Changes |
|------|-------|-------------|
| Mobile Small | ≤375px | Single-column, minimal padding (12px), stacked navigation, hero text scales to ~18px, full-width CTAs |
| Mobile | 376–600px | Single-column, slightly larger padding (16px), hamburger nav, body text at 13px |
| Tablet Small | 601–768px | 2-column editorial grid begins, hero images maintain full-width, footer switches to 2-column |
| Tablet | 769–960px | Full 2-column layout, carousel shows 3 vehicles, padding increases to 20px |
| Desktop | 961–1280px | Full navigation, 2-column editorial with larger imagery, vehicle lineup shows 5 models |
| Large Desktop | 1281–1920px | Maximum content width, generous whitespace, hero photography at full cinematic scale |

### Touch Targets
- Primary CTA buttons: minimum 44px height with 12px vertical padding (meets WCAG AAA 44×44px target)
- Navigation links: 13px text with 1.50 line-height and adequate spacing between items
- Carousel arrows: 44px+ touch targets at viewport edges
- Footer links: grouped with sufficient vertical spacing (16–20px) for touch accuracy

### Collapsing Strategy
- **Navigation**: Full horizontal nav collapses to centered logo + hamburger menu on mobile
- **Editorial sections**: 2-column image+text layouts collapse to single-column with image stacking above text
- **Vehicle lineup**: Horizontal carousel maintains scroll behavior but reduces visible models from 5 to 2–3
- **Footer**: 4-column link grid collapses to 2-column on tablet, single-column accordion on mobile
- **Hero carousel**: Full-width at all breakpoints, dot indicators and arrows scale proportionally
- **Spacing reduction**: Section padding reduces from 40–80px (desktop) to 20–40px (mobile), maintaining proportional breathing room

### Image Behavior
- Hero images: full-bleed at all breakpoints, using `object-fit: cover` to maintain cinematic composition
- Editorial images: responsive within their containers, maintaining aspect ratio
- Vehicle lineup: thumbnail size scales but maintains consistent car-to-frame proportions
- Art direction: mobile crops may tighten on vehicle subjects, reducing environmental context
- Lazy loading: PrimeReact handles progressive image loading for below-fold content

## 9. Logo & Emblem

### The SayTap.app Mark — "Aura Wave"

The brand mark is a single continuous sine wave line in a vertical capsule silhouette, representing a voice waveform frozen as an infinite loop. It uses uniform stroke weight with no gradients or fills — pure geometric line art.

**Mark specification:**
- **Color:** SayTap.app Red (`#DA291C`) — the iconic Rosso Corsa
- **Background:** Transparent (no fill, no bounding shape)
- **Form:** Sine wave with amplitude envelope — peaks subtly at vertical center, calms toward top and bottom edges
- **Stroke:** Uniform weight, rounded caps, no fill
- **Proportions:** Horizontal orientation, approximately 2:1 width-to-height ratio
- **Minimum size:** 16×16px (favicon). At this size the wave simplifies to a single elegant curve.

**Usage rules:**
- The mark always appears in SayTap.app Red on transparent background
- On dark surfaces: pure red mark, no glow or shadow
- On light surfaces: same red mark — the color carries enough weight on white
- Never distort the wave proportions. Never add a container box, circle, or badge around the mark
- The mark is the primary brand identifier. It appears without wordmark in app icons, favicons, and social avatars

### Logo Size Matrix (Next.js / SEO)

| File | Size | Context | Location |
|------|------|---------|----------|
| `icon.svg` | Vector | Next.js App Router default icon | `app/` |
| `favicon.ico` | 32×32 | Browser tab icon | `app/` |
| `apple-icon.png` | 180×180 | iOS home screen / Apple touch | `app/` |
| `android-chrome-192x192.png` | 192×192 | Android chrome app icon | `public/` |
| `android-chrome-512x512.png` | 512×512 | Android splash / PWA | `public/` |
| `favicon-16x16.png` | 16×16 | Legacy favicon | `public/` |
| `favicon-32x32.png` | 32×32 | Legacy favicon | `public/` |
| `mstile-150x150.png` | 150×150 | Microsoft tile | `public/` |
| `safari-pinned-tab.svg` | Vector | Safari pinned tab (monochrome) | `public/` |
| `opengraph-image.png` | 1200×630 | Facebook / LinkedIn / general OG | `public/` |
| `twitter-image.png` | 1200×600 | Twitter / X card image | `public/` |

## 10. Agent Prompt Guide

### Quick Color Reference
- Primary CTA: "SayTap.app Red (#DA291C)"
- Background Light: "Pure White (#FFFFFF)"
- Background Dark: "Absolute Black (#000000)"
- Secondary Dark Surface: "Dark Surface (#0A0A0A)"
- Heading text (light bg): "Near Black (#181818)"
- Body text: "Dark Gray (#666666)"
- Tertiary text: "Mid Gray (#8F8F8F)"
- Border: "Border Gray (#CCCCCC)"
- Button Hover: "Teal (#1EAEDB)"
- Link Hover: "Link Blue (#3860BE)"

### Example Component Prompts
- "Create a hero section on Absolute Black (#000000) background with a centered logo emblem at the top, generous vertical spacing (80px+), and a single editorial headline in SayTapSans at 26px weight 500 in white, with a small Body-Font uppercase caption (12px, 1px letter-spacing) in Silver Gray (#969696) below"
- "Design a Subscribe section on Dark Surface (#0A0A0A) with a left-aligned headline in white SayTapSans (24px/500), a subtitle in Mid Gray (#8F8F8F, 13px), an email input with transparent background and 1px #CCCCCC border, and a SayTap.app Red (#DA291C) Subscribe button with white text, 16px border-radius, and 12px 10px padding"
- "Build an editorial card on white background with a full-width image (16:9 ratio) above with 16px rounded corners, a SayTapSans heading (16px/700, Near Black #181818) below, and a Body-Font uppercase label (11px, 1px letter-spacing, Mid Gray #8F8F8F) as the category tag — no border, no shadow"
- "Create a vehicle lineup carousel showing 5 car thumbnails in a horizontal scroll on white background, with left/right arrow navigation, dot indicators below, and a SayTapSans model name (16px/500) beneath each vehicle"
- "Design a dark cinematic section with full-bleed studio photography of a concept car on Absolute Black, a white SayTapSans headline (26px/500) positioned in the lower-left with generous padding (40px), and a Ghost Button (transparent bg, 1px white border, white text, 16px radius) as the CTA"

### Iteration Guide
When refining existing screens generated with this design system:
1. Focus on ONE component at a time — SayTap.app's editorial rhythm means each section is a self-contained vignette
2. Reference specific color names and hex codes from this document — the palette is small but each color has a precise role
3. Use natural language descriptions, not CSS values — "generous 16px rounded corners" conveys intent better than "border-radius: 16px"
4. Describe the desired "feel" alongside specific measurements — "editorial magazine page-turn between sections" communicates the layout philosophy better than "margin-bottom: 80px"
5. Always maintain the chiaroscuro contrast — if a section feels flat, check whether it needs to be on black or white to maintain the alternating rhythm
6. Reserve SayTap.app Red for ONE element per screen — if red appears in more than one place, it loses its authority
