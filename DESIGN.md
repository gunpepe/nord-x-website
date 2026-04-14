# NORD-X — DESIGN.md

## Overview

NORD-X company website. Stylish, clean, consulting-firm aesthetic with punchy cyan and orange accents.
White base with deep navy text. The site speaks to hotel owners, SME executives, and students.

**Tone**: Direct and grounded. No overblown marketing language. Every line should feel honest and specific.

**Catchphrase**: 「データが、一番正直だ。」 — simple, confident, not pretentious.

---

## Colors

| Name          | Hex       | Usage                                       |
|---------------|-----------|---------------------------------------------|
| White         | `#FFFFFF` | Page background                             |
| Surface       | `#F4F6FB` | Alternate section backgrounds, card fills   |
| Border        | `#E4E8F2` | Dividers, card borders                      |
| Navy          | `#0D0F1E` | Primary headings, strong text               |
| Body          | `#2C3252` | Body text                                   |
| Muted         | `#7A849A` | Secondary text, captions, labels            |
| Cyan          | `#00A8C8` | CTAs, links, highlights, active states      |
| Cyan Light    | `#E6F7FB` | Tag backgrounds, tinted surfaces            |
| Orange        | `#F55A1E` | Secondary CTAs, badges, accents             |
| Orange Light  | `#FFF0EB` | Tag backgrounds, tinted surfaces            |

Do not use dark backgrounds for any major section. No pastels. Keep the palette tight.

---

## Typography

**Fonts**: `'Syne'` (display), `'Inter'` (body) — both via Google Fonts.

| Role          | Font  | Size      | Weight | Line Height | Letter Spacing |
|---------------|-------|-----------|--------|-------------|----------------|
| Hero Title    | Syne  | 64–76px   | 800    | 1.08        | -0.03em        |
| Section Title | Syne  | 40–48px   | 700    | 1.2         | -0.02em        |
| Card Title    | Syne  | 22–26px   | 700    | 1.25        | -0.01em        |
| Body          | Inter | 15–16px   | 400    | 1.75        | 0              |
| Small         | Inter | 13–14px   | 400    | 1.55        | 0.01em         |
| Label / Tag   | Inter | 11px      | 600    | 1.4         | 0.08em (caps)  |

**Numbers**: Always use `font-variant-numeric: tabular-nums` on numeric displays to prevent layout shift.
All section labels: UPPERCASE, letter-spacing 0.07em+.

---

## Spacing

Base unit: `8px`

| Token | Value  | Typical Use               |
|-------|--------|---------------------------|
| xs    | 4px    | Icon gaps                 |
| sm    | 8px    | Tight internal padding    |
| md    | 16px   | Component padding         |
| lg    | 32px   | Between components        |
| xl    | 64px   | Section padding           |
| 2xl   | 120px  | Hero padding              |

Max content width: `1200px`, centered.

---

## Shadows

Shadows are subtle and color-matched. Never use heavy black drop shadows.

| Token       | Value                                      | Use                     |
|-------------|--------------------------------------------|-------------------------|
| card        | `0 2px 16px rgba(13,15,30,0.07)`           | Default card            |
| card-hover  | `0 8px 40px rgba(0,168,200,0.15)`          | Hovered card            |
| btn-cyan    | `0 4px 20px rgba(0,168,200,0.35)`          | Cyan button hover       |
| btn-orange  | `0 4px 20px rgba(245,90,30,0.28)`          | Orange button hover     |
| mockup      | `0 16px 48px rgba(13,15,30,0.12)`          | In-page UI mockups      |

---

## Border Radius

| Element       | Radius |
|---------------|--------|
| Cards         | 20px   |
| Mockups       | 14px   |
| Buttons       | 8px    |
| Tags          | 999px  |
| Inputs        | 8px    |
| Icon boxes    | 12px   |

---

## Icon System

Use **Lucide Icons** via CDN (`https://unpkg.com/lucide@latest/dist/umd/lucide.min.js`).
Initialize with `lucide.createIcons()` after DOM load.

Usage: `<i data-lucide="icon-name" class="icon"></i>`

Icon size: 20px default, 18px in compact contexts. Stroke width: 1.75.
Color: inherit from parent text color. Never use emoji as icons in the UI.

Key icons in use:
- DPLite section: `bar-chart-2`, `plug`, `map-pin`, `users`
- AI section: `cpu`, `zap`, `arrow-up-right`, `target`
- Navigation: `menu`
- CTAs: `arrow-right`
- Contact: `send`, `mail`

---

## Card Variants

Three distinct card types — never use the same card style twice in the same section.

