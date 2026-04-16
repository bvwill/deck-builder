---
name: deck-builder
description: "Build polished, interactive HTML presentation decks styled to match any brand, audience, or moment. Use this skill whenever the user mentions building a deck, presentation, slides, pitch deck, workshop deck, course slides, lightning lesson, keynote, all-hands deck, sales pitch, or wants to create any kind of visual presentation. Also trigger when the user says 'show me my options' in a deck context, references a named style like 'Swiss Rigor' or 'editorial warmth', asks to match a brand or website's look, or wants to turn an outline or content into a presentation. Even casual mentions like 'I need slides for Thursday' or 'help me put together something for the board' should trigger this skill."
---

# Deck Builder

Build single-file HTML presentation decks that match the moment -- not a template. Each deck ships as one `.html` file with CSS and JS inline, opens in any browser, works offline, and can be deployed to a password-protected URL for sharing.

The core thesis: **every presentation is a moment with an audience, a format, and a feeling.** Get those three things right and the design follows. The user should never have to think about CSS, fonts, or layout -- they describe the moment and you build the deck.

## How This Skill Works

There are three modes. Ask the user which one they want, or infer from context:

### Mode 1: One-Shot
The user gives you content + context and you build the whole thing. Best when they're in a hurry or trust you to make good choices. You should still apply meaningful thought to the structure -- what story does this deck tell? What's the narrative arc? How do you earn the audience's attention slide by slide?

### Mode 2: Collaborative
You work through the deck together. You propose the layout, flow, and style -- the user reacts and edits before you build. Best when they're not sure what they want, or the stakes are high enough to warrant iteration. For high-stakes decks (sales proposals, client-facing, board), default to this mode.

In collaborative mode, your proposal should include:
- Specific slide count and titles
- One-line description of what each slide does and why it earns its place
- The narrative arc reasoning (not just "slide 3 = topic X" but "slide 3 is the curriculum overview -- interactive bento so they explore at their own pace")
- Which capabilities you'd include and why
- What you'd leave out and why

### Mode 3: Show Me My Options
The user wants to see what's possible. Generate a visual sampler: a single HTML file with thumbnail-style previews of the available styles AND a showcase of interactive capabilities. Each option gets a label and a one-line description of when to use it. End with: *"These are starting points. If you have a different idea -- a brand site, a screenshot, a vibe -- just describe it and we'll build from there."*

For the style sampler, read `references/style-catalog.md`. For the capabilities showcase, read `references/capabilities-catalog.md`. Don't just list them -- render mini visual examples so the user can SEE the difference.

---

## The Workflow

### Step 1: Research Before You Propose

Before proposing a structure, **research the actual content**. If the user references a project, wiki page, proposal doc, or curriculum -- read it. Don't just structure the text they pasted. The best decks come from understanding what the content actually IS, not just reformatting what the user handed you.

For client/sales decks: read the deal page, person page, project page, and any prior communication. The deck should reflect the full relationship context, not just the proposal text.

For course/workshop decks: read the session plans and any student feedback. What actually works in delivery often differs from what's on the plan.

### Step 2: Capture the Moment

Before touching any HTML, get three things:

1. **Audience** -- Who's in the room? Board members, engineers, students, prospects, a Loom viewer? If async, who's the primary reader and who's the secondary? (e.g., "Alex makes the decision, Jordan evaluates the fit for their ICs")
2. **Format** -- Live presentation, recorded video (Loom), async reading, workshop with working sessions, teaching with exercises? **Async decks need to be self-explanatory without voiceover** -- this changes everything about density, interactivity, and navigation.
3. **Feeling** -- One or two adjectives max. "Confident and warm." "Sharp and rigorous." "Raw and fast." "Inviting and patient."

