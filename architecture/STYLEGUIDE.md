# Style Guide — MUEGGE Workshop-Präsentation

## Design-Referenz
Basiert auf https://procme.greyt-webseiten.com/ (Greyt PROCME Sales-Prasentation).
Adaptiert mit Purple statt Blue. Zusatzliche Patterns aus greyt-starter (Animationen,
fluid Typography) und Catalpa (Glass Morphism, farbige Shadows, Micro-Interactions).

## Farbpalette

| Variable | Wert | Verwendung |
|----------|------|------------|
| `--primary` | `#5B21B6` | Haupt-Akzent, Badges filled, Progress Bar, Step-Circles |
| `--primary-light` | `#7C3AED` | Akzent-Text in Headlines (`.accent`), Badge-Border |
| `--primary-lighter` | `#8B5CF6` | Card-Nummern (leichter), Timeline-Bars |
| `--primary-dim` | `rgba(91,33,182,0.08)` | Icon-Circle Hintergrund |
| `--primary-bg` | `#F5F3FF` | Fazit-Box Hintergrund |
| `--cover-gradient` | `#1E0A4A → #3B1289 → #5B21B6 → #7C3AED` | Cover-Slide Fullscreen |
| `--text` | `#1A1A2E` | Haupttext |
| `--text-sub` | `#6C757D` | Subtitles, Beschreibungen |
| `--text-muted` | `#ADB5BD` | Hints, Timestamps, Footer-Hint |
| `--bg-card` | `#F8F9FA` | Card-Hintergrund |
| `--border-card` | `#E9ECEF` | Card-Border |
| `--success` | `#10B981` | Checkmarks, "Was sich ändert" |
| `--danger` | `#EF4444` | X-Marks, "Was sich NICHT ändert" |
| `--warning` | `#F59E0B` | Teilweise-Indikatoren |

## Typografie

| Element | Size | Weight | Farbe | Alignment |
|---------|------|--------|-------|-----------|
| Cover Headline | 42-72px | 900 | White | Center |
| Cover Tagline | 11-14px | 600 | White 55% | Center, uppercase, letter-spacing 0.2em |
| Slide Headline (`.s-headline`) | 32-52px | 900 | `--text` | **Center** |
| Accent-Wörter (`.accent`) | inherit | inherit | `--primary-light` | — |
| Subtitle (`.s-subtitle`) | 14-18px | 400 | `--text-sub` | Center, max-width 700px |
| Badge (`.s-badge`) | 11-13px | 600 | `--primary` | Center, pill-shape |
| Body/Bullets | 13-15px | 400 | `--text` | Left |
| Metric Values | 28-44px | 800 | `--primary` | Center |
| Card Titles | 14-17px | 700 | `--primary` | Center |
| Card Descriptions | 11-13px | 400 | `--text-sub` | Center |

## Layout-Patterns

### Slide-Struktur (jede Content-Slide)
```
┌────────────────────────────────────────────────┐
│                                                │
│              [ Badge/Pill ]                    │
│         Große zentrierte Headline              │
│           Subtitle in grau                     │
│                                                │
│    ┌──────┐  ┌──────┐  ┌──────┐               │
│    │ Card │  │ Card │  │ Card │               │
│    └──────┘  └──────┘  └──────┘               │
│                                                │
│ < ─────────────────────────────────────────  > │
│                                                │
├────────────────────────────────────────────────┤
│ 3/13  3/13 ████░░░░  Pfeiltasten...   greyt.  │
└────────────────────────────────────────────────┘
```

### Cover-Slide
- Full-bleed `--cover-gradient`
- Tagline uppercase oben
- Riesige Headline weiß uppercase
- Logo-Pills: "MUEGGE Group" × "greyt."
- "Klicken zum Starten" unten mitte
- "g" Icon unten rechts
- KEINE Footer-Bar, KEINE Nav-Arrows

### Footer-Bar (fixed, auf allen Slides außer Cover)
- Height: 52px
- Links: Slide-Nummer "X / 13"
- Daneben: "X / 13" + Progress Track (purple fill)
- Rechts: "Pfeiltasten zur Navigation" + "greyt." Wordmark

### Nav-Arrows
- Kreise, 40x40px, links/rechts am Viewport-Rand
- Vertikal zentriert (top: 50%)
- Disabled-State: opacity 0.25
- Ausgeblendet auf Cover-Slide

### Card-Typen
1. **Metric Card** (`metric-card`): Große Zahl + Label, zentriert
2. **Clean Card** (`card-clean`): Icon-Circle + Title + Desc, zentriert
3. **Numbered Card** (`ncard`): Große leichte Nummer + Title + Desc
4. **Detail Column** (`dcol`): Nummer + Title + Bullet-Liste
5. **Question Block** (`q-block`): Nummer + Frage-Text, left-border purple

6. **Formula Chip** (`formula-chip`): Pill-Shape mit Icon + Text, Outline oder Filled
7. **Assessment Panel** (`panel--green/amber/red`): Farbcodierte Bewertungs-Cards
8. **Contact Card** (`contact-card`): Zentrierte Kontaktinfo mit Brand + Divider

### Alle Cards
- Background: `#FFFFFF` oder `#F8F9FA`
- Border: `1px solid #E9ECEF`
- Border-radius: `16px`
- Farbige Shadows: `box-shadow: 0 4px 16px rgba(91,33,182,0.06)`
- Hover-Lift: `translateY(-2px)` + verstarkte Shadow

### Icons
- Inline SVGs (stroke-based, 24x24 viewBox)
- In `card-icon-circle` Container: 52x52px, border-radius 14px, background `--primary-dim`
- Stroke: `--primary`, fill: none, stroke-width: 2

## Animationen (v3)

### Entrance-Animationen
- `data-anim` Attribut auf Content-Elementen
- `slide-fade-up`: opacity 0 + translateY(24px) → normal (0.6s ease)
- `slide-fade-scale`: opacity 0 + translateY(12px) + scale(0.97) → normal
- Stagger via `--d` CSS Variable (z.B. `style="--d:0.2s"`)
- Reset bei Slide-Wechsel (JS `resetAnims()`)
- `prefers-reduced-motion` wird respektiert

### Glass Morphism (nur Vision 2)
- `backdrop-filter: blur(12px)` + rgba Background
- Nur auf `.mod-grid .card-clean` Elementen

### Cover-Textur
- Dot-Grid Pattern via CSS `radial-gradient` Pseudo-Element

## CSS Custom Properties
Alle Design-Tokens sind als CSS Custom Properties in `:root` definiert. Bei Anderungen dort zentral anpassen.

## Deployment
- GitHub: https://github.com/philipp-ekstrand/praesentation-muegge
- Vercel: https://slidesmuegge.vercel.app/muegge-workshop.html
- Auto-Deploy bei Push auf `main`