### Featured Card (horizontal)
- Full-width, horizontal split: text left (~55%), visual right (~45%)
- Used for: primary business showcase
- Top accent bar: 3px, accent color
- Background: white
- Visual area: contains an in-page UI mockup

### Feature Grid Card (compact vertical)
- ~1/3 width, used in 3-column grids
- Icon box at top, title, short description
- Background: white, border on default, borderless on surface background
- Hover: slight lift + border color change

### Info Row (flat)
- Used in Company section
- No border-radius variation — consistent at 14px
- Label above, value below
- Background: white on surface, or surface on white

---

## Component Specs

### Primary Button (Cyan)
- Background: `#00A8C8`, text: `#FFFFFF`
- Padding: `14px 32px`, font: Inter 15px 600
- Hover: `brightness(1.08)` + `btn-cyan` shadow
- Arrow icon (`arrow-right`) trailing, 16px

### Secondary Button (Orange outline)
- Border: `1.5px solid #F55A1E`, text: `#F55A1E`
- Hover: fill `#F55A1E`, text white, `btn-orange` shadow

### Tag / Badge
- Cyan: bg `#E6F7FB`, text `#00A8C8`
- Orange: bg `#FFF0EB`, text `#F55A1E`
- Padding: `4px 14px`, 11px 600 caps

### Navigation
- `rgba(255,255,255,0.92)` + `backdrop-filter: blur(14px)`
- Border-bottom: `1px solid #E4E8F2`
- Height: 64px, sticky
- Logo: Syne 700, navy. Hyphen + X: cyan
- Links: Inter 14px 500, muted. Hover: navy
- Mobile: hamburger menu, links hidden

---

## In-page Mockups

Mockups are HTML/CSS representations of the product UI — not screenshots.
They exist to make text-heavy sections more visual.

### DPLite Dashboard Mockup
- Mini card with dark header bar (`#0D0F1E`)
- Bar chart: 7 bars with varying heights, active bar in cyan
- Price recommendation badge: orange background, white text
- Subtle shine/gradient on the card surface

### AI Process Flow
- 3 horizontal steps connected by dashed arrows
- Each step: number, title, short label
- Colors: step bg = surface, connector = muted dashes, arrow = cyan

---

## Motion & Animation

All motion should feel purposeful and smooth, never showy.

### Entrance (scroll-triggered)
- Trigger: `IntersectionObserver` at `threshold: 0.12`
- Effect: `opacity 0→1` + `translateY 24px→0`
- Duration: `0.55s`, easing: `cubic-bezier(0.16, 1, 0.3, 1)` (ease-out expo)
- Stagger siblings with `transition-delay: 0.1s` increments (max 0.4s)
- Once only — do not re-trigger on scroll up

### Hero text reveal
- Each word/phrase staggered: delay 0, 0.08s, 0.16s, 0.24s
- Same opacity+translateY effect

### SVG chart draw (hero)
- `stroke-dashoffset` animation: full path length → 0
- Duration: `1.8s`, easing: `ease-out`, delay: `0.6s`
- Dot markers fade in at `1.4s`

### Animated counters (stats)
- Count up from 0 to target over `1.2s` when scrolled into view
- Easing: ease-out (decelerates toward end)
- Trigger: IntersectionObserver, once

### Hover
- Cards: `transform: translateY(-4px)`, `0.2s ease`
- Buttons: `filter: brightness(1.08)` + shadow, `0.2s ease`
- Nav links: color change, `0.15s ease`

### Do not use
- Bounce, spring, or overly elastic easings
- Animations longer than 0.7s for UI feedback
- Parallax scrolling
- Auto-playing carousels

---

## Layout Patterns

- **Hero**: 55/45 split. Left: all text. Right: hero visual (chart SVG).
- **Featured Business**: Full-width horizontal card. Text left, mockup right.
- **Feature Grid**: 3-column grid of compact cards.
- **Two-column**: 50/50 for Careers, Company intro.
- **Centered narrow**: max-width 640px for Contact form.

Sections alternate: White → Surface → White → Surface.

---

## Do's and Don'ts

**Do:**
- Use Syne for all titles and card headings (not just section headers)
- Let whitespace breathe — don't cram content
- Use Lucide icons consistently for all iconography
- Show the product visually with mockups, not just words
- Make numbers feel precise (tabular-nums, right-aligned where appropriate)

**Don't:**
- Don't write catchphrases that sound like they're trying too hard
- Don't use emoji as UI icons
- Don't make all cards the same shape and layout
- Don't animate everything — reserve animation for high-impact moments
- Don't use `font-weight: 400` for any heading, ever