Also ask about practical constraints:
- How many slides (or let you decide)?
- Any content they'll paste in, or do they want you to write it?
- Any specific embeds: images, Looms, diagrams, links, copy blocks?
- Do they need interactive capabilities (timers, click-to-copy, etc.)?
- Branding: their name, company, domain for the top bar? Should brand bar elements link out (LinkedIn, website)?
- Will this be deployed to a URL? Need password protection?

If the user has already given you most of this context (from the conversation or the prompt), don't re-ask. Extract what you can and confirm: *"Here's what I'm building -- does this look right before I start?"*

### Step 3: Choose a Style

Four paths to a style:

**Path A: Named style from the catalog.**
Read `references/style-catalog.md`. It has 6 named styles with full specs (typography, palette, layout logic, use cases). If the user says "Swiss" or "editorial" or "brutalist" -- you know exactly what to build.

**Path B: Style from a URL.**
The user gives you a company website or brand reference. Spawn a subagent to research the brand thoroughly -- don't just scrape the homepage. Check:
- The brand site itself (CSS custom properties, hero colors, typography)
- Brand portal if one exists (e.g., `brand.company.com`) for official guidelines
- Design aggregator sites for curated brand analysis
- Case studies that show the brand applied to different surfaces

Extract concrete tokens: hex codes, font names (with Google Fonts fallbacks for licensed typefaces), corner radius conventions, spacing density, tone guidelines. The goal is to build a deck that feels like it was made inside their brand system.

**Path C: Style from screenshot(s) or image folder.**
The user provides one or more images (screenshots, mood boards, examples they like) or points to a folder of images (e.g., a LinkedIn carousel export, a brand asset folder). Analyze visually:
- Dominant colors and accent colors (extract specific hex values)
- Typography character (rounded, sharp, classic, modern) and weight patterns
- Layout patterns (grid, asymmetric, card-based, text-heavy)
- White space ratio
- Recurring design motifs (accent bars, border treatments, decorative blocks, highlight styles)
- Overall mood

**When given a folder of images:** Read *all* of them, not just the first one. Carousel posts, slide exports, and brand asset folders contain the full design system -- colors shift between slides, layout patterns vary, and motifs repeat. Synthesize across the set to extract the complete visual language: primary/secondary/accent colors, which elements are structural (appear on every image) vs. decorative (appear once), and how hierarchy is created (size, weight, color, position). The goal is to derive a coherent design system, not match a single screenshot.

Describe what you see back to the user before building: *"I'm seeing a dark, spacious layout with teal accents and monospace type -- feels like a developer tool dashboard. Does that match what you're going for?"*

**Path D: Describe it.**
The user just tells you what they want: "dark and moody with gold accents" or "clean like Apple's keynotes" or "like a premium magazine." Work with that directly.

### Step 4: Structure the Content

This is where the one-shot vs collaborative split matters.

**One-shot:** Take whatever content the user gave you (outline, notes, bullet points, a transcript, raw ideas) and structure it into a narrative arc. Think about:
- What's the opening hook? (Why should the audience care in the first 10 seconds?)
- What's the journey? (Problem → insight → solution → evidence → payoff)
- What's the closing action? (CTA, next step, question to sit with)
- Where do section dividers go? (Create breathing room in decks longer than 6 slides)
- Which slides need interactive capabilities? (Working sessions get timers, resource slides get copy blocks)

