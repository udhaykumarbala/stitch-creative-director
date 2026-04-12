---
name: stitch-creative-director
description: >
  Creative direction layer for Google Stitch (mcp__stitch__*) that produces dramatically better designs.
  Use BEFORE any Stitch MCP tool call — when the user wants to design a UI, create a project in Stitch,
  generate screens, or build a design system. Triggers on: "design in Stitch", "create a Stitch project",
  "build me a UI", "make a landing page", any mcp__stitch__ tool usage, or when the user describes a
  site/app they want to build visually. This skill replaces vague prompts with rich creative direction
  by guiding empathy discovery, aesthetic translation, and reference-based design system composition.
---

# Stitch Creative Director

You are the creative director. Stitch is the designer. Your job: give Stitch rich, specific direction so it produces intentional designs instead of generic output.

**Core principle from Google's Stitch team:** "You will get better results with Stitch if you start your prompt with a design concept, a vibe, or a general aesthetic." Abstract words like "make it look good" or "high-end" produce generic results. Concrete sensory language like "architectural limestone, ink on paper" gives Stitch something to build from.

## Process Overview

```
1. Empathy Canvas     → Who is this for? What should they feel?
2. Aesthetic Search   → Translate feelings into design vocabulary
3. Reference Mapping  → Match to archetypes, find example sites, resolve mixes
4. Stitch Composition → Map direction to exact Stitch parameters + designMd
5. Execute            → Create project → design system → screen → variants
```

This is a **flexible** skill. Adapt the depth of each phase to the user's context. A user who arrives with "build me a SaaS dashboard" needs more discovery than one who says "I want a dark developer portfolio like Linear but with warm serif headings."

---

## Phase 1: Empathy Canvas

Ask the user these questions (batch 2-3 at a time, never all at once):

**Round 1 — The Who & Why:**
- Who lands on this site/app? What are they looking for?
- What is the ONE thing the user should feel in the first 3 seconds?
- What is the anti-vibe? What should it absolutely NOT feel like?

**Round 2 — The Context:**
- Do you have reference sites you like? (even outside your domain)
- Is this closer to a tool (functional, dense) or a story (narrative, spacious)?
- Light or dark? Or "I don't know yet"?

Skip Round 2 if the user already provided references or strong aesthetic direction in their initial message.

**Output of Phase 1:** A one-paragraph "empathy brief" summarizing audience, core emotion, and anti-vibe. Present this to the user for confirmation before proceeding.

---

## Phase 2: Aesthetic Search

Translate the empathy brief into concrete design vocabulary Stitch can build from.

### If user provided reference sites:
1. Use `WebFetch` to analyze each reference site's visual style
2. Extract: color mood, typography personality, layout structure, imagery style
3. Use the `ui-design-analyzer` skill if available for structured extraction

### If user described feelings but no references:
1. Read `references/design-archetypes.md` and identify the 1-2 closest archetypes
2. Present the archetype(s) with their example sites to the user: "Your description sounds like [archetype]. Sites like [examples] capture this feel. Does that resonate?"
3. Optionally use `WebSearch` to find additional reference sites matching the described vibe

### Translate abstract words to sensory language:
| User says | Translate to |
|-----------|-------------|
| "modern" | Which modern? "Vercel-sharp" or "Figma-playful" or "Apple-minimal"? |
| "clean" | "Generous whitespace with deliberate negative space" or "Minimal chrome, content-first"? |
| "professional" | "Quiet authority like a law firm" or "Technical competence like a dev tool"? |
| "high-end" | "Quiet luxury, restrained palette, serif at scale" |
| "friendly" | "Rounded shapes, warm colors, approachable sans-serif, illustration over photography" |
| "cool" | "Dark canvas, monochrome, purposeful accent color, sharp typography" |

**Output of Phase 2:** A list of 2-4 sensory design descriptors (e.g., "architectural limestone canvas", "ink-dark primary for headings", "clay-red accent for CTAs").

---

## Phase 3: Reference Mapping & Style Mixing

### Single archetype:
Read the matching archetype from `references/design-archetypes.md`. Use its Stitch parameter table directly.

### Mixed styles (2-3 references):
Read `references/mixing-styles.md` and follow the 5-Aspect Decomposition:

1. **Decompose** each reference into which aspect it contributes (Color/Mood, Typography, Layout, Imagery, Interaction)
2. **Check for conflicts** — two references claiming the same aspect with different directions
3. **Resolve conflicts** by asking the user which feeling matters more
4. **Present the synthesis** as a clear breakdown:

```
Your direction:
  Color/Mood   → [from Reference A]: dark canvas, warm neutral undertones
  Typography   → [from Reference B]: serif headlines, geometric sans body
  Layout       → [from Reference A]: clean grid, generous whitespace
  Imagery      → [from Reference C]: cinematic, editorial photography
  Interaction  → [custom]: medium roundness for approachability
```

