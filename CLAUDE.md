# MUEGGE Group Workshop-Präsentation

## Projekt-Überblick
Greyt GmbH erstellt eine professionelle HTML-Präsentation für einen Workshop mit dem Kunden **MUEGGE Group**. Thema: Website-Analyse & Optimierungskonzept. Die Präsentation wird von Johannes Lorenz (Greyt) gehalten.

## Ziel
Single-File HTML-Präsentation (13 Slides), die auf dem Design-Level der PROCME-Referenz (https://procme.greyt-webseiten.com/) liegt. Kein Framework — vanilla HTML/CSS/JS, alles inline.

## Wichtige Dateien

| Datei | Beschreibung |
|-------|-------------|
| `muegge-workshop.html` | **Die Präsentation** — Single HTML file mit allem inline |
| `input/2026_03_16 Greyt Vorlage.pdf` | Greyt PowerPoint-Vorlage (PDF) — initialer Style-Referenz |
| `input/MUEGGE_Website_Analyse_Greyt.docx` | Vollständige Website-Analyse — inhaltliche Quelle für alle Slides |
| `PROGRESS.md` | Fortschritt, erledigte Tasks, offene Punkte |
| `STYLEGUIDE.md` | Design-Entscheidungen, Farben, Typografie, Patterns |
| `SLIDES.md` | Slide-für-Slide Dokumentation mit Inhalten und Layout |

## Design-Referenz
Die Präsentation orientiert sich am Design von **https://procme.greyt-webseiten.com/** (Greyt's eigene Sales-Präsentation für PROCME). Screenshots der Referenz liegen als `ref-slide*.png` im Projektordner.

## Technische Eckdaten
- **Font:** Inter (Google Fonts) + system-ui Fallback
- **Farbe:** Greyt-Purple (#5B21B6 / #7C3AED) — NICHT Blue wie in der PROCME-Referenz
- **16:9** optimiert für Beamer (1280x720 / 1920x1080)
- **Navigation:** Pfeiltasten, Nav-Arrow-Buttons, Touch, Klick auf Cover zum Starten
- **Footer-Bar:** Slide-Counter + Progress-Bar + "Pfeiltasten zur Navigation" + "greyt." Logo
- **Print:** Alle Slides untereinander via `@media print`

## Verifikation
Immer nach Änderungen mit Playwright via `http://127.0.0.1:8791/muegge-workshop.html` (python3 HTTP server) verifizieren. Screenshots machen und vergleichen.

## Regeln
- Niemals `git push` ohne explizite Anweisung
- Alle Inhalte basieren auf dem DOCX-Analysedokument — nichts erfinden
- Nach Änderungen: Playwright-Screenshot zur Verifikation