Apply domain awareness:
- **Sales pitch / proposal**: This is an "executive visual companion" -- scannable, explorable, self-explanatory without voiceover. Lead with the reframe, prove you understand the client's context, show the structure, close with what you need from them and next steps. Consider whether interactive bento tiles can replace linear detail slides -- one explorable overview often beats four sequential slides.
- **Workshop/class (in-person)**: Alternate instruction → work time → share-back. Timers on every work slide. "Turn to your neighbor" exercises work. Handouts can supplement. Energy is managed through room dynamics -- standing, moving, pair work.
- **Workshop/class (virtual)**: Read `references/workshop-pedagogy.md` for the full instructional design framework. Key differences from in-person: chat is the primary interaction channel (not hand-raising), breakout rooms replace "turn to your neighbor" (groups of 2-3, 3-5 minutes, auto-return), attention drops 30% faster, and the "screenshot this" summary slide is critical because there's no physical handout. Design a participation moment every 5-7 minutes: chat prompt, poll, reflection pause, or working exercise. Handwritten-style annotations (Caveat font) should be audience-facing ("Be honest -- have you ever asked this?") not facilitator-facing ("Pause here and ask the room").
- **Lightning lesson (virtual, 25-35 min)**: A compressed virtual workshop for 50-200 attendees. Defaults: chat-first engagement in the first 2 minutes, a contrast/tension slide before the teaching content, 4-6 content slides with varied layouts, one peak moment with word-by-word reveal, a cheat-sheet summary slide, one working exercise (5 min timer), optional breakout practice (3 min), and a bookend close. Read `references/workshop-pedagogy.md` for the pedagogical arc. The constraint is time -- every slide must earn its place, and the exercise must produce a usable artifact, not just "reflection."
- **All-hands**: Lead with the headline, then context, then what's next. Keep it under 15 slides.
- **Executive/board**: Numbers first, adjectives last. Swiss Rigor style. Every slide should pass the "so what?" test.
- **Keynote/video**: Pacing matters more than density. Magazine or Editorial style. Reveal animations earn their keep here.
- **Team launch/kickoff**: Bento style. Energy, spatial, modern. One hero metric, supporting tiles around it.

**Collaborative:** Present the proposed structure as a numbered outline with slide titles and one-line descriptions. Ask: *"Here's what I'm thinking for the flow. Want me to build this, change anything, or see a couple different versions?"*

If they ask for multiple versions, generate 2-3 variant outlines (different narrative arcs, different emphasis points) and let them pick or mix.

**The fewer-slides principle:** Always look for opportunities to consolidate. An interactive bento overview slide that lets the reader explore 4 topics at their own pace is better than 4 sequential slides with the same content. This is especially true for async decks where the reader controls the pace. Start by proposing the interactive version; add linear slides only if the content demands it.

### Step 5: Build the Deck

Read `assets/starter-template.html` for the common shell. It includes:
- Slide container with fade transitions
- Top branding bar (customizable name, domain, company)
- Bottom nav rail with progress dots, prev/next, keyboard shortcuts
- Timer infrastructure (for work-time slides)
- Click-to-copy infrastructure
- Core CSS reset and layout primitives

Layer in:
1. **Style CSS** -- from the chosen style (catalog or custom). Define as CSS custom properties at `:root` so they're easy to tune.
2. **Slide content** -- each slide as a `<section class="slide">` with a `data-section` attribute for the progress rail.
3. **Capabilities** -- only the ones this deck needs. Don't add a timer to a sales pitch. Don't add reveal animations to a data-heavy board deck unless it serves the story.
4. **Embeds** -- images as inline `<img>` (base64 if local, URL if remote), videos as `<iframe>` (Loom, YouTube, Vimeo), diagrams as inline SVG where possible.
5. **Copy blocks** -- `data-copy` attributes on any element that should be click-to-copy. Support both single-line (links) and multi-line (announcements, prompts, code snippets).

Everything in ONE HTML file. No external dependencies except Google Fonts (loaded via `<link>`). The file should work if you open it from your desktop with no server.

#### Visual Personality — Every Slide Must Be Interesting

A deck that just puts content on backgrounds is a document pretending to be a presentation. HTML can do things PowerPoint and Google Slides can't. Use that advantage. Every slide should have at least one of these:

**Entrance animations** — free wow for recorded and live-presented decks:
- Word-by-word reveal: stagger opacity + translateY at 0.08-0.15s per word. Use for big statements, recommendations, mission slides.
- Staggered list items: each bullet fades in 0.2s after the previous. Use for lists, risks, "more time" slides.
- Growing bars: width animates from 0 to target over 0.6s. Use for timelines, gauges, progress indicators.
- Line grows: a thin accent-colored line animates its width. Use after mission statements or section breaks.

