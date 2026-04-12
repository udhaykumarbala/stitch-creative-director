# Design Archetypes — Stitch Parameter Mappings

Each archetype maps a design feeling to concrete Stitch `create_design_system` parameters.

## Table of Contents
- [Editorial / Magazine](#editorial--magazine)
- [Developer / Technical](#developer--technical)
- [Warm Minimalism](#warm-minimalism)
- [Bold / Expressive](#bold--expressive)
- [Luxury / Premium](#luxury--premium)
- [Friendly / SaaS](#friendly--saas)
- [Brutalist / Raw](#brutalist--raw)
- [Corporate / Enterprise](#corporate--enterprise)
- [Organic / Craft](#organic--craft)
- [Retro / Nostalgic](#retro--nostalgic)
- [Dashboard / Data](#dashboard--data)
- [Portfolio / Creative](#portfolio--creative)

---

## Editorial / Magazine
**Feel:** Authoritative, premium, story-driven, curated
**Reference sites:** NYT, Bloomberg, Monocle, The Verge, Aeon
**Best for:** Blogs, content platforms, media, thought leadership

| Param | Value |
|-------|-------|
| colorMode | LIGHT |
| headlineFont | NEWSREADER or EB_GARAMOND or LITERATA |
| bodyFont | INTER or SOURCE_SANS_THREE |
| labelFont | SPACE_GROTESK |
| roundness | ROUND_FOUR |
| colorVariant | NEUTRAL or MONOCHROME |
| customColor | `#1a1a1a` (deep ink) |
| neutralOverride | `#faf8f5` (warm paper) |

**Layout keywords:** editorial lookbook, large typography over images, full-bleed hero, magazine spread, generous whitespace, serif headlines at scale
**designMd direction:** "Ink on quality paper. Think of a curated journal or long-form magazine. Headlines command attention. Photography is cinematic, not decorative."

---

## Developer / Technical
**Feel:** Precise, capable, fast, no-nonsense, trustworthy
**Reference sites:** Linear, Vercel, Raycast, Supabase, Railway
**Best for:** Dev tools, APIs, CLIs, technical portfolios, documentation

| Param | Value |
|-------|-------|
| colorMode | DARK |
| headlineFont | GEIST or INTER |
| bodyFont | GEIST or INTER |
| labelFont | SPACE_GROTESK or IBM_PLEX_SANS |
| roundness | ROUND_FOUR or ROUND_EIGHT |
| colorVariant | MONOCHROME or NEUTRAL |
| customColor | `#6366f1` (indigo) or `#10b981` (emerald) |
| neutralOverride | `#0a0a0a` (near-black) |

**Layout keywords:** clean grid, functional density, monospace accents, code-aware sections, subtle borders, card-based with low elevation
**designMd direction:** "A well-built CLI in visual form. Every element earns its place. Monospace for metadata, clean sans for content. Dark canvas, purposeful color only for interactive elements."

---

## Warm Minimalism
**Feel:** Human, calm, trustworthy, approachable, considered
**Reference sites:** Notion, Basecamp, Stripe Docs, Bear, iA Writer
**Best for:** Productivity apps, personal sites, writing tools, landing pages

| Param | Value |
|-------|-------|
| colorMode | LIGHT |
| headlineFont | PUBLIC_SANS or INTER |
| bodyFont | INTER or PUBLIC_SANS |
| labelFont | SPACE_GROTESK or INTER |
| roundness | ROUND_EIGHT |
| colorVariant | NEUTRAL |
| customColor | `#d97706` (warm amber) |
| neutralOverride | `#fffbf5` (warm cream) |

**Layout keywords:** generous whitespace, content-first, warm background tones, subtle shadows, friendly but structured
**designMd direction:** "Architectural limestone and warm ink. The feel of a well-organized notebook. Not cold, not playful. Considered warmth that lets content breathe."

---

## Bold / Expressive
**Feel:** Energetic, creative, confident, attention-grabbing, playful
**Reference sites:** Figma, Framer, Arc Browser, Pitch, Loom
**Best for:** Creative tools, portfolio showcases, product launches, communities

| Param | Value |
|-------|-------|
| colorMode | LIGHT or DARK |
| headlineFont | SORA or DM_SANS or MANROPE |
| bodyFont | DM_SANS or INTER |
| labelFont | SPACE_GROTESK |
| roundness | ROUND_TWELVE |
| colorVariant | VIBRANT or EXPRESSIVE |
| customColor | `#8b5cf6` (violet) or `#f43f5e` (rose) |

**Layout keywords:** bold gradients, oversized typography, dynamic asymmetric layouts, vibrant CTAs, layered depth, illustration-friendly
**designMd direction:** "A stage for the product. Bold type demands attention, gradient backgrounds create depth. Nothing subtle. Color is the personality."

---

## Luxury / Premium
**Feel:** Exclusive, refined, aspirational, quiet confidence, timeless
**Reference sites:** Apple, Aesop, Rapha, Hodinkee, Rimowa
**Best for:** High-end products, fashion, premium services, exclusive memberships

| Param | Value |
|-------|-------|
| colorMode | LIGHT or DARK |
| headlineFont | LIBRE_CASLON_TEXT or EB_GARAMOND or DOMINE |
| bodyFont | INTER or SOURCE_SANS_THREE |
| labelFont | SPACE_GROTESK or MANROPE |
| roundness | ROUND_FOUR |
| colorVariant | MONOCHROME or NEUTRAL |
| customColor | `#1c1917` (rich black) or `#78716c` (stone) |
| neutralOverride | `#fafaf9` (stone white) |

**Layout keywords:** cinematic hero imagery, restrained palette, massive whitespace, serif at display scale, editorial-level photography, minimal UI chrome
**designMd direction:** "Quiet luxury. Let the product speak. Generous space conveys value. Serif headlines whisper authority. Photography is everything. Color is an event, not decoration."

---

## Friendly / SaaS
**Feel:** Approachable, modern, trustworthy, energetic but professional
**Reference sites:** Slack, Twilio, Intercom, Canva, Calendly
**Best for:** B2B SaaS, collaboration tools, marketplaces, onboarding flows

| Param | Value |
|-------|-------|
| colorMode | LIGHT |
| headlineFont | PLUS_JAKARTA_SANS or NUNITO_SANS |
| bodyFont | INTER or PLUS_JAKARTA_SANS |
| labelFont | INTER |
| roundness | ROUND_TWELVE or ROUND_FULL |
| colorVariant | TONAL_SPOT or VIBRANT |
| customColor | `#3b82f6` (blue) or `#8b5cf6` (purple) |

**Layout keywords:** card-based, illustration-friendly, vibrant CTAs, rounded elements, clear hierarchy, feature grids, social proof sections
**designMd direction:** "A friendly handshake. Rounded shapes signal approachability. Primary color is confident but not loud. Illustrations over photography. Everything should feel one click away."

---

## Brutalist / Raw
**Feel:** Authentic, unconventional, statement-making, raw, unapologetic
**Reference sites:** Cargo, many indie portfolios, Bloomberg Businessweek digital features
**Best for:** Art portfolios, experimental projects, personal statements, creative agencies

| Param | Value |
|-------|-------|
| colorMode | LIGHT or DARK |
| headlineFont | SPACE_GROTESK or IBM_PLEX_SANS |
| bodyFont | IBM_PLEX_SANS or INTER |
| labelFont | SPACE_GROTESK |
| roundness | ROUND_FOUR |
| colorVariant | MONOCHROME |
| customColor | `#000000` (black) or `#ef4444` (red) |

**Layout keywords:** raw grid, exposed structure, monospace accents, high contrast, visible borders, no-frills hierarchy, bold type at extreme scale
**designMd direction:** "The wireframe IS the design. Exposed grids, raw typography, no decorative flourish. Every element is structural. Color is either absent or screaming."

---

## Corporate / Enterprise
**Feel:** Professional, stable, scalable, credible, systematic
**Reference sites:** Salesforce, IBM, Microsoft, Atlassian, Datadog
**Best for:** Enterprise products, B2B platforms, admin dashboards, documentation

| Param | Value |
|-------|-------|
| colorMode | LIGHT |
| headlineFont | IBM_PLEX_SANS or SOURCE_SANS_THREE |
| bodyFont | IBM_PLEX_SANS or INTER |
| labelFont | IBM_PLEX_SANS |
| roundness | ROUND_EIGHT |
| colorVariant | NEUTRAL or TONAL_SPOT |
| customColor | `#2563eb` (corporate blue) |

**Layout keywords:** structured grid, data-dense, consistent hierarchy, system-level components, table-friendly, navigation-heavy
**designMd direction:** "Built for scale. Systematic color usage. Clear information hierarchy. Everything follows a grid. Accessibility is non-negotiable. Density serves productivity."

---

## Organic / Craft
**Feel:** Earthy, handmade, sustainable, warm, textured
**Reference sites:** Patagonia, Allbirds, Blue Bottle Coffee, many D2C brands
**Best for:** D2C brands, food/beverage, sustainability, wellness, outdoor

| Param | Value |
|-------|-------|
| colorMode | LIGHT |
| headlineFont | DOMINE or LITERATA |
| bodyFont | SOURCE_SERIF_FOUR or INTER |
| labelFont | MANROPE |
| roundness | ROUND_EIGHT |
| colorVariant | NEUTRAL or FIDELITY |
| customColor | `#854d0e` (earth brown) or `#166534` (forest green) |
| neutralOverride | `#fef3c7` (warm sand) |

**Layout keywords:** organic imagery, full-bleed photography, earthy tones, textured backgrounds, hand-drawn accents, story-driven sections
**designMd direction:** "Sun-warmed clay and linen. Colors from nature, not a color picker. Serif headlines feel handset. Photography is real, unpolished, human. Whitespace like open sky."

---

## Retro / Nostalgic
**Feel:** Vintage, playful, nostalgic, distinctive, personality-driven
**Reference sites:** Poolside FM, many indie games, some crypto projects
**Best for:** Entertainment, games, community platforms, personal brands

| Param | Value |
|-------|-------|
| colorMode | LIGHT or DARK |
| headlineFont | SPACE_GROTESK or EPILOGUE |
| bodyFont | BE_VIETNAM_PRO or SPLINE_SANS |
| labelFont | SPACE_GROTESK |
| roundness | ROUND_FOUR or ROUND_FULL |
| colorVariant | EXPRESSIVE or RAINBOW |
| customColor | `#f59e0b` (amber) or `#ec4899` (pink) |

**Layout keywords:** retro grid, pixel-adjacent, neon accents, playful layout breaks, bold color blocking, chunky borders
**designMd direction:** "A time machine to your favorite decade. Bold color blocking, chunky UI elements, personality over polish. The interface itself is the entertainment."

---

## Dashboard / Data
**Feel:** Clear, efficient, informative, scannable, professional
**Reference sites:** Grafana, Datadog, Vercel Analytics, Plausible, PostHog
**Best for:** Analytics, monitoring, admin panels, financial dashboards

| Param | Value |
|-------|-------|
| colorMode | DARK |
| headlineFont | INTER or GEIST |
| bodyFont | INTER or GEIST |
| labelFont | SPACE_GROTESK or GEIST |
| roundness | ROUND_EIGHT |
| colorVariant | NEUTRAL or MONOCHROME |
| customColor | `#6366f1` (indigo) |
| neutralOverride | `#111827` (slate-900) |

**Layout keywords:** dense grid, chart-friendly, metric cards, sidebar navigation, data tables, small type at scale, status indicators
**designMd direction:** "Information density without chaos. Dark canvas reduces eye strain. Color means something (status, change, category). Monospace for numbers. Every pixel serves comprehension."

---

## Portfolio / Creative
**Feel:** Personal, distinctive, curated, memorable, authentic
**Reference sites:** Many award-winning portfolios on Awwwards, Behance featured
**Best for:** Designer portfolios, creative agencies, freelancer sites, personal brands

| Param | Value |
|-------|-------|
| colorMode | DARK or LIGHT |
| headlineFont | EPILOGUE or MANROPE or SORA |
| bodyFont | INTER or DM_SANS |
| labelFont | SPACE_GROTESK |
| roundness | ROUND_FOUR or ROUND_EIGHT |
| colorVariant | NEUTRAL or MONOCHROME |
| customColor | varies by personality |

**Layout keywords:** project showcase grid, large hero with name/title, case-study layout, image-heavy, scroll-driven narrative, bento grid
**designMd direction:** "The portfolio IS the work. Let projects dominate. The frame should be invisible or iconic. Navigation is minimal. Every scroll reveals a new piece. Typography carries the personal voice."
