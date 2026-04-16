# Style Catalog

Each style below is a distinct visual identity. They share a common shell (nav rail, progress indicator, keyboard shortcuts, top-brand bar) but diverge completely in typography, color, and layout logic.

To request a new deck in this framework, name the style. Example: *"Build me a 10-slide deck in the Swiss Rigor style for our enterprise sales pitch."*

---

## 01. Editorial Warmth

**Feel:** Invitation. Patience. Something worth sitting with.
**Typography:** Fraunces serif (headlines), Inter sans (body), subtle italic.
**Palette:** Warm paper `#faf7f2`, deep ink `#0f1f2e`, rust accent `#b8552a`, warm rule `#e2d8c8`.
**Layout:** Journal masthead. Drop cap. Footer notes in italic.
**Best for:** Coaching workshops, thought-leadership talks, long-form video recordings, premium client proposals, founder keynotes.
**Avoid for:** High-data density, engineering contexts, anything needing speed/scan.

**Reference implementation:** Coaching workshop deck + Lightning Lesson slide 3.

---

## 02. Cohort Dark

**Feel:** Focus. Momentum. "We're building something."
**Typography:** Fraunces serif (display), Inter sans (body), JetBrains Mono (metadata/tags).
**Palette:** Near-black `#07080c`, teal glow `#2b7a6c`, amber glow `#b87a1a`, blue thread `#4460a0`. Soft radial color wash in the background.
**Layout:** Card-based with color-coded headers (teal = async, amber = live, blue = cycle). Background glows without being noisy.
**Best for:** Live cohort classes, online course sessions, developer-adjacent education, async learning material.
**Avoid for:** Conservative enterprise audiences, boards.

**Reference implementation:** Online cohort course deck + Lightning Lesson slide 4.

---

## 03. Swiss Rigor

**Feel:** Adult. Numerical. Unplayful.
**Typography:** Inter Tight at heavy weights, single typeface does all expressive work.
**Palette:** Pure white `#ffffff`, pure black `#000000`, one saturated accent (red `#e63946` in current implementation).
**Layout:** 12-column grid (optionally visible at low opacity). Everything aligns. White space is 60%+ of the composition.
**Best for:** Board meetings, enterprise sales pitches, investor decks, regulated-industry presentations.
**Avoid for:** Warm/inviting moments, creative-industry audiences, keynotes.

**Reference implementation:** Lightning Lesson slide 5.

---

## 04. Terminal Brutalism

**Feel:** Raw. Fast. No BS.
**Typography:** JetBrains Mono exclusively, heavy weights.
**Palette:** Off-cream `#e8e4d9`, pitch black `#111`, one punch color (rust orange `#ff4500`), highlighter yellow `#fff59d` for emphasis.
**Layout:** Thick borders, no rounded corners, no shadows, blinking cursor animation, terminal prompt styling.
**Best for:** Engineering all-hands, post-mortems, dev-tool launches, hackathons, technical-audience contexts.
**Avoid for:** Non-technical audiences, anything requiring warmth.

**Reference implementation:** Lightning Lesson slide 6.

---

## 05. Magazine Feature

**Feel:** Mixed. Rich. Deliberately paced.
**Typography:** Playfair Display (display, italic), Fraunces (body serif), Inter (metadata).
**Palette:** Deep warm-brown `#1a1612`, cream `#f5ede0`, amber `#e8a35c`, cover-color rust gradient.
**Layout:** Masthead with publication-style title. "Cover" image block paired with feature copy. Pull-quotes with accent-color labels.
**Best for:** Keynotes, annual reviews, brand launches, high-polish video recordings, long-form narrative decks.
**Avoid for:** Data-dense content, short/fast presentations.

**Reference implementation:** Lightning Lesson slide 7.

---

## 06. Bento Modern

**Feel:** Product-native. Spatial. Energetic.
**Typography:** Inter Tight (display, heavy), Inter (body), one monospace note.
**Palette:** Neutral off-white `#f5f5f7`, deep ink `#1d1d1f`, one gradient tile (purple-indigo), one punch tile (orange `#ff9500`).
**Layout:** 4×2 card grid with one `span-2×2` hero tile, one accent tile, one dark tile, one wide tile. Soft shadows lift on hover.
**Best for:** Product launches, team kickoffs, roadmap reviews, investor updates, feature reveals.
**Avoid for:** Deep-narrative content, academic contexts.

**Reference implementation:** Lightning Lesson slide 8.

---

## Style Pairings

Some moments benefit from a **mix** of styles across a single deck:

- **Editorial + Bento** — for a keynote that has narrative AND a product reveal
- **Swiss + Terminal** — for a technical sales pitch that needs numbers AND credibility with engineers
- **Cohort Dark + Editorial** — for a cohort launch where the content is warm but the energy is dev-native

The Lightning Lesson deck itself is the proof of concept: 7 different styles in one deck, each matched to the content it supports.

---

## Adding a New Style

When you encounter a deck moment the catalog doesn't serve, add a new entry here with:

- Name and 1-line "feel" summary
- Typography stack
- Palette with hex codes
- Layout logic
- Best for / Avoid for
- Reference implementation path

Keep the catalog curated — 6-10 styles total, not dozens. Each should genuinely serve a different moment.