Trigger animations when `.slide.active` is applied:
```css
.slide.active .reveal-word { animation: revealWord 0.5s forwards; }
.slide.active .reveal-word:nth-child(2) { animation-delay: 0.08s; }
```

**Staggered and overlapping layouts** — never put 3+ cards in a flat grid:
- Quote cards: offset each card right 1-2rem and down 0.5rem from the previous. Creates depth.
- Person cards: vary translateY per card for a staggered row. Hover lifts one, dims others.
- Risk items: slight stagger like quote cards. Amber border instead of green to signal risk.

**Decorative elements** — the design details that make it feel crafted:
- Large faded quotation marks (3rem, opacity 0.15) positioned behind quote text
- Handwriting font (Caveat) annotations rotated 2-3 degrees, overlaid on content. **For virtual and recorded decks, these should be audience-facing** -- the presenter's voice speaking directly to the viewer ("Be honest -- have you ever asked this?" or "If it feels awkward, you're doing it right."), not facilitator notes ("Pause here and ask the room"). Size at 1.4-1.6rem so they're readable on screen share. Limit to one per slide max -- they lose charm if overused.
- Accent-color glow on headshots (box-shadow with blurred accent color)
- Radial gradient glows behind key moments (recommendation, mission, closing)
- Subtle pulse animation on highlighted table rows (very subtle — 2-3% opacity oscillation)

**Data moments** — when a number matters, make it LARGE:
- Key metrics ($120M, 50%, ~5/100) should be 2-4rem, in the accent color, not inline with body text
- Pair the number with a one-line "so what" in regular text below it
- A number that looks like body text is a number that gets skipped

**Interactive hover states** on cards and table rows:
- Cards: hover lifts (translateY -6px), increases shadow, siblings dim (opacity 0.5-0.6). Transition 0.3-0.4s.
- Table rows: hover brightens background. Recommendation/winner row has accent tint always visible.
- Smooth transitions on everything — nothing should snap.

**Bookend devices** — repeated slides with a twist:
- Mission statement appears early and echoes near the close. The close version has one word changed (e.g., "everyone" → "us"). Animate the word swap if possible (fade out old, fade in new).
- Section titles can echo as callbacks ("Why?" appears twice — first as intro, last as payoff with all evidence filled in).

**The anti-pattern to avoid: literal translation.** If you're importing from PPTX, Google Slides, or an outline, the HTML version must be BETTER than the original, not a 1:1 reproduction. The original was constrained by its tool. You aren't. Every slide should have something the original couldn't do — an animation, an interaction, a layout that overlaps elements, a hover state. If you build a slide that PowerPoint could have built identically, you've wasted the format.

#### Importing from PPTX

When recreating an existing deck from a PPTX file:

1. **Extract first:** Unzip the PPTX (`unzip file.pptx`), read slide XMLs for content, theme XML for colors/fonts, notesSlides for speaker notes, media/ for images.

2. **Consolidate:** PPTX decks often have "filler" slides (video-still placeholders, progressive reveal stages of the same table). Merge these — put the video still as an inline thumbnail on the quote slide, collapse 3-stage table reveals into one interactive table.

3. **Enhance, don't replicate:** For every slide, ask: "what can HTML do here that the PPTX couldn't?" Add entrance animations, hover states, overlapping layouts, decorative elements. The rebuild should make the original feel flat by comparison.

4. **Preserve the narrative structure:** The story arc, the pacing, the bookend devices — keep all of these. Change the visual execution, not the narrative spine.

5. **Copy images to img/ directory:** Reference with relative paths (`img/image1.png`). For GitHub Pages deployment, the images deploy alongside the HTML.

