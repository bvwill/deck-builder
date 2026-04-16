# Deck Builder

A Claude Code skill that builds polished, interactive HTML presentation decks from a conversation. One skill, one HTML file output, any brand, any audience.

## What It Does

Describe the moment -- who's in the room, what the format is, what it should feel like -- and the skill builds a complete presentation deck as a single `.html` file. No PowerPoint, no Google Slides, no build tools.

**What's inside:**
- **7 reference files** -- presentation psychology, narrative arcs, workshop pedagogy, speaker notes, style catalog, capabilities catalog, starter template
- **6 named styles** -- Editorial Warmth, Cohort Dark, Swiss Rigor, Terminal Brutalism, Magazine Feature, Bento Modern
- **9 interactive capabilities** -- timers, click-to-copy, word-by-word reveals, video embeds, expandable Bento tiles, persistent brand bar, progress rail, password gate, keyboard navigation
- **7 domain types** -- sales pitch, virtual workshop, lightning lesson, in-person workshop, all-hands, board review, keynote

[Loom Demo Video](https://www.loom.com/share/dbf241ef8f3d4a3aa018d8d7148e43a4)
## Install

```bash
git clone https://github.com/bvwill/deck-builder ~/.claude/skills/deck-builder
```

That's it. Next time you open Claude Code, say "build me a deck" and the skill activates.

**Works in:** Claude Code CLI, VS Code extension, JetBrains extension.

## Update

```bash
cd ~/.claude/skills/deck-builder && git pull
```

## Usage

### One-Shot (fastest)
```
Build me a deck -- lightning lesson on "5 Things Every PM Should Automate
This Quarter." Virtual, 50 people, punchy and practical. One-shot it.
```

### Collaborative (high-stakes)
```
I need a sales deck for a 30-person product team. Let's work through the
structure together before you build it.
```

### Show Me Options (exploring)
```
Show me what styles are available for a board review deck.
```

### Brand Matching
```
Build me a proposal deck. Match the style to stripe.com.
```
```
Use the images in ~/brand-assets/ as the source for the style.
```
```
Dark and sharp, like a dev tool dashboard.
```

## How It Works

The skill follows a 7-step workflow:

1. **Research** the actual content -- reads source material, not just what you paste
2. **Capture the moment** -- audience, format, feeling
3. **Choose a style** -- from the catalog, a URL, images, or a description
4. **Structure** the content into a narrative arc with domain awareness
5. **Build** from the starter template -- one HTML file, zero dependencies
6. **Open and iterate** -- edits in place, doesn't regenerate
7. **Deploy** (optional) -- to GitHub Pages with optional password protection

## Output

Every deck ships as a single `.html` file:
- Opens in any browser, works offline
- Arrow keys / click / spacebar to navigate
- Press **T** to start/stop timers on workshop slides
- Progress rail with section names
- Persistent brand bar on every slide
- Print-friendly

## File Structure

```
deck-builder/
├── SKILL.md                          # Core skill instructions
├── references/
│   ├── presentation-principles.md    # Cognitive science of presentations
│   ├── narrative-arc-templates.md    # 6 story structures mapped to decks
│   ├── speaker-notes-guide.md        # How to write complementary notes
│   ├── workshop-pedagogy.md          # Instructional design for training
│   ├── style-catalog.md              # 6 named visual styles with specs
│   └── capabilities-catalog.md       # 9 interactive affordances
├── assets/
│   └── starter-template.html         # HTML/CSS/JS shell for all decks
└── deck-builder-cheatsheet.html      # One-page visual overview
```

## Requirements

- [Claude Code](https://claude.ai/download) (CLI, VS Code, or JetBrains)
- A browser to view the output

## License

MIT
