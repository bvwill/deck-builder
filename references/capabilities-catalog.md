# Capabilities Catalog

Interactive affordances that turn a deck from a slideshow into a tool. Each capability is implemented in vanilla HTML/CSS/JS — no build step, no dependencies, single file.

To request a capability in a new deck, name it: *"Build me a workshop deck with the Editorial style and inline timers."*

---

## 01. Inline Timer

**What:** A prominent countdown on designated "work time" slides. Start / Pause / Reset controls, plus ±1 min adjusters. Gentle audio beep on zero. Visual state changes: rust-orange while running, green when done.

**When to use:** Workshops, classes, working sessions — any slide where the presenter wants the room to spend N minutes writing, thinking, or building.

**Why it wins:** The presenter doesn't have to tab-switch to a timer app mid-flow. The timer is where their eyes already are. Keyboard shortcut (T) to start/stop.

**Reference:** Coaching workshop deck (5 timers, 5 & 10 min) + Lightning Lesson slide 9 (demo).

---

## 02. Click-to-Copy (Links + Multi-line)

**What:** Clickable rows that copy text to the clipboard — URLs, prompt snippets, or full multi-line blocks (e.g., a Zoom-chat announcement with title, time, and multiple links). Visual feedback: button flips green with a checkmark for ~1.4 seconds.

**When to use:** Any live session where the presenter wants to drop links or text into Zoom chat, email, or shared notes without hunting for the right tab.

**Why it wins:** Single click → paste-ready text. Removes the most common "hold on, let me find that link" interruption in every live presentation.

**Reference:** Lightning Lesson slide 9.

---

## 03. Reveal-on-Cue Animation

**What:** Text that fades in word-by-word with a staggered delay, then holds, then resets. Loopable via CSS animation. Accent words can render in a different color and font (e.g., italic serif accent).

**When to use:** Video recordings (the beat of the reveal is part of the cadence), dramatic headline moments, the single line you want the room to feel.

**Why it wins:** Replaces PowerPoint's awkward "click to advance" animation with a cinematic continuous reveal. Works offline, works in any browser.

**Reference:** Lightning Lesson slide 9.

---

## 04. Embedded Video (Loom, YouTube)

**What:** An iframe that embeds a video directly inside a slide — autoplay-configurable, responsive, no cropping. Works with Loom, YouTube, Vimeo.

**When to use:** When you want a pre-recorded walkthrough to play inside the presentation, not as a separate tab. Common for async course material, "here's how I did X" moments, or bringing in a guest clip.

**Why it wins:** No app-switching. No link-clicking. The audience stays in the deck.

**Reference:** Lightning Lesson slide 9.

---

## 05. Expandable Bento Tiles (FLIP animation)

**What:** A bento-grid where each tile is clickable. Click a tile to smoothly expand it to fill the grid with additional detail content; click again to collapse. Uses the FLIP technique (First-Last-Invert-Play) so the animation tweens between grid layout and absolute positioning — a pure CSS transition would be instant.

**When to use:** Decks where you want to present a summary grid AND the option to drill into one item during live Q&A.

**Why it wins:** Lets a single slide serve as both overview and deep-dive. Presenter can answer audience questions by expanding the relevant tile instead of clicking through hidden slides.

**Reference:** Lightning Lesson slide 8.

---

## 06. Persistent Top-Brand Bar

**What:** A fixed bar across the top of every slide showing the presenter's name, domain, and company, plus an event/deck descriptor on the right. Blurred-glass background so it works over any slide color.

**When to use:** Any deck being recorded, shared, or screenshotted for social — the branding travels with every frame.

**Why it wins:** Free recurring brand impressions throughout the deck. Essential for anything published on LinkedIn or as a Loom recording.

**Reference:** Lightning Lesson — every slide.

---

## 07. Progress Rail + Section Name

**What:** A bottom bar (or top, depending on the deck) showing segmented progress dots (clickable for navigation) plus the current section name and slide counter. Keyboard-navigable (← → or Space).

**When to use:** Decks longer than ~6 slides, anything recorded, any presenter who wants the audience to know where they are in the arc.

**Why it wins:** Reduces "how much more is left?" friction. Creates a sense of pacing and momentum the presenter can lean into.

**Reference:** Both decks built so far.

---

## 08. Section Divider Slides

**What:** Simple dedicated slides that mark the transition between parts of the deck. Usually a Roman numeral or part number, a large title, and a one-line lede.

**When to use:** Multi-part decks (4+ sections). Gives the audience a pause-and-orient moment.

**Why it wins:** Creates rhythm. Without dividers, long decks feel monotonous.

**Reference:** Coaching workshop deck.

---

## 09. Keyboard Shortcuts

**What:** Full keyboard control — arrow keys or spacebar to navigate, T to toggle the current-slide timer, R to reset it, click progress dot to jump, « » buttons to jump by 5.

**When to use:** Every deck. Low cost, high affordance for live presenters.

**Why it wins:** Presenter doesn't need a clicker or mouse. Faster, more confident live delivery.

**Reference:** Both decks.

---

## Capability Pairings with Styles

Capabilities are mostly style-agnostic, but some pairings are especially strong:

- **Editorial Warmth + Timer** → workshop delivery
- **Terminal Brutalism + Click-to-Copy** → dev post-mortem with repro steps
- **Bento Modern + Expandable Tiles** → product launch with deep-dive Q&A
- **Magazine Feature + Reveal Animation** → keynote video recording
- **Cohort Dark + Embedded Video** → async course session

---

## Adding a New Capability

When you build a new affordance in a deck, add it here with:

- Name and 1-line "what" summary
- When to use
- Why it wins (the specific friction it removes)
- Reference implementation path

Keep capabilities composable. Every capability should be addable to any style without fighting it.