#### Contrast Check Before Shipping

After building the deck, visually verify contrast before showing the user. This is non-negotiable -- a deck nobody can read is worse than no deck.

Check these five things:
1. **Default body color is set.** On dark backgrounds, `body { color: var(--ink); }` is mandatory. Browser default is black text, which is invisible on dark backgrounds. Every element without an explicit color class will inherit from body. If body has no color, you will ship black text on dark backgrounds. This has happened. Don't let it happen again.
2. **Text on every background.** Primary text must be clearly readable. Secondary text must be distinguishable from the background, not just theoretically different.
3. **Cards vs. page surface.** Card backgrounds must be visibly distinct from the page background. If you squint and they blend, bump the card lighter (on dark mode) or darker (on light mode).
4. **Accent colors pop.** The accent color must be clearly visible against its background. A teal that looks great on white will disappear on dark navy.
5. **Status colors are distinguishable.** Red, orange, yellow, green must be clearly different from each other AND readable against the card/page surface.

**Overflow check:** After building, verify that no text, labels, or hints are pushed below the visible slide area. Elements inside flex containers with `flex: 1` siblings can silently overflow. Check that all content is visible without scrolling on each slide.

**The most common mistake:** taking brand tokens designed for a light-mode website (dark headers on white content) and applying them to a full dark-mode deck. Brand colors are designed for their original context. When you change the context (light → dark, web → presentation), you must adapt the palette, not copy it. Keep the brand *family* (same hue range), but adjust lightness and saturation so the colors actually work on the new surface.

A practical test: if the background is `#0a2133` and the accent is `#03657f`, those are only 15-20% apart in lightness. That's invisible. The accent needs to be at least 40-50% lighter than its background to read as an accent.

#### Building Interactive Bento Tiles

For decks where multiple topics, features, or sections need to be explorable (proposals, product overviews, curriculum summaries), use expandable bento tiles:

**Collapsed state must have substance.** Don't just show a title -- include:
- 3 preview bullets showing what's inside (concrete, not generic)
- A clear expand affordance: "See full detail →" with an arrow that animates on hover
- Visual differentiation between tiles (graduated accent colors on left borders, not uniform)

**Expanded state** fills the grid area with full detail content. Other tiles fade out (opacity 0.15, scale 0.97) with a smooth transition.

**Use the FLIP technique** (First-Last-Invert-Play) for the expand/collapse animation. CSS cannot transition between grid layout and absolute positioning -- you must:
1. Capture the starting bounding rect
2. Apply the class change (which switches to `position: absolute; inset: 0`)
3. Calculate the inverse transform
4. Animate from the inverse to identity

```js
function flipTo(tile, applyChange) {
  const startRect = tile.getBoundingClientRect();
  applyChange();
  const endRect = tile.getBoundingClientRect();
  const dx = startRect.left - endRect.left;
  const dy = startRect.top - endRect.top;
  const sx = startRect.width / endRect.width;
  const sy = startRect.height / endRect.height;
  tile.style.transformOrigin = 'top left';
  tile.style.transition = 'none';
  tile.style.transform = `translate(${dx}px, ${dy}px) scale(${sx}, ${sy})`;
  tile.offsetHeight; // force reflow
  requestAnimationFrame(() => { tile.style.transition = ''; tile.style.transform = ''; });
}
```

**Navigation must pause while tiles are expanded:**
- Click-to-navigate (left/right screen halves) must check for `.bento.has-expanded` and bail out
- Keyboard arrow keys and spacebar must be blocked
- Escape key should close the expanded tile
- Clicks inside `.tile` elements must not bubble to the navigation handler

#### Building Click-to-Navigate

Add PowerPoint-style click navigation: clicking the left ~35% of the screen goes back, right ~35% goes forward, middle is dead zone. Always exclude links, buttons, interactive elements, and nav from this handler:

