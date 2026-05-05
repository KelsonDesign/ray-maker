# Kaia Cacao — Design System

> _Shift Your Mood._

Kaia Cacao is a pre-launch ceremonial-cacao / wellness chocolate brand. The brand sits at the intersection of **wellness ritual** and **artisan craft chocolate** — closer to a high-end botanical or skincare line than a candy company. The product (drinking cacao, intended to support mood, focus, calm) is positioned as a daily ritual, not an indulgence.

The website is currently a waitlist landing page on Framer at <https://www.kaiacacao.com/>. The full identity treats cacao as the sun-warmed, grounding, sensory plant medicine it is — earthy palette, sun symbolism, refined typography.

## Sources
- **Public site (waitlist):** https://www.kaiacacao.com/ — the only currently-public surface.
- **Color swatches:** `uploads/Screenshot 2026-05-04 at 10.38.25 PM.png` — six approved brand colors (extracted into `colors_and_type.css`).
- **Fonts (provided):** `uploads/RedHatDisplay-{Bold,Medium,SemiBold}.ttf` — copied to `fonts/`.
- **Logo + reference imagery:** lifted from the public Framer site into `assets/` (logo lockup with sun rays, founder portraits, lifestyle imagery).

> ⚠️ **No code or Figma access** was provided. The system below is reconstructed from the public site, the swatch sheet, and the supplied fonts. UI kit components are interpretations consistent with the brand's vibe rather than recreations of production code.

---

## Index — what's in this folder

```
README.md                — you are here
SKILL.md                 — agent skill manifest (Claude Code-compatible)
colors_and_type.css      — CSS custom properties for color, type, spacing, motion
fonts/                   — Red Hat Display TTFs
assets/                  — logo, wordmark, reference photography
preview/                 — design-system preview cards (rendered in the DS tab)
ui_kits/website/         — web UI kit: components + interactive index.html
reference/               — raw scraped reference (kept for traceability)
```

---

## Brand snapshot

| | |
|---|---|
| **Tagline** | Shift Your Mood |
| **Category** | Functional / ceremonial cacao, drinking chocolate, wellness ritual |
| **Stage** | Pre-launch, waitlist on kaiacacao.com (Framer) |
| **Audience** | Wellness-curious adults; people building rituals around mornings, focus, calm; existing matcha / adaptogen drinkers |
| **Primary feeling** | Warm, grounding, sun-on-skin, slow morning, ceremonial |
| **Adjacent brands (vibe)** | Moon Juice, Ceremonia, Golde, Verb Energy, Apothékary |

---

## Content fundamentals

**Voice:** Calm, sensory, first-person plural ("we"), intimate without being precious. The brand speaks _to_ you, not _at_ you. Short sentences. Generous whitespace around copy.

**Tone:** Warm + assured. Not hype. Not cute. Not science-y or clinical — sensory and embodied is the lane (talk about feeling, mood, ritual; not milligrams).

**Casing:**
- Display / hero copy uses **Title Case** in the serif (e.g. _Get Early Access_).
- Wordmark is **ALL CAPS** ("KAIA CACAO") — letterspaced, classic.
- Body copy is sentence case.
- Tiny eyebrow labels are **UPPERCASE + LETTERSPACED** (e.g. `SHIFT YOUR MOOD`, `THE RITUAL`).

**Person:** "We" for the brand, "you" for the reader. Avoid "I". Avoid "users", "customers".

**Emoji:** Not used. Avoid. The brand achieves warmth through photography, color, and serif type — not glyphs.

**Sample copy (in the brand voice):**
- "We're getting close. Sign up to follow our journey and get early access to our first shipments of Kaia Cacao."
- "A daily cup. A different morning."
- "Cacao is the original mood-shifter. We grow ours slow, source it close, and serve it warm."
- "Join 100+ others on the waitlist."

**What to avoid:**
- Exclamation points ("Save 20%!").
- Health claims ("clinically proven", "boosts immunity").
- Stacked feature bullets with checkmarks.
- "Game-changing", "revolutionary", "unlock".
- Tech-startup voice. This is not a SaaS.

---

## Visual foundations

### Palette
Six-color system, all warm-leaning. Built for **earth + sun**, not tech.
- **Ink `#2c3538`** — deepest text, near-black; never pure black.
- **Teal `#405358`** — signature deep teal; the primary brand surface (logo background, hero, footer).
- **Stone `#a0a9ac`** — cool warm-gray; secondary text and dividers.
- **Rose `#d9a597`** — dusty clay rose; the wordmark color, primary accent on dark.
- **Cream `#ecdfc7`** — warm bone / latte; default light background, cards.
- **Amber `#f2b66f`** — honey gold; CTA highlight, "sun" accent.

The palette is documented in detail in `colors_and_type.css` with a tonal extension (e.g. `--kc-teal-700`, `--kc-rose-200`).

