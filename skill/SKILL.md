---
name: website-review
description: Prueft README + Website eines GitHub-Repos gegen typ-spezifische Checklisten (CLI-Tool, Lernreise, Framework, Checklist, Mini-Tool) und gibt Stufen-Score (Bronze/Silber/Gold/Platin) + fehlende Punkte aus. Use when the user says 'website-review', 'README pruefen', 'Website checken', 'Repo-Qualitaet', 'Gold-Check', 'Stufen-Check', or wants to evaluate a project's public presence.
autonomy_level: on_the_loop
---

# Website Review

Pruefe README + Website eines GitHub-Repos gegen typ-spezifische Checklisten. Gib einen Stufen-Score und fehlende Punkte aus. Diagnostiziere — fixe nichts.

## Phase 0: Voraussetzungen

Pruefe BEVOR du irgendetwas anderes tust:

1. Ist das aktuelle Verzeichnis ein Git-Repo? Pruefe mit `git rev-parse --show-toplevel`.
2. Existiert eine `README.md` (case-insensitive)? Pruefe mit Glob nach `README.md`, `readme.md`, `Readme.md`.

**Wenn eine Bedingung fehlt:** Abbruch mit:
> "Kein Git-Repo oder keine README gefunden. Bitte im Repo-Root ausfuehren."

## Phase 1: Typ- und Stufen-Erkennung

Scanne das Repo um Projekttyp und Ziel-Stufe vorzuschlagen.

### Typ-Erkennung (Heuristik)

Pruefe in dieser Reihenfolge — erster Treffer gewinnt:

| Pruefung | Typ |
|---|---|
| `pyproject.toml`/`setup.py` mit CLI-Entry-Point (`[project.scripts]`, `console_scripts`), oder `bin/` Ordner | **CLI-Tool** |
| `astro.config.*` vorhanden, oder `/content/docs/` Struktur, oder Kapitel-Ordner (`l1/`, `l2/`, `level-`) | **Lernreise** |
| `starter`/`template`/`scaffold` im Repo-Name oder README-Titel, oder "Clone" + "Configure" + "Run" Pattern in README | **Framework** |
| README besteht primaer aus Checklisten (`- [ ]`, `- [x]`), keine Install-Anleitung | **Checklist** |
| Weniger als 5 Source-Dateien (`.py`, `.js`, `.ts`, `.go`, `.rs`), kein Build-System (`package.json`, `pyproject.toml`, `Cargo.toml`, `go.mod`) | **Mini-Tool** |

### Stufen-Erkennung (Heuristik fuer Ziel-Vorschlag)

Diese Heuristik bestimmt NICHT das Ergebnis — nur den Vorschlag.

| Signal | Vorgeschlagene Ziel-Stufe |
|---|---|
| `/docs/` Ordner mit HTML/CSS oder Framework-Config (`astro.config`, etc.) | **Gold** |
| README mit Architecture/Config Sektionen (Grep nach `## Arch`, `## Config`, `## Setup`) | **Silber** |
| README existiert, aber minimal (< 50 Zeilen) | **Bronze** |
| Platin wird nie automatisch vorgeschlagen | — |

### User-Bestaetigung (blockend)

Praesentiere dem User:

> **Erkannt:** [Typ] ([Tech-Stack]). **Ziel-Stufe:** [Stufe]. Korrekt?
>
> Typ korrigieren: 1) CLI-Tool 2) Lernreise 3) Framework 4) Checklist 5) Mini-Tool
> Stufe korrigieren: Bronze / Silber / Gold / Platin

**Warte auf Bestaetigung.** Fahre NICHT fort ohne Antwort.

## Phase 2: Checkliste laden

1. Lese die passende Checklisten-Datei: `~/.claude/skills/website-review/checklists/<typ>.md`
   - cli-tool → `checklists/cli-tool.md`
   - lernreise → `checklists/lernreise.md`
   - framework → `checklists/framework.md`
   - checklist → `checklists/checklist.md`
   - mini-tool → `checklists/mini-tool.md`

2. Filtere Kriterien bis zur Ziel-Stufe (kumulativ):
   - Bronze → nur Bronze-Kriterien
   - Silber → Bronze + Silber
   - Gold → Bronze + Silber + Gold (README + Website)
   - Platin → alle

3. Wenn Ziel-Stufe >= Gold aber kein `/docs/` Ordner existiert:
   > "Fuer Gold wird eine Website in /docs/ benoetigt. Website-Kriterien werden als FAIL gewertet."

## Phase 3: Kriterien pruefen

Gehe jedes Kriterium aus der geladenen Checkliste durch. Pruefung ist **statische Dateianalyse** (Read + Grep), kein Browser-Rendering.