```js
document.querySelector('.stage').addEventListener('click', (e) => {
  if (e.target.closest('a, button, [data-copy], nav, .tile')) return;
  if (document.querySelector('.bento.has-expanded')) return;
  const x = e.clientX / window.innerWidth;
  if (x < 0.35) go(idx - 1);
  else if (x > 0.65) go(idx + 1);
});
```

#### Brand Bar Links

For async decks, make the presenter name and company in the top bar clickable links (LinkedIn profile, website). Use `target="_blank"` and style as no-underline until hover. This is a subtle credibility signal for decks shared via URL.

#### Password Gate

For client-facing or private decks, add a branded password overlay. Always:
- Style it to match the deck's brand (not a browser `prompt()`)
- Hash the password with SHA-256 using Web Crypto API -- never store plaintext
- Persist the unlock for the browser session (sessionStorage)
- Support Enter key on the input field
- Add a couple of decoy variables near the hash to obscure which value is real

```js
async function hashPwd(pwd) {
  const data = new TextEncoder().encode(pwd);
  const buf = await crypto.subtle.digest('SHA-256', data);
  return Array.from(new Uint8Array(buf)).map(b => b.toString(16).padStart(2, '0')).join('');
}
```

To get the hash for a new password, run in terminal:
```bash
echo -n 'your-password' | shasum -a 256
```

### Step 6: Open and Iterate

After building, open the deck in the browser:
```bash
open path/to/deck.html
```

Then ask: *"Take a look. What do you want to change? I can adjust the style, reorder slides, add/remove capabilities, or rework any content."*

Common iteration requests and how to handle them:
- "Make it darker/lighter" → adjust CSS custom properties
- "This slide is too dense" → split into two slides or reduce content
- "Can you add a timer here?" → add work-time slide with timer infrastructure
- "The font feels wrong" → swap the font family in custom properties
- "Match this screenshot instead" → re-derive style from the new reference
- "These slides feel redundant" → consolidate into an interactive bento overview
- "The tiles are too bland" → add preview bullets, visual differentiation, and clear expand CTAs
- "Text is too small" → likely a 4K monitor issue; bump base font size or suggest Cmd++ for review

### Step 7: Deploy (Optional)

After the user is happy, offer deployment:

*"Want to share this as a URL instead of a file? I can deploy it to GitHub Pages -- you'd get a permanent link you can share."*

**GitHub Pages deployment (full flow):**

1. **Determine the target repo.** Convention: a `decks` repo outside the main project workspace. If it doesn't exist yet, create it.

2. **If the decks repo doesn't exist:**
   ```bash
   mkdir -p /path/to/decks/{deck-slug}
   cp deck.html /path/to/decks/{deck-slug}/index.html
   cd /path/to/decks
   git init
   git add {deck-slug}/index.html
   git commit -m "Add {deck-name}"
   gh repo create {username}/decks --public --source=. --push --description "Presentation decks"
   gh api repos/{username}/decks/pages -X POST -f "source[branch]=main" -f "source[path]=/"
   ```

3. **If the decks repo already exists:**
   ```bash
   cp deck.html /path/to/decks/{deck-slug}/index.html
   cd /path/to/decks
   git add {deck-slug}/index.html
   git commit -m "Add {deck-name}"
   git push
   ```

4. **URL pattern:** `{username}.github.io/decks/{deck-slug}/`

5. **Important:** GitHub Pages on the free plan requires a **public** repo. This is fine when the deck has a password gate -- the HTML source is public but the content is behind a hashed password. Not Fort Knox, but sufficient for proposals and client decks.

6. **Tell the user** the password and URL should be sent separately (URL in email, password in a text/Slack). Don't put both in the same message.

7. **Custom domain option:** If the user wants a cleaner URL (like `decks.yoursite.com`), they need one DNS CNAME record pointing to `{username}.github.io` plus the custom domain setting in the repo's Pages configuration.

