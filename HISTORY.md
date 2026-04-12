# How This Skill Was Born

## The Spark

It started with a YouTube video: ["One Design Decision to Create Better Results in Stitch"](https://www.youtube.com/watch?v=tnP_Q5mS1I8) by Google for Developers.

The video's presenter built a marathon community site in Stitch and showed how the **same tool** produces dramatically different results depending on one thing: creative direction. His first prompt was vague ("a road running race listing page") and got a generic, directionless design. His second prompt was rich with sensory language, design concepts, and aesthetic references, and got something with soul.

The core insight: **Stitch is a designer, not a creative director.** It needs someone to set the vision. Most people skip that step and wonder why their AI-generated designs look like templates.

## Extracting the Knowledge

We couldn't just watch the video and wing it. We needed the actual methodology. So we:

1. **Pulled the full transcript** using `yt-dlp` (2,336 lines of auto-generated captions)
2. **Extracted every design principle** the presenter used:
   - Start with empathy (who is the user, what should they feel)
   - Avoid abstract words ("make it look good") in favor of sensory language ("architectural limestone, ink on paper")
   - Color is a hierarchy, not a palette (Neutral 80-90%, Primary = ink, Secondary = subdued, Tertiary = accent)
   - Use physical object metaphors for layout ("If my website was a book, what kind?")
   - The `designMd` field is the most powerful lever in Stitch
   - Variants with targeted aspects (layout, images, text) at specific creativity levels (Refine, Explore, Reimagine)
3. **Mapped the Stitch MCP tool schemas** to understand every parameter: 29 fonts, 10 color variants, roundness levels, the full `create_design_system` API
4. **Built a reference library** of 12 design archetypes, each with exact Stitch parameter mappings, example sites, layout keywords, and designMd direction templates

## The Design Decision

The question was: should the skill just be a prompt template, or should it be a full creative direction process?

We went with the process. A template gives you one good output. A process gives you good outputs forever, because it teaches you to think about design the way designers do: empathy first, then aesthetics, then parameters.

The skill follows a 5-phase workflow:

```
1. Empathy Canvas     -> Who is this for? What should they feel?
2. Aesthetic Search   -> Translate feelings into design vocabulary
3. Reference Mapping  -> Match to archetypes, resolve mixed styles
4. Stitch Composition -> Map to exact Stitch params + write designMd
5. Execute            -> Create project -> design system -> screen -> variants
```

## The Style Mixing Problem

A key question came up during design: **what happens when someone references 2-3 different sites?**

"I want Linear's dark mode but warmer, like Notion, with editorial serif headings like NYT."

This could easily produce a mess. Different references pull in different directions. The solution was the **5-Aspect Decomposition**: every design reference contributes to one of 5 aspects (Color/Mood, Typography, Layout, Imagery, Interaction). The skill maps each reference to its dominant aspect, checks for conflicts, and resolves them before handing anything to Stitch.

We also pre-mapped 5 proven combinations (Developer+Editorial, Luxury+Warm, SaaS+Bold, Corporate+Developer, Editorial+Organic) and documented anti-patterns (Brutalist+Luxury, Corporate+Bold) so the skill can warn you before you waste a generation.

The verdict: **mixing styles doesn't complicate the flow. It makes it better.** Because example sites are the most concrete direction you can give. The skill just needs to resolve them into a single coherent direction before calling Stitch.

## Testing It: Three Portfolio Concepts

We tested the skill by redesigning a real portfolio site (udhaykumarbala.dev). The skill generated three completely different concepts from the same brief:

### Concept 1: "The Illustrated Field Guide"
- **Metaphor:** A naturalist's journal for the digital age
- **Design system:** Warm parchment canvas, Literata serif headlines, burnt sienna accents
- Stitch named its enriched system **"The Curated Specimen"** and autonomously added: deckled paper edges, ink-bleed shadows, marginalia components, a "no-line rule" (use tonal shifts instead of borders)

### Concept 2: "The Comic Panel Grid"
- **Metaphor:** A graphic novel for the web
- **Design system:** Void black canvas, Sora bold headlines, electric amber accent, asymmetric bento grid
- Stitch named its enriched system **"The Noir Curator"** and autonomously added: 0px border-radius rule, panel overlap mechanics, hard offset shadows, halftone textures, a "Cell Reveal" hover interaction spec

### Concept 3: "The Creative Workshop"
- **Metaphor:** A craftsperson's studio at midnight
- **Design system:** Warm charcoal canvas, Geist headlines, workshop amber accents
- Stitch named its enriched system **"The Tactile Architect"** and autonomously added: "groove" dividers (3D inset), frosted resin nav bars, warm amber glow interactions, "drawer label" tag components

The key observation: **Stitch enriched every designMd far beyond what we provided.** Our briefs were ~300 words. Stitch expanded them into comprehensive design systems with shadow specs, interaction patterns, component rules, and creative north stars. This only happens when you give Stitch rich creative direction to build from. Vague prompts get vague expansions.

## What We Learned

1. **The designMd field is criminally underused.** Most people set colors and fonts and call it done. The designMd is where the magic happens. It's a freeform creative brief that Stitch uses to drive ALL generation decisions.

2. **Empathy-first design avoids the "generic AI look."** When you start with "who is this for and how should they feel" instead of "what color should the buttons be", the entire design has intent behind it.

3. **Physical metaphors unlock layout.** "If this site were a coffee table book" gives Stitch a lookbook layout. "If this site were a field guide" gives editorial columns with margin annotations. Abstract layout instructions ("make it grid-based") produce generic grids.

4. **Progressive disclosure keeps the skill lean.** The main SKILL.md is 220 lines. The full knowledge base is 640 lines across 4 files. The skill only loads the archetype reference when matching a vibe, the font guide when picking typography, and the mixing guide when the user references multiple styles.

5. **Sensory language is the universal unlock.** Not just for Stitch. For any AI design tool. "Architectural limestone" beats "off-white." "Ink on quality paper" beats "dark text." "Clay-red like an old running track" beats "red accent." The more concrete and physical the language, the more intentional the output.

## Timeline

- Watched the YouTube video, extracted transcript via `yt-dlp`
- Analyzed the Stitch MCP tool schemas (create_project, create_design_system, generate_screen, generate_variants)
- Built the 12-archetype reference library with exact Stitch parameter mappings
- Built the font personality guide (29 fonts categorized)
- Built the style mixing framework (5-aspect decomposition)
- Wrote the 5-phase SKILL.md workflow
- Validated and packaged with the skill-creator toolchain
- Tested on a real portfolio redesign (3 concepts generated and compared)
- Published
