# MUEGGE Group Workshop-Präsentation

## Projekt-Überblick
Greyt GmbH erstellt eine professionelle HTML-Präsentation für einen Workshop mit dem Kunden **MUEGGE Group**. Thema: Website-Analyse & Optimierungskonzept. Die Präsentation wird von Johannes Lorenz (Greyt) gehalten.

## Ziel
Single-File HTML-Prasentation (14 Slides), die auf dem Design-Level der PROCME-Referenz (https://procme.greyt-webseiten.com/) liegt. Kein Framework — vanilla HTML/CSS/JS, alles inline.

## Wichtige Dateien

| Datei | Beschreibung |
|-------|-------------|
| `muegge-workshop.html` | **Die Präsentation** — Single HTML file mit allem inline |
| `input/2026_03_16 Greyt Vorlage.pdf` | Greyt PowerPoint-Vorlage (PDF) — initialer Style-Referenz |
| `input/MUEGGE_Website_Analyse_Greyt.docx` | Vollständige Website-Analyse — inhaltliche Quelle für alle Slides |
| `architecture/PROGRESS.md` | Fortschritt, erledigte Tasks, offene Punkte |
| `architecture/STYLEGUIDE.md` | Design-Entscheidungen, Farben, Typografie, Patterns |
| `architecture/SLIDES.md` | Slide-für-Slide Dokumentation mit Inhalten und Layout |

## Ordnerstruktur

| Ordner | Inhalt |
|--------|--------|
| `architecture/` | Projekt-Dokumentation (Progress, Styleguide, Slides-Doku) |
| `input/` | Quelldokumente (Greyt-Vorlage, MUEGGE-Analyse DOCX) |
| `ref-screenshots/` | PROCME-Referenz Design-Screenshots |
| `screenshots/v1..v5/` | Entwicklungs-Screenshots nach Version |
| `muegge-website/` | MUEGGE-Website Screenshots (Bilder-Recherche) |
| `.playwright-mcp/` | Playwright MCP temporäre Dateien |

## Design-Referenz
Die Präsentation orientiert sich am Design von **https://procme.greyt-webseiten.com/** (Greyt's eigene Sales-Präsentation für PROCME). Screenshots der Referenz liegen in `ref-screenshots/`.

## Technische Eckdaten
- **Font:** Inter (Google Fonts) + system-ui Fallback
- **Farbe:** MUEGGE Dark Navy (#0A1523) + Cyan (#00D4FF) — seit v4 auf MUEGGE Corporate Design umgestellt
- **16:9** optimiert für Beamer (1280x720 / 1920x1080)
- **Navigation:** Pfeiltasten, Nav-Arrow-Buttons, Touch, Klick auf Cover zum Starten
- **Footer-Bar:** Slide-Counter + Progress-Bar + "Pfeiltasten zur Navigation" + "greyt." Logo
- **Print:** Alle Slides untereinander via `@media print`

## Deployment
- **GitHub:** https://github.com/philipp-ekstrand/praesentation-muegge (public)
- **Vercel:** https://slidesmuegge.vercel.app/muegge-workshop.html (Free Tier, Auto-Deploy)
- Push auf `main` triggert automatischen Vercel-Build

## Verifikation
Immer nach Anderungen mit Playwright via `http://127.0.0.1:8791/muegge-workshop.html` (python3 HTTP server) verifizieren. Screenshots machen und vergleichen. Nach Deploy auch die Vercel-URL prufen.

## Regeln
- Niemals `git push` ohne explizite Anweisung
- Alle Inhalte basieren auf dem DOCX-Analysedokument — nichts erfinden
- Nach Änderungen: Playwright-Screenshot zur Verifikation