**Naming convention:** Use descriptive slugs, not dates. Git handles versioning. Examples:
- `leadership-offsite/`
- `client-proposal-acme/`
- `q2-product-launch/`

---

## Key Principles

**The deck is a tool, not a slideshow.** Whenever a capability (timer, copy block, embed, expandable tile) would remove friction during the actual use of the deck, include it. The best decks do work during the meeting -- or, for async decks, do work during the reader's exploration.

**Fewer slides, more interactivity.** Always ask: can an interactive overview replace multiple linear slides? A 6-slide deck with one expandable bento is better than a 10-slide deck with four topic slides that all look the same. The reader explores what they care about and skips what they don't.

**Show, don't tell.** Don't describe what a style looks like -- render it. Don't explain what a timer does -- build one that works. The user should be able to see and interact with everything before committing.

**Match the moment, not the template.** A board review and a team kickoff should never look the same. The style, density, pacing, and capabilities should all shift based on who's in the room and what the deck needs to accomplish.

**One file, zero build steps.** Every deck ships as a single `.html` file. No npm, no build tools, no server required. Open it in Chrome and present. This is a hard constraint -- it's what makes the workflow fast and the output portable.

**Iterate in place.** When the user wants changes, edit the existing file. Don't regenerate from scratch unless they ask for a fundamentally different approach. Small edits compound into a polished deck faster than re-rolls.

**Branding persists.** The top bar with the user's name/domain/company should appear on every slide. When the deck is recorded, screenshotted, or shared, the brand travels with every frame.

**Research the content, don't just format it.** Read the wiki, the project page, the prior emails, the curriculum docs. The best decks come from understanding what the content actually is and restructuring it for the audience -- not from reformatting what the user pasted.

**Speaker notes never go on the slides.** Talk tracks, facilitator cues ("say this," "pause here," "narrate while it builds"), timing notes, and any text meant for the presenter but not the audience must NEVER appear in the HTML deck. The slides are what gets projected -- anything that breaks the fourth wall ruins the presentation. If the user requests speaker notes, generate them as a separate markdown file (e.g., `speaker-notes.md`) alongside the deck, keyed by slide number. The deck file stays clean.

---

## Reference Files

- `references/presentation-principles.md` -- The psychological and communication principles behind presentations that create moments rather than slideware. Read this before structuring any deck. It covers: dual coding, contrast structure, peak-end rule, chunking, visual density, and the "so what" mechanism -- each with failure modes and practitioner patterns.
- `references/narrative-arc-templates.md` -- Six proven story structures (Pixar Story Spine, Hero's Journey, Man in a Hole, The Quest, Rebirth, Problem-Agitate-Solution) with presentation-mapped beats, quick selector by deck type, and guidance on combining arcs. Read this when choosing how to structure the narrative.
- `references/speaker-notes-guide.md` -- How to write notes that complement slides rather than duplicate them. Covers the four note types (so what, transition, story prompt, timing), per-arc note guidance, opening/closing note conventions, and formatting tags. Use when building decks where speaker notes matter.
- `references/workshop-pedagogy.md` -- Instructional design principles for training, workshop, and education decks. Covers: earning tension before solutions, visual pattern variation, participation cadence (every 5-7 min), the "screenshot this" moment, audience-facing annotations, artifact-producing exercises, and virtual-specific mechanics (chat, breakouts, energy management). Read this whenever the deck's purpose is teaching, training, or skill-building.
- `references/style-catalog.md` -- The 6 named visual styles with full specs (typography, palette, layout, use cases). Read this when the user picks a named style or asks to see options.
- `references/capabilities-catalog.md` -- The 9 interactive affordances (timer, copy-to-clipboard, reveal animation, video embed, expandable bento, top-brand bar, progress rail, section dividers, keyboard shortcuts). Read this when deciding which capabilities to include.
- `assets/starter-template.html` -- The common HTML/CSS/JS shell. Start every deck from this base.