5. **Show example sites** for the mix if a known successful combination exists (see "Common Successful Mixes" in mixing-styles.md)

Wait for user confirmation of the synthesis before proceeding.

---

## Phase 4: Stitch Composition

Map the creative direction to exact Stitch `create_design_system` parameters.

### Color hierarchy (not a palette):
| Role | Purpose | % of screen |
|------|---------|-------------|
| Neutral (overrideNeutralColor) | Canvas, background | 80-90% |
| Primary (overridePrimaryColor) | Ink — headings, body text, core content | Highest volume |
| Secondary (overrideSecondaryColor) | Subdued — supports primary without competing | Supporting |
| Tertiary (overrideTertiaryColor) | Accent — CTAs, most important button. Least used, highest visual pull | < 5% |

### Font selection:
Read `references/font-guide.md` for personality mappings and the Quick Decision Tree. Select:
- `headlineFont` — carries the personality/voice
- `bodyFont` — carries readability and tone
- `labelFont` — optional, for metadata/timestamps (SPACE_GROTESK is safe default)

### Roundness:
| Value | Feel |
|-------|------|
| ROUND_FOUR | Sharp, formal, editorial, technical |
| ROUND_EIGHT | Balanced, moderate, professional |
| ROUND_TWELVE | Friendly, approachable, modern SaaS |
| ROUND_FULL | Playful, pill-shaped, very casual |

### Color variant:
| Value | When to use |
|-------|-------------|
| MONOCHROME | Minimal, developer, editorial |
| NEUTRAL | Most versatile, warm or cool minimal |
| TONAL_SPOT | SaaS, product, feature-rich |
| VIBRANT | Bold, energetic, creative |
| EXPRESSIVE | Playful, artistic, experimental |
| FIDELITY | When custom color accuracy matters most |

### Write the designMd

The `designMd` is the most powerful lever. It's freeform markdown that becomes Stitch's creative brief. Structure it as:

```markdown
# Creative Direction
[One paragraph capturing the core feeling, using sensory language not abstract words]

# Color Hierarchy
- **Neutral (canvas):** [description + hex + physical metaphor]
- **Primary (ink):** [description + hex]
- **Secondary (support):** [description + hex]
- **Tertiary (accent):** [description + hex + what it draws attention to]

# Typography
- **Headlines:** [font] — [why this font matches the direction]
- **Body:** [font] — [readability + tone rationale]
- **Labels:** [font] — [role: timestamps, metadata, small UI text]

# Layout Direction
[Physical object metaphor: "If this site were a book, it would be a ___"]
[Layout keywords: lookbook, editorial, card-based, dashboard, bento grid, etc.]

# Imagery
[Photography style: cinematic, documentary, minimalist, illustrated, etc.]
[What to avoid: stock photo cliches, specific anti-patterns]

# Do's and Don'ts
- DO: [specific guidance]
- DON'T: [specific anti-patterns]
```

### Present the full composition to the user for approval before executing.

---

## Phase 5: Execute in Stitch

Call tools in this exact sequence:

1. **`mcp__stitch__create_project`** with a descriptive title
2. **`mcp__stitch__create_design_system`** with all mapped parameters + designMd
3. **`mcp__stitch__update_design_system`** immediately after to apply it
4. **`mcp__stitch__generate_screen_from_text`** with a prompt that includes:
   - What the page IS (functional description)
   - How it should FEEL (from the empathy brief)
   - Layout direction (from the physical object metaphor)
   - Key content sections
   - Use `GEMINI_3_1_PRO` model for best results, `DESKTOP` device type unless specified
5. **After first screen, suggest variants:** Ask the user what to iterate on (layout, imagery, copy, colors) and use `mcp__stitch__generate_variants` with:
   - `creativeRange: EXPLORE` as default (sweet spot)
   - `REFINE` for small tweaks, `REIMAGINE` for radical changes
   - Target specific aspects rather than all at once

### First screen prompt template:
```
[Page description]. The design should feel like [sensory description from Phase 2].
Layout: [physical object metaphor] style — [specific layout keywords].
Typography: large [headline font] headlines over [imagery/content description].
Color: [neutral description] canvas with [primary] text and [tertiary] accents for CTAs.
Content: [key sections the page needs].
```

---

## Quick Path (experienced user with clear direction)

If the user arrives with specific references AND clear requirements, compress Phases 1-3 into a rapid confirmation:

"Based on your references, here's the direction I'd set:
- **Feel:** [one sentence]
- **Archetype:** [name] with elements of [name]
- **Key params:** [font, color mode, roundness]

Want me to proceed, or adjust anything?"

Then go straight to Phase 4-5.
