# Stitch Font Guide — Personalities & Pairings

## Font Personalities

### Serif — Authority, Editorial, Tradition
| Font | Personality | Best as |
|------|------------|---------|
| NEWSREADER | Journal, editorial, literary | Headline |
| EB_GARAMOND | Classic, elegant, bookish | Headline |
| LIBRE_CASLON_TEXT | Traditional, stable, law-firm gravitas | Headline |
| DOMINE | Sturdy serif, dependable, slightly modern | Headline |
| LITERATA | Readable, bookish, warm | Headline or Body |
| NOTO_SERIF | Neutral serif, global, accessible | Headline or Body |
| SOURCE_SERIF_FOUR | Warm, readable, content-heavy | Body |

### Geometric Sans — Modern, Clean, Technical
| Font | Personality | Best as |
|------|------------|---------|
| GEIST | Developer-centric, Vercel-adjacent, sharp | Headline + Body |
| INTER | Swiss-knife, ultra-readable, neutral-modern | Any role |
| DM_SANS | Geometric, friendly-modern, slightly playful | Headline + Body |
| SPACE_GROTESK | Monospace-adjacent, technical, distinctive | Label (use sparingly for headlines) |
| IBM_PLEX_SANS | Corporate-technical, systematic, trustworthy | Any role |
| SORA | Geometric, futuristic, clean | Headline |

### Humanist Sans — Warm, Approachable, Friendly
| Font | Personality | Best as |
|------|------------|---------|
| PUBLIC_SANS | Official but approachable, rounder USWDS font | Headline + Body |
| PLUS_JAKARTA_SANS | Modern, warm, SaaS-friendly | Headline + Body |
| NUNITO_SANS | Soft, rounded, very approachable | Headline + Body |
| LEXEND | Designed for readability, inclusive | Body |
| RUBIK | Friendly, slightly geometric, versatile | Headline + Body |
| MANROPE | Clean, semi-geometric, modern | Headline + Body |

### Neutral Sans — Invisible, Workhorse, Universal
| Font | Personality | Best as |
|------|------------|---------|
| SOURCE_SANS_THREE | Adobe's workhorse, professional | Body |
| WORK_SANS | Unobtrusive, gets the job done | Body |
| ARIMO | Metric-compatible with Arial, invisible | Body |
| HANKEN_GROTESK | Clean, slightly refined neutral | Body |
| BE_VIETNAM_PRO | Modern neutral, good for dense UI | Body or Label |
| SPLINE_SANS | Clean, minimal, unfussy | Body |

### Display / Statement — Bold, Distinctive, Branded
| Font | Personality | Best as |
|------|------------|---------|
| EPILOGUE | Geometric, statement-making, modern | Headline only |
| MONTSERRAT | Bold geometric, confident, widely recognized | Headline |
| METROPOLIS | Art-deco adjacent, architectural | Headline |

## Pairing Principles

1. **Contrast roles, not clash.** Pair a serif headline with a sans body, or a geometric headline with a humanist body. Never pair two fonts from the same personality row.

2. **One voice, one font.** Most designs need only 2 fonts. A third (label) is optional and should be reserved for metadata, timestamps, or technical labels.

3. **The label font is a whisper.** SPACE_GROTESK is excellent for labels and timestamps. Keep it out of headlines (it gets noisy at scale).

4. **Match formality.** A casual body font (NUNITO_SANS) fights with a formal headline (LIBRE_CASLON_TEXT). Pair within the same register of formality.

## Quick Decision Tree

```
Need authority/editorial? → Serif headline (NEWSREADER, EB_GARAMOND) + Sans body (INTER)
Need developer/technical? → GEIST everything, or INTER + SPACE_GROTESK labels
Need warm/approachable?   → PUBLIC_SANS or PLUS_JAKARTA_SANS + INTER body
Need bold/creative?       → SORA or DM_SANS headline + INTER body
Need luxury/premium?      → LIBRE_CASLON_TEXT headline + SOURCE_SANS_THREE body
Need corporate/safe?      → IBM_PLEX_SANS everything
Need invisible frame?     → INTER everything
```
