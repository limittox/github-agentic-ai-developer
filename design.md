# Design — The Agentic Developer

A locked design system for this app. Every page redesign reads this file before
emitting code. Do not regenerate per page — extend or amend this file when the
system needs to grow.

## Genre
editorial

## Macrostructure family
- Content pages (all module study guides): **Long Document** — continuous prose,
  inline section heads, single 65ch column, negative space as divider, no scroll
  reveals. Varies only in per-module content and the interactive study apparatus
  (recall / flashcards / quiz), which shares one component voice.

## Theme — Almanac
- `--color-paper`    oklch(96% 0.012 80)
- `--color-paper-2`  oklch(93% 0.014 80)
- `--color-ink`      oklch(20% 0.012 60)
- `--color-muted`    oklch(38% 0.010 70)
- `--color-neutral`  oklch(50% 0.010 75)
- `--color-rule`     oklch(84% 0.012 80)
- `--color-accent`   oklch(55% 0.19 35)   (vermilion)
- `--color-accent-2` oklch(48% 0.17 35)
- `--color-ok`       oklch(48% 0.12 145)  (quiz-correct only)
- `--color-focus`    oklch(52% 0.19 35)

## Typography
- Display: Cabinet Grotesk (Fontshare), weights 700/800, style normal — never italic
- Body:    Source Serif 4 (Google), weight 400 (600 for emphasis)
- Mono:    JetBrains Mono (Google), weight 400 — code blocks and data numerals only
- Display tracking: -0.015em to -0.02em
- Small-caps labels: `font-variant-caps: all-small-caps; letter-spacing: 0.08em`
- Type scale anchor: --text-display = clamp(2.4rem, 4.5vw + 1rem, 4.4rem)
- Reading measure: 65ch

## Spacing
4-point named scale in `tokens.css`. Pages use named tokens (`var(--space-md)`),
never raw values.

## Motion
- Easing: cubic-bezier(0.16, 1, 0.3, 1) named `--ease-out`
- Duration: `--dur-short` 220ms, interactive states only
- Reveal pattern: **none** — Long Document pages are just there
- Reduced-motion fallback: transitions collapse to ≤ 10ms

## Microinteractions stance
- Silent success; no celebratory toasts
- Quiz verdicts appear statically under a rule — no entrance animation beyond opacity
- Hover states: colour + ≤ 4px indent shifts, transform/opacity only

## CTA voice
- Primary: ink hairline border, small-caps label, fills ink on hover (`.btn`)
- Quiet secondary: rule-coloured border, neutral text (`.btn.quiet`)
- Destructive/again: accent border + accent text (`.btn.warn`)
- Links: ink text, vermilion underline, offset 0.2em

## Per-page allowances
- Content pages: typography only. No enrichment, no hero imagery, no re-drawn chrome.

## What pages MUST share
- The masthead: "The Agentic Developer" (N6 newspaper masthead) with module nav
- The Almanac palette; vermilion accent ≤ 3% of any viewport
- Cabinet Grotesk + Source Serif 4 + JetBrains Mono (2+1, no fourth face)
- CTA voice and the exam-paper quiz / index-card flashcard components
- Ft4 dense colophon footer
- Section head rhythm: `h2.inline` with unit number inside the heading text and a
  0.5em vermilion square anchor; `h3.run-in` small-caps with hairline underneath

## What pages MAY differ on
- Module content, contents-line entries, and per-module colophon reading links
- Quiz bank size and refresher mix (interleaving rule: modules ≥ 02 always draw
  2 refreshers from earlier modules)

## Banned on this project (from hallmark gates)
- Italic display/headers anywhere
- Tag-left / heading-right hanging section headers (gate 54)
- Mono eyebrow labels as default section furniture
- Pure #000/#fff; accents as background fills; card-in-card; glassmorphism
- Scroll-triggered entrance reveals

## Exports

Drop-in formats for re-using this design system in other projects.

### tokens.css
```css
:root {
  --color-paper:    oklch(96% 0.012 80);
  --color-paper-2:  oklch(93% 0.014 80);
  --color-rule:     oklch(84% 0.012 80);
  --color-neutral:  oklch(50% 0.010 75);
  --color-muted:    oklch(38% 0.010 70);
  --color-ink:      oklch(20% 0.012 60);
  --color-accent:   oklch(55% 0.19 35);
  --color-accent-2: oklch(48% 0.17 35);
  --color-ok:       oklch(48% 0.12 145);
  --color-focus:    oklch(52% 0.19 35);

  --font-display: "Cabinet Grotesk", ui-sans-serif, sans-serif;
  --font-body:    "Source Serif 4", ui-serif, Georgia, serif;
  --font-mono:    "JetBrains Mono", ui-monospace, monospace;

  --space-3xs: 0.25rem; --space-2xs: 0.5rem; --space-xs: 0.75rem;
  --space-sm: 1rem;  --space-md: 1.5rem;  --space-lg: 2rem;
  --space-xl: 3rem;  --space-2xl: 4.5rem; --space-3xl: 7rem;

  --text-xs: 0.8rem; --text-sm: 0.9rem; --text-base: 1.0625rem;
  --text-md: 1.25rem; --text-lg: 1.5625rem; --text-xl: 1.9531rem;
  --text-2xl: 2.4414rem;
  --text-display: clamp(2.4rem, 4.5vw + 1rem, 4.4rem);

  --ease-out: cubic-bezier(0.16, 1, 0.3, 1);
  --dur-short: 220ms;
  --rule-hair: 1px;
  --radius-card: 0px; --radius-pill: 2px; --radius-input: 2px;
}
```

### Tailwind v4 `@theme`
```css
@theme {
  --color-paper:   oklch(96% 0.012 80);
  --color-ink:     oklch(20% 0.012 60);
  --color-accent:  oklch(55% 0.19 35);
  --font-display:  "Cabinet Grotesk", sans-serif;
  --font-body:     "Source Serif 4", serif;
  --font-mono:     "JetBrains Mono", monospace;
  --spacing-md:    1.5rem;
  --text-md:       1.25rem;
  --ease-out:      cubic-bezier(0.16, 1, 0.3, 1);
}
```

### DTCG `tokens.json`
```json
{
  "color": {
    "paper":  { "$value": "oklch(96% 0.012 80)", "$type": "color" },
    "ink":    { "$value": "oklch(20% 0.012 60)", "$type": "color" },
    "accent": { "$value": "oklch(55% 0.19 35)", "$type": "color" }
  },
  "font": {
    "display": { "$value": "Cabinet Grotesk", "$type": "fontFamily" },
    "body":    { "$value": "Source Serif 4", "$type": "fontFamily" }
  },
  "space": {
    "md": { "$value": "1.5rem", "$type": "dimension" }
  }
}
```

### shadcn/ui CSS variables
```css
:root {
  --background:         96% 0.012 80;
  --foreground:         20% 0.012 60;
  --primary:            55% 0.19 35;
  --primary-foreground: 96% 0.012 80;
  --muted:              93% 0.014 80;
  --muted-foreground:   50% 0.010 75;
  --border:             84% 0.012 80;
  --input:              84% 0.012 80;
  --ring:               52% 0.19 35;
  --radius:             2px;
}
```
