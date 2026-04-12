# Mixing Design Styles — Resolution Framework

When users reference 2-3 sites or aesthetics, resolve them into one coherent direction BEFORE calling Stitch.

## The 5-Aspect Decomposition

Every design reference contributes to one or more of these aspects. Identify which aspect each reference provides:

| Aspect | What it controls | Example |
|--------|-----------------|---------|
| **Color/Mood** | Palette, light/dark, warmth, energy | "The dark elegance of Linear" |
| **Typography** | Font personality, scale, weight | "The editorial headlines of NYT" |
| **Layout** | Grid, spacing, density, structure | "The card-based layout of Notion" |
| **Imagery** | Photo style, illustration, icons | "The cinematic photography of Apple" |
| **Interaction** | Roundness, animation feel, UI density | "The friendly rounded buttons of Slack" |

## Resolution Process

### Step 1: Map each reference to its dominant aspect

Example: "I want Linear's dark mode + Stripe's layout clarity + NYT's editorial headings"
- Linear → Color/Mood (dark, monochrome, purposeful accent)
- Stripe → Layout (clean grid, generous whitespace, clear hierarchy)
- NYT → Typography (serif headlines at scale, editorial feel)

### Step 2: Check for conflicts

Conflicts happen when two references claim the same aspect with different directions:

| Conflict | Resolution strategy |
|----------|-------------------|
| Both claim Color/Mood | Ask: "Which site's color feel should dominate?" |
| Both claim Typography | Take headline from one, body from the other |
| Both claim Layout | Ask: "Which site's content structure matches yours?" |
| Formality mismatch | Lean toward the one that matches the audience |
| Light vs Dark | One wins; mix via "dark with warm undertones" |

### Step 3: Synthesize the designMd

Write a single coherent paragraph that names the specific contribution of each reference:

**Bad:** "A mix of Linear and Notion"
**Good:** "Dark canvas like a developer tool at midnight (Linear's purposeful darkness), but with warm undertones in the neutral palette (Notion's approachable warmth). Editorial serif headlines create authority (NYT's typographic confidence), while the body stays in a clean geometric sans. Layout is content-first with generous whitespace (Stripe's clarity). Rounded corners at medium radius bridge the technical and friendly."

## Common Successful Mixes

### Developer + Editorial (portfolio, devrel, technical blog)
- **Take from Developer:** Dark mode, monospace labels, technical credibility
- **Take from Editorial:** Serif headlines, large typography, content-first layout
- **Stitch params:** DARK, headlineFont: NEWSREADER, bodyFont: GEIST, labelFont: SPACE_GROTESK, ROUND_FOUR, MONOCHROME
- **Reference sites:** Think Increment magazine, or Stripe's engineering blog

### Luxury + Warm (premium but approachable brand)
- **Take from Luxury:** Restraint, serif headlines, cinematic imagery, massive whitespace
- **Take from Warm:** Cream/warm backgrounds, rounded corners, friendly body font
- **Stitch params:** LIGHT, headlineFont: LIBRE_CASLON_TEXT, bodyFont: PUBLIC_SANS, ROUND_EIGHT, NEUTRAL, neutralOverride: warm cream
- **Reference sites:** Think Aesop meets Basecamp

### SaaS + Bold (energetic product launch)
- **Take from SaaS:** Card-based layout, clear CTAs, feature grids
- **Take from Bold:** Vibrant gradients, oversized headlines, dynamic asymmetry
- **Stitch params:** LIGHT, headlineFont: SORA, bodyFont: DM_SANS, ROUND_TWELVE, VIBRANT
- **Reference sites:** Think Figma meets Intercom

### Corporate + Developer (enterprise dev platform)
- **Take from Corporate:** Structured grid, professional tone, trustworthy
- **Take from Developer:** Dark option, code-aware, technical density
- **Stitch params:** DARK, headlineFont: IBM_PLEX_SANS, bodyFont: INTER, ROUND_EIGHT, NEUTRAL
- **Reference sites:** Think Datadog meets GitHub

### Editorial + Organic (artisanal content platform)
- **Take from Editorial:** Large typography, lookbook layout, story-driven
- **Take from Organic:** Earth tones, natural imagery, serif body
- **Stitch params:** LIGHT, headlineFont: DOMINE, bodyFont: SOURCE_SERIF_FOUR, ROUND_EIGHT, FIDELITY, warm earth custom color
- **Reference sites:** Think Kinfolk magazine

## Anti-Patterns (mixes that fight)

- **Brutalist + Luxury:** Brutalism's rawness kills luxury's refinement. Pick one.
- **Corporate + Bold:** Corporate needs restraint; bold needs freedom. One will dominate and the other will just look inconsistent.
- **Retro + Developer:** Unless intentionally ironic (which Stitch can't convey through static design), these aesthetics contradict.

When the user suggests a conflicting mix, say: "These aesthetics pull in opposite directions. Which feeling matters more for your audience? I can lean one way and borrow a small element from the other."
