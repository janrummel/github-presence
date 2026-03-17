# ASCII Art Font Catalog

5 kuratierte Fonts für Projekt-Banner auf GitHub READMEs und Landing Pages.
Generiert mit [figlet](https://github.com/cmatsuoka/figlet) + erweiterter Font-Sammlung von [xero/figlet-fonts](https://github.com/xero/figlet-fonts).

## Übersicht

| # | Font | Charakter | Höhe | Beste für |
|---|------|-----------|------|-----------|
| 1 | **ANSI Shadow** | Kräftig, 3D-Schatten, Box-Drawing | 6 Zeilen | Hero-Banner auf Landing Pages |
| 2 | **ANSI Regular** | Kräftig, kompakt, ohne Schatten | 5 Zeilen | README-Header, platzsparend |
| 3 | **Calvin S** | Minimal, Box-Drawing, elegant | 3 Zeilen | Kompakte READMEs, Einzeiler |
| 4 | **Slant** | Kursiv, elegant, Schrägschrift | 5 Zeilen | Frameworks, Methoden-Projekte |
| 5 | **Block-Gradient** | Custom ██▓▓▒▒░░ Verlauf | 5 Zeilen | Maximale Aufmerksamkeit |

## Installation

```bash
# figlet installieren
brew install figlet  # macOS
apt install figlet   # Ubuntu/Debian

# Erweiterte Fonts (ANSI Shadow, Calvin S, etc.) herunterladen
FONT_DIR=$(figlet -I2)
curl -sL "https://raw.githubusercontent.com/xero/figlet-fonts/main/ANSI%20Shadow.flf" -o "$FONT_DIR/ANSI Shadow.flf"
curl -sL "https://raw.githubusercontent.com/xero/figlet-fonts/main/ANSI%20Regular.flf" -o "$FONT_DIR/ANSI Regular.flf"
curl -sL "https://raw.githubusercontent.com/xero/figlet-fonts/main/Calvin%20S.flf" -o "$FONT_DIR/Calvin S.flf"
# slant ist in der Standard-Installation enthalten
```

## Font 1: ANSI Shadow

Der meistgenutzte ASCII-Art-Font auf GitHub. Box-Drawing-Zeichen (╔═╗ ██╗) rendern plattformübergreifend konsistent.

```
figlet -f "ANSI Shadow" "Project"
```

```
██████╗ ██████╗  ██████╗      ██╗███████╗ ██████╗████████╗
██╔══██╗██╔══██╗██╔═══██╗     ██║██╔════╝██╔════╝╚══██╔══╝
██████╔╝██████╔╝██║   ██║     ██║█████╗  ██║        ██║
██╔═══╝ ██╔══██╗██║   ██║██   ██║██╔══╝  ██║        ██║
██║     ██║  ██║╚██████╔╝╚█████╔╝███████╗╚██████╗   ██║
╚═╝     ╚═╝  ╚═╝ ╚═════╝  ╚════╝ ╚══════╝ ╚═════╝   ╚═╝
```

**Tipp:** Für Gradient auf der Website jede Zeile in einen `<span>` mit abgestufter Farbe wrappen:

```html
<pre>
<span style="color:#fbbf24">██████╗ ██████╗  ██████╗ ...</span>
<span style="color:#f59e0b">██╔══██╗██╔══██╗██╔═══██╗...</span>
<span style="color:#d97706">██████╔╝██████╔╝██║   ██║...</span>
<span style="color:#b45309">██╔═══╝ ██╔══██╗██║   ██║...</span>
<span style="color:#92400e">██║     ██║  ██║╚██████╔╝...</span>
<span style="color:#78350f">╚═╝     ╚═╝  ╚═╝ ╚═════╝ ...</span>
</pre>
```

**Amber Gradient Palette (6 Stufen):**
- `#fbbf24` (hell)
- `#f59e0b`
- `#d97706`
- `#b45309`
- `#92400e`
- `#78350f` (dunkel)

**Alternative Paletten:**
- **Blue:** `#93c5fd` → `#3b82f6` → `#2563eb` → `#1d4ed8` → `#1e40af` → `#1e3a8a`
- **Green:** `#86efac` → `#4ade80` → `#22c55e` → `#16a34a` → `#15803d` → `#166534`
- **Purple:** `#c4b5fd` → `#a78bfa` → `#8b5cf6` → `#7c3aed` → `#6d28d9` → `#5b21b6`
- **White Fade:** `#ffffff` → `#e6edf3` → `#c9d1d9` → `#848d97` → `#6e7681` → `#484f58`

## Font 2: ANSI Regular

Wie ANSI Shadow, aber ohne die Shadow-Zeichen — kompakter, gleiche Lesbarkeit.

```
figlet -f "ANSI Regular" "Project"
```

```
██████  ██████   ██████       ██ ███████  ██████ ████████
██   ██ ██   ██ ██    ██      ██ ██      ██         ██
██████  ██████  ██    ██      ██ █████   ██         ██
██      ██   ██ ██    ██ ██   ██ ██      ██         ██
██      ██   ██  ██████   █████  ███████  ██████    ██
```

## Font 3: Calvin S

Minimal und elegant. Nutzt Box-Drawing-Zeichen (┌─┐ ├┤ └─┘). Passt in 3 Zeilen — ideal für kompakte READMEs.

```
figlet -f "Calvin S" "Project Name"
```

```
╔═╗┬─┐┌─┐ ┬┌─┐┌─┐┌┬┐  ╔╗╔┌─┐┌┬┐┌─┐
╠═╝├┬┘│ │ │├┤ │   │   ║║║├─┤│││├┤
╩  ┴└─└─┘└┘└─┘└─┘ ┴   ╝╚╝┴ ┴┴ ┴└─┘
```

## Font 4: Slant

Elegante Schrägschrift. Gut für Frameworks und Methoden-Projekte.

```
figlet -f slant "Project Name"
```

```
    ____               _           __     _   __
   / __ \_________    (_)__  _____/ /_   / | / /___ _____ ___  ___
  / /_/ / ___/ __ \  / / _ \/ ___/ __/  /  |/ / __ `/ __ `__ \/ _ \
 / ____/ /  / /_/ / / /  __/ /__/ /_   / /|  / /_/ / / / / / /  __/
/_/   /_/   \____/_/ /\___/\___/\__/  /_/ |_/\__,_/_/ /_/ /_/\___/
                /___/
```

## Font 5: Block-Gradient (Custom)

Handgemachter Stil mit Unicode-Block-Zeichen (██ ▓▓ ▒▒ ░░) die einen vertikalen Verlauf bilden.
Nicht per figlet generierbar — manuell aus ANSI Regular ableiten und Zeichen ersetzen.

**Technik:** ANSI Regular generieren, dann pro Zeile die Block-Zeichen ersetzen:
- Zeile 1: `██` (volle Blöcke)
- Zeile 2: `██` (volle Blöcke)
- Zeile 3: `▓▓` (dichte Schraffur)
- Zeile 4: `▒▒` (mittlere Schraffur)
- Zeile 5: `░░` (leichte Schraffur)

Kombiniert mit Farb-Gradient für maximalen Effekt auf Dark-Theme Websites.

## Entscheidungshilfe

```
Brauche ich maximale Aufmerksamkeit?
├── Ja → ANSI Shadow + Gradient (Font 1)
└── Nein
    ├── Ist Platz knapp (README)?
    │   ├── Ja → Calvin S (Font 3)
    │   └── Nein → ANSI Regular (Font 2)
    └── Ist es ein Framework/Methoden-Projekt?
        ├── Ja → Slant (Font 4)
        └── Spezialprojekt → Block-Gradient (Font 5)
```

## Hinweise

- **README:** Kein Farb-Gradient möglich (GitHub rendert kein farbiges HTML). Monochrom verwenden.
- **Website:** Gradient über CSS-Spans pro Zeile. Immer in `<pre>` mit Monospace-Font.
- **Breite:** Max 70 Zeichen pro Zeile für Mobile-Kompatibilität. Bei langen Namen aufteilen.
- **Fallback:** Immer einen `<h1>` mit dem Projektnamen als `sr-only` oder `aria-label` für Accessibility.

## Quellen

- [xero/figlet-fonts](https://github.com/xero/figlet-fonts) — 500+ figlet Fonts (ANSI Shadow, Calvin S, etc.)
- [patorjk.com/software/taag](http://patorjk.com/software/taag/) — Online-Generator mit "Test All"
- [oh-my-logo](https://github.com/shinshin86/oh-my-logo) — Claude Code / Gemini CLI Style Gradient-Logos
- [GitHub Copilot CLI ASCII Banner](https://github.blog/engineering/from-pixels-to-characters-the-engineering-behind-github-copilot-clis-animated-ascii-banner/) — Engineering-Referenz
