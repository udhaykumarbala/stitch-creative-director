# stitch-creative-director

A creative direction skill for [Google Stitch](https://stitch.withgoogle.com) that produces dramatically better UI designs by guiding empathy discovery, aesthetic translation, and reference-based design system composition before any Stitch MCP tool call.

> "You will get better results with Stitch if you start your prompt with a design concept, a vibe, or a general aesthetic."
> -- Google's Stitch team ([source](https://www.youtube.com/watch?v=tnP_Q5mS1I8))

## The Problem

Most people prompt Stitch with vague instructions like "make me a landing page" or "design a portfolio site." The result: generic, directionless designs that look like every other AI-generated UI.

The fix isn't better prompting tricks. It's **creative direction** -- the same process a design lead would use before handing work to a designer.

## What This Skill Does

It acts as a **creative director layer** between you and Stitch. Before any `mcp__stitch__*` tool call, the skill walks through a structured process:

```
1. Empathy Canvas     -> Who is this for? What should they feel?
2. Aesthetic Search   -> Translate feelings into concrete design vocabulary
3. Reference Mapping  -> Match to archetypes, find example sites, resolve mixed styles
4. Stitch Composition -> Map direction to exact Stitch API parameters + designMd
5. Execute            -> Create project -> design system -> screen -> variants
```

The key insight from Google's own Stitch team: **abstract words like "make it look good" produce generic results. Concrete sensory language like "architectural limestone, ink on paper" gives Stitch something to build from.**

## What's Inside

```
stitch-creative-director/
├── SKILL.md                          # Core workflow (5-phase creative direction process)
├── references/
│   ├── design-archetypes.md          # 12 design archetypes with Stitch parameter mappings
│   ├── font-guide.md                 # All 29 Stitch fonts categorized by personality
│   └── mixing-styles.md             # Framework for mixing 2-3 design references
└── stitch-creative-director.skill    # Packaged skill (ready to install)
```

### Design Archetypes (12 built-in)

Each archetype maps a design feeling to concrete Stitch `create_design_system` parameters:

| Archetype | Feel | Example Sites |
|-----------|------|---------------|
| Editorial / Magazine | Authoritative, premium, story-driven | NYT, Bloomberg, Monocle |
| Developer / Technical | Precise, capable, no-nonsense | Linear, Vercel, Raycast |
| Warm Minimalism | Human, calm, trustworthy | Notion, Basecamp, iA Writer |
| Bold / Expressive | Energetic, creative, confident | Figma, Framer, Arc |
| Luxury / Premium | Exclusive, refined, timeless | Apple, Aesop, Rapha |
| Friendly / SaaS | Approachable, modern, trustworthy | Slack, Twilio, Canva |
| Brutalist / Raw | Authentic, unconventional, statement | Cargo, indie portfolios |
| Corporate / Enterprise | Professional, stable, scalable | Salesforce, IBM, Atlassian |
| Organic / Craft | Earthy, handmade, sustainable | Patagonia, Blue Bottle |
| Retro / Nostalgic | Vintage, playful, personality-driven | Poolside FM, indie games |
| Dashboard / Data | Clear, efficient, scannable | Grafana, Vercel Analytics |
| Portfolio / Creative | Personal, distinctive, curated | Award-winning portfolios |

### Font Personality Guide

All 29 fonts available in Stitch, categorized by personality:

- **Serif (Authority):** Newsreader, EB Garamond, Libre Caslon Text, Domine, Literata, Noto Serif, Source Serif 4
- **Geometric Sans (Modern):** Geist, Inter, DM Sans, Space Grotesk, IBM Plex Sans, Sora
- **Humanist Sans (Warm):** Public Sans, Plus Jakarta Sans, Nunito Sans, Lexend, Rubik, Manrope
- **Neutral Sans (Invisible):** Source Sans 3, Work Sans, Arimo, Hanken Grotesk, Be Vietnam Pro, Spline Sans
- **Display (Statement):** Epilogue, Montserrat, Metropolis

### Style Mixing Framework

When you reference 2-3 sites ("I want Linear's dark mode but warmer, like Notion"), the skill:

1. **Decomposes** each reference into 5 aspects: Color/Mood, Typography, Layout, Imagery, Interaction
2. **Detects conflicts** (two references claiming the same aspect differently)
3. **Resolves** by asking which feeling matters more
4. **Synthesizes** into a single coherent direction with exact Stitch parameters

Includes 5 pre-mapped "proven combinations" (Developer+Editorial, Luxury+Warm, SaaS+Bold, Corporate+Developer, Editorial+Organic) and anti-pattern warnings for mixes that fight.

## Installation

### Claude Code (CLI)

```bash
# Install from the .skill file
claude skill install stitch-creative-director.skill

# Or install from GitHub
claude skill install udhaykumarbala/stitch-creative-director
```

### Manual Installation

Copy the `SKILL.md` and `references/` directory to your Claude Code skills directory:

```bash
# Global (all projects)
cp -r stitch-creative-director/ ~/.claude/skills/stitch-creative-director/

# Project-level
cp -r stitch-creative-director/ .claude/skills/stitch-creative-director/
```

## Usage

The skill triggers automatically when you:
- Say "design in Stitch", "create a Stitch project", "build me a UI", "make a landing page"
- Use any `mcp__stitch__*` tool
- Describe a site/app you want to build visually

### Example: Quick Start

```
You: "Build me a portfolio site in Stitch"

Skill activates -> Asks empathy questions -> Matches archetypes ->
Maps to Stitch params -> Creates project with rich designMd ->
Generates screen with intentional direction
```

### Example: With References

```
You: "I want a developer portfolio like Linear's dark mode but with
      warm serif headings like a literary magazine"

Skill activates -> Decomposes references:
  Color/Mood -> Linear (dark, monochrome, purposeful accent)
  Typography -> Editorial (serif headlines at scale)
  Layout     -> Linear (clean grid, functional density)
  
-> Resolves into coherent direction
-> Maps to: DARK, headlineFont: NEWSREADER, bodyFont: GEIST,
   labelFont: SPACE_GROTESK, MONOCHROME, ROUND_FOUR
-> Writes rich designMd creative brief
-> Creates project in Stitch
```

### Example: Vague Input (skill helps most here)

```
You: "I want something modern and clean for my startup"

Skill asks: "Which modern? Vercel-sharp or Figma-playful or Apple-minimal?"
Skill asks: "Who lands on this site? What should they feel in 3 seconds?"
Skill asks: "What's the anti-vibe? What should it NOT feel like?"

-> Translates vague words into concrete design vocabulary
-> "Modern and clean" becomes "generous whitespace, geometric sans at scale,
    monochrome with a single purposeful accent, content-first layout"
```

## The Process (From Google's Stitch Video)

This skill is built on design principles shared by Google's Stitch team:

### 1. Start with Empathy, Not Aesthetics
Think about what your user needs and how you want them to feel. Not color, typography, and layouts first.

### 2. Act as the Creative Director
Stitch is the designer, you're the creative director. Like coding agents benefit from you being their tech lead.

### 3. Use Sensory Language, Not Abstract Words
"Make it look good" -> generic. "Architectural limestone canvas, ink-dark primary, clay-red accent for CTAs" -> intentional design.

### 4. Color is a Hierarchy, Not a Palette
| Role | Purpose | Screen % |
|------|---------|----------|
| Neutral | Canvas, background | 80-90% |
| Primary | Ink, headings, body text | Highest volume |
| Secondary | Subdued, supports primary | Supporting |
| Tertiary | Accent, CTAs, most important button | < 5% (loudest, least used) |

### 5. Layout Through Physical Metaphors
"If my website was a book, what kind of book?" Coffee table book -> lookbook layout. Field guide -> editorial column with margin annotations. Newspaper -> bold headline grid.

### 6. The designMd is the Most Powerful Lever
Stitch's `designMd` field accepts freeform markdown as a creative brief. A well-written designMd with sensory language, physical metaphors, and do's/don'ts is the single biggest lever for design quality.

### 7. Iterate with Variants
Use `generate_variants` with specific aspect targeting (layout, images, text, colors) and creativity levels (Refine, Explore, Reimagine).

## Requirements

- [Google Stitch MCP server](https://stitch.withgoogle.com) connected to your Claude Code environment
- The `mcp__stitch__*` tools available (create_project, create_design_system, update_design_system, generate_screen_from_text, generate_variants)

## Inspiration

Built from insights in ["One Design Decision to Create Better Results in Stitch"](https://www.youtube.com/watch?v=tnP_Q5mS1I8) by Google for Developers.

## License

MIT