### Type
- **Display serif:** Cormorant Garamond — high-contrast classical serif used for the wordmark, hero, and all major headings. ⚠ This is a **substitution** for the unknown brand display face used on the live site (close visual match: condensed strokes, refined terminals, elegant capitals). Please confirm or upload the licensed face.
- **UI sans:** Red Hat Display (provided) — Medium 500 for body, SemiBold 600 for buttons + emphasis, Bold 700 sparingly.
- **Mono:** JetBrains Mono — for code/numerics in the design system itself; not used in product surfaces.

The serif/sans pairing is the workhorse: serif gives ceremony, sans keeps interface legible.

### Spacing & rhythm
4-step base scale (4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 96 / 128). Generous whitespace is core to the brand — sections breathe, copy never feels tight. Default vertical rhythm between major sections is `--kc-space-9` (96px) on desktop.

### Backgrounds
- **No bluish-purple gradients.** Ever.
- Large flat warm fields are the default — cream for light surfaces, deep teal for hero/footer, ink for dramatic moments.
- Photography is treated as the primary "texture": warm, golden-hour-lit, slightly creamy/milky, never high-contrast or cool. Subjects are people in soft natural light, hands holding cups, cacao pods, simple morning rituals.
- No repeating patterns or hand-drawn illustrations on production surfaces. The sunburst icon (from the logo) is the only graphic motif and appears _sparingly_ as a divider or watermark.

### Animation
- **Easing:** `cubic-bezier(0.22, 1, 0.36, 1)` — gentle, slow-out. Set on `--kc-ease`.
- **Durations:** 160ms (hover micro), 260ms (default state), 520ms (entrance / scroll reveals).
- **Vibe:** fades and gentle slide-up reveals. **No bounces, no springs, no swooshes.** Things settle, they don't pop.
- Reduce motion respected (`prefers-reduced-motion`) — fades only.

### Hover states
- Buttons darken slightly (ink → teal-700) and stay still — no scale pulse.
- Links shift to rose on hover, with a 1px underline appearing in `--kc-dur`.
- Image cards: a slow, subtle 1.04 zoom on the image itself (not the whole card) over 520ms.

### Press states
- Buttons: `transform: scale(0.98)` only. No color flash.
- Tappable photo tiles dim by ~6% momentarily.

### Borders
- Hairline only — `1px solid var(--kc-line)` on cream surfaces, `1px solid var(--kc-line-deep)` on teal.
- No 2px borders, no double borders. Borders are quiet structural elements, never decorative.

### Shadows
Soft + warm + ink-tinted (never neutral gray). Three steps:
- `--kc-shadow-sm` — resting cards.
- `--kc-shadow-md` — menus, popovers, hovered cards.
- `--kc-shadow-lg` — modals, lifted elements.
Inner shadows are not used.

### Corner radii
- Buttons: **pill** (`--kc-r-pill`, 999px).
- Cards: 20px (`--kc-r-card`).
- Inputs: rare — most fields are an underlined baseline, not a boxed input. When a box is needed, 8px.
- Images: typically 16–24px; hero imagery is occasionally **fully rounded** (oval / soft bottle-shape) to evoke the apothecary/jar metaphor.

### Transparency & blur
- Sticky nav over imagery uses a `backdrop-filter: blur(12px)` with `rgba(64, 83, 88, 0.62)` (teal-translucent).
- Otherwise blur is reserved — it's not part of the everyday vocabulary.

### Imagery direction
Warm, slightly grainy, golden hour. Skin tones favored over product-on-white. Beverages photographed in real ceramic cups, not staged. Slight film grain acceptable. **Never cool, never high-contrast, never b&w.**

### Layout rules
- Max content width 1200px, narrow column 680px for prose.
- Sticky top nav, low height (~64px), translucent over hero.
- Footer is full-bleed deep teal with rose wordmark — mirrors the logo lockup.
- Asymmetric image+text rows (image on alternating sides) are a primary editorial pattern.

---

## Iconography

The brand has effectively **no UI icon system** today — the public site is content-and-photography first. For the UI kit, this design system uses **Lucide** (CDN, stroke-based, 1.5px stroke weight) as a substitution. Lucide's quiet, geometric outline style is the closest match to the brand's restraint. Substitution is **flagged** — please supply or commission a custom icon set if needed.

Rules for icon usage:
- Stroke-only (no filled icons).
- 1.5px stroke, 24px default size, currentColor.
- Icons are **utilitarian only** — used for search, menu, cart, close. Never decorative.
- Emoji and unicode glyphs are **not** used.
- The **sunburst** mark (from the logo) is treated as a brand graphic, not an icon — see `assets/wordmark.svg` and the logo lockup.

---

## Index of UI kits

- **`ui_kits/website/`** — public website kit. Hero, nav, footer, waitlist form, founder/story section, primary buttons, fields. `index.html` shows an interactive recreation of the Kaia Cacao landing experience.

---

## Caveats / open questions
- **Display serif is a substitution** (Cormorant Garamond standing in for the wordmark face). Please confirm.
- No production codebase or Figma file was provided — this kit is built from the public Framer site + swatch sheet only.
- Only the waitlist surface exists publicly today; the full product, e-commerce, blog, and account flows are speculative — they're **not** included here.
- Iconography defaults to Lucide as a flagged substitution.