### Verifikations-Referenz

| Kriterium-Typ | Pruefmethode |
|---|---|
| README-Sektionen (FAQ, Architecture, Contributing, ...) | Grep nach Heading-Pattern (`## FAQ`, `## Architecture`, `## Contributing`, ...) in README |
| Problem-Statement | Grep nach erklaerenden Saetzen in den ersten 30 Zeilen der README (nicht nur Titel) |
| Install/Usage/Quick-Start | Grep nach Code-Bloecken mit `pip install`, `npm install`, `cargo install`, `git clone`, oder aehnlichen Patterns |
| Configuration | Grep nach Code-Bloecken mit YAML/TOML/ENV Beispielen oder `## Config` Heading |
| Feature-Grid/Ueberblick | Grep nach Listen (3+ `- ` Items) oder Tabellen unter Feature-relevanten Headings |
| Before/After | Grep nach "before", "after", "vorher", "nachher", "without", "with" |
| Meta/OG-Tags | Grep nach `og:title`, `og:image`, `og:description` in HTML-Dateien unter `/docs/` |
| Mobile Breakpoint | Grep nach `@media` in CSS-Dateien unter `/docs/` |
| Dark Theme | Grep nach `--bg`, `#0d1117`, `#161b22`, Dark-Palette-Tokens in CSS |
| Terminal-Animation | Grep nach `animation`, `@keyframes`, `.term`, `term-` in HTML/CSS |
| Scroll-Animationen | Grep nach `IntersectionObserver`, `animate-in`, `.visible` |
| Interaktive Demo | Grep nach `onclick`, `addEventListener`, `button`, interaktive JS-Patterns |
| Story/Motivation | Grep nach `## Why`, `## Story`, `## Motivation`, `why this exists` in HTML |
| FAQ-Section | Grep nach `<details`, `<summary`, `## FAQ`, `faq` in HTML |
| Architecture-Diagramm | Grep nach `architect`, `diagram`, `svg`, `flow`, `big picture` in HTML |
| Curriculum/Inhaltsverzeichnis | Grep nach `## Curriculum`, `## Table of Contents`, `## Inhalt`, geordnete Listen |
| Progress-Indikatoren | Grep nach `progress`, `step`, `lesson`, Level-Nummern in HTML/CSS |
| Druckbare Version | Grep nach `@media print` in CSS |

Jedes Kriterium ist **binaer: PASS oder FAIL**. Kein PARTIAL.

## Phase 4: Output

### Aktuelle Stufe berechnen

Die hoechste Stufe bei der ALLE Kriterien PASS sind = aktuelle Stufe.
- Nicht alle Bronze-Kriterien PASS → **"Unter Bronze"** (keine Stufe erreicht)
- Alle Bronze-Kriterien PASS → mindestens Bronze
- Alle Bronze + Silber PASS → mindestens Silber
- Alle Bronze + Silber + Gold (README + Website) PASS → Gold
- Ein einziger FAIL in einer Stufe → diese Stufe ist NICHT erreicht

### Output-Template

Use this template verbatim for the output:

## Website Review: <Projektname>

**Typ:** <Typ> | **Erkannt:** automatisch/manuell | **Ziel-Stufe:** <Stufe>

### Status: <Aktuelle Stufe> -- fuer <Ziel-Stufe> fehlen <N> Punkte

#### README (<PASS>/<TOTAL> fuer <Ziel-Stufe>)
- PASS/FAIL <id>: <Beschreibung> [-- <Detail wenn FAIL>]

#### Website (<PASS>/<TOTAL> fuer <Ziel-Stufe>)
- PASS/FAIL <id>: <Beschreibung> [-- <Detail wenn FAIL>]

### Naechste Schritte fuer <Ziel-Stufe> (<N> Punkte)
1. <Gruppierter actionable Schritt>
2. ...

**Regeln:**
- "Naechste Schritte" gruppiert verwandte FAILs zu actionable Items (z.B. FAQ in README + FAQ auf Website = 1 Schritt)
- Die Anzahl der Schritte kann kleiner sein als die Anzahl der FAILs
- Website-Section wird nur angezeigt wenn Ziel-Stufe >= Gold
- Bei Bronze/Silber: "Website: Nicht erforderlich fuer diese Stufe"
- Wenn alle Kriterien PASS: "Alle Kriterien fuer <Stufe> erfuellt!"
- Wenn nicht alle Bronze-Kriterien PASS: Status zeigt "Unter Bronze"

## Wissensbasis

Diese Dateien sind Hintergrundwissen — nicht zum automatischen Einlesen bei jedem Lauf, aber als Referenz wenn Kriterien unklar sind:

- **Playbook:** `../playbook.md` (im gleichen Repo)
