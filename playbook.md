# Website Design Playbook — GitHub Pages Landing Pages

Wiederverwendbare Erkenntnisse und Schritt-fuer-Schritt-Vorgehen fuer Projekt-Websites. Basierend auf Learnings aus mehreren Projekten, anwendbar auf alle Projekte mit Landing Pages.

## 1. Seitenstruktur (bewaeht)

```
Hero (Icon + Name + Tagline + Badges)
  ↓
Problem-Statement (WARUM existiert das Projekt?)
  ↓
Install-Box (3 Zeilen: install, setup, run)
  ↓
CTA-Button (View on GitHub)
  ↓
Interaktive Demo (Tabs mit Terminal-Mockups)
  ↓
Feature-Grid (6 Karten, 2x3)
  ↓
Architecture (ASCII-Diagramm)
  ↓
Design Principles (3 Karten)
  ↓
Footer (Links + Tagline)
```

**Wichtig:** Problem-Statement VOR der Loesung. Nicht mit Features anfangen, sondern mit dem Schmerz den das Tool loest.

## 2. Terminal-Mockups in HTML

### Was funktioniert
- `white-space: pre` ist PFLICHT fuer monospace-Content
- HTML-Entities statt Unicode-Sonderzeichen (browser-sicher)
- Farbige `<span>` Tags fuer Syntax-Highlighting
- macOS Terminal-Bar (3 Dots: rot/gelb/gruen) fuer Wiedererkennungswert

### Kritische Fallstricke
| Problem | Ursache | Loesung |
|---|---|---|
| Text fliesst zusammen | `white-space: pre` fehlt | Immer explizit setzen, auch bei `.arch` Klassen |
| Box-Zeichen verschoben | `<span>` Tags verschieben Zeichenpositionen | Sichtbare Zeichen zaehlen, nicht HTML-Zeichen |
| Zu breit fuer Container | ASCII-Art zu breit | `overflow-x: auto` + Diagramm schmaler halten |
| Vertikale Striche ungleich | Unterschiedliche Textlaengen | Alle Zeilen auf gleiche Spaltenposition padden |

### Template fuer Terminal-Mockup
```html
<div class="term">
    <div class="term-bar">
        <div class="term-dot r"></div>
        <div class="term-dot y"></div>
        <div class="term-dot g"></div>
        <span class="term-title">command</span>
    </div>
    <div class="term-body">Content hier (white-space: pre!)</div>
</div>
```

### CSS Minimum
```css
.term { background: #161b22; border: 1px solid #30363d; border-radius: 12px; overflow: hidden; }
.term-bar { background: #21262d; padding: 10px 16px; display: flex; gap: 8px; align-items: center; }
.term-dot { width: 12px; height: 12px; border-radius: 50%; }
.term-dot.r { background: #ff5f57; }
.term-dot.y { background: #febc2e; }
.term-dot.g { background: #28c840; }
.term-body {
    padding: 24px;
    font-family: 'SF Mono', 'Fira Code', monospace;
    font-size: 13px;
    line-height: 1.7;
    white-space: pre;
    overflow-x: auto;
}
```

## 3. Apple HIG Prinzipien fuer Websites

| Prinzip | Anwendung auf Landing Pages |
|---|---|
| **Clarity** | Jedes Element verdient seinen Platz. Keine dekorativen Icons wenn Text reicht |
| **Hierarchy** | Hero gross, Meta klein. Outcome-Zahlen bold, Details dim |
| **Color = Meaning** | gruen=Erfolg, gelb=Achtung, rot=Fehler, dim=sekundaer. NIE dekorativ |
| **Consistency** | Gleiche Marker ueberall (● ○ ✓ !) |
| **Breathing** | Grosszuegiges Padding, Sections mit 64px Abstand |
| **Progressive Disclosure** | Tabs statt alles auf einmal zeigen |

## 4. Interaktive Tabs (JavaScript)

Statt 4 Terminal-Mockups untereinander → klickbare Tabs die jeweils einen View zeigen.

**Vorteile:**
- Spart 70% vertikalen Platz
- Simuliert die echte App-Erfahrung
- Besucher koennen explorieren

**Bonus:** Keyboard-Shortcuts (1-4) auf der Website wie in der echten App.

```javascript
function showView(name) {
    document.querySelectorAll('.tab-view').forEach(v => v.classList.remove('active'));
    document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
    document.getElementById('view-' + name).classList.add('active');
    event.target.closest('.tab').classList.add('active');
}
```

## 5. Depersonalisierung Checkliste

Vor dem Veroeffentlichen JEDES Repos durchgehen:

- [ ] Grep nach persoenlichen Namen, Usernamen, Pfaden
- [ ] Grep nach `/Users/<name>/` in Source, Tests, Docs
- [ ] Grep nach privaten Projektnamen in Beispielen
- [ ] Grep nach `sk-`, `token`, `password`, `secret`, `credential`
- [ ] Grep nach persoenlichen Pfaden in Obsidian/Vault-Referenzen
- [ ] Tests nach Rename AUSFUEHREN (Variable-Rename kann Syntax brechen)
- [ ] GitHub-URLs sind gewollt und korrekt
- [ ] `.env` in `.gitignore` verifizieren

**Regex fuer Sweep:**
```bash
grep -rn "DEINNAME\|/Users/DEIN\|PRIVATPROJEKT" --include="*.{py,md,html,yaml,toml}" .
```

## 6. Experten-Review-Prozess

Jede Website durch 5 Perspektiven pruefenm:

| Rolle | Fragt nach |
|---|---|
| **UI Designer** | Visuelle Hierarchie, Spacing, Farben, Konsistenz |
| **UX Designer** | Informationsfluss, User Journey, CTA-Platzierung |
| **QA Engineer** | Kaputte Links, falsche Befehle, Console-Errors, Mobile |
| **Content Strategist** | Problem-Statement, Zielgruppe, Tonalitaet |
| **Developer (Zielgruppe)** | "Wuerde ich das installieren?" — Vertrauen, Kompetenz |

**Typische Findings:**
- Favicon fehlt (404 in Console)
- Install-Befehl stimmt nicht mit Realitaet ueberein
- Kein Problem-Statement — Features ohne Kontext
- Kein CTA-Button oder CTA am falschen Ort
- Kein Mobile-Responsive

## 7. Dark-Mode Farbpalette (bewaehrt)

```css
:root {
    --bg: #0d1117;        /* Hintergrund */
    --card: #161b22;      /* Karten/Panels */
    --border: #30363d;    /* Raender */
    --text: #e6edf3;      /* Primaertext */
    --dim: #7d8590;       /* Sekundaertext */
    --green: #3fb950;     /* Erfolg */
    --yellow: #d29922;    /* Warnung */
    --blue: #58a6ff;      /* Links, Akzent */
    --red: #f85149;       /* Fehler */
    --cyan: #79c0ff;      /* Labels */
    --magenta: #d2a8ff;   /* Hervorhebung */
}
```

Basiert auf GitHub Dark Theme — vertraut fuer Entwickler.

## 8. Mobile Breakpoint

```css
@media (max-width: 600px) {
    .hero h1 { font-size: 36px; }
    .term-body, .arch { font-size: 11px; padding: 16px; }
    .grid { grid-template-columns: 1fr; }
}
```

Terminal-Mockups muessen `overflow-x: auto` haben fuer horizontales Scrolling auf kleinen Screens.

## 9. Schritt-fuer-Schritt Vorgehen (neues Projekt)

1. **Inhalt zuerst:** Problem-Statement, Features, Architecture als Text BEVOR HTML
2. **Struktur:** Hero → Problem → Install → Demo → Features → Architecture → Footer
3. **Terminal-Mockups:** Echte CLI-Ausgabe kopieren, in `<pre>`-aehnliche Divs
4. **Farben:** Nur die 7 Farben aus der Palette, jede mit Bedeutung
5. **Review:** 5-Perspektiven-Check durchfuehren
6. **Depersonalisierung:** Checkliste abarbeiten
7. **Deploy:** GitHub Pages aus `/docs` Ordner
8. **Verify:** Screenshot mit Playwright, Console-Errors pruefen

## 10. Level-/Sektions-Farbsystem (aus Example Learning Path)

Wenn eine Site mehrere Bereiche/Level hat, gibt jedem Bereich eine eigene Akzentfarbe. Sofortige visuelle Orientierung.

**Apple System Colors (Dark Mode) als Ausgangspunkt:**
```css
--l1: #2997FF;  /* Blue */
--l2: #30D158;  /* Green */
--l3: #FF9F0A;  /* Orange */
--l4: #BF5AF2;  /* Purple */
```

**Umsetzung:**
1. Statische Token pro Sektion (`--af-l1` bis `--af-l4`)
2. Kontextuelle Token (`--af-level-color`) via `data-level` Attribut auf `<body>`
3. Inline-Script erkennt Sektion aus URL-Pfad und setzt `data-level`
4. Sidebar, Badges, Heroes, Progress-Indikatoren nutzen `var(--af-level-color)`
5. Fallback auf globalen Accent wenn kein Level aktiv

**Warum es funktioniert:** User weiss sofort wo er ist, ohne Seitenname zu lesen.

## 11. Custom Components fuer Doku-Sites

Wiederverwendbare Astro-Components die in jedem Starlight-Projekt funktionieren:

| Component | Zweck | Props |
|---|---|---|
| **LessonHeader** | Badge + Progress-Dots | `level, lesson, total` |
| **LevelHero** | Gradient-Header pro Sektion | `level, title, description` |
| **LevelCard** | Card mit Farb-Akzent | `level, title, description, href` |
| **LessonIllustration** | Bild-Container | `src, alt` |

**i18n-Trick:** Locale aus `Astro.url.pathname` lesen statt separaten Prop — weniger Props, weniger Fehler.

## 12. Illustration-Strategie

| Aspekt | Empfehlung |
|---|---|
| **Quelle** | Storyset.com (Rafiki-Stil) — kostenlos, anpassbar |
| **Farbanpassung** | Jede Illustration auf Sektionsfarbe toenen |
| **Format** | SVG (skalierbar, klein) |
| **Platzierung** | Nach dem Titel, vor dem ersten Absatz |
| **Benennung** | `l1-01-thema.svg` — Level, Nummer, Slug |
| **Alternative** | unDraw.co (simpler), Humaaans (modular) |

**Wichtig:** Keine Emojis als Ersatz fuer Illustrationen — wirkt unprofessionell.

## 13. Dark-First Design (Starlight)

Starlight-spezifisches Dark-First Setup:
1. Kein `defaultTheme` Config (existiert nicht in Starlight)
2. CSS Token-Swap: `:root` = Dark, `[data-theme='light']` = Light
3. Starlight ThemeProvider respektiert `prefers-color-scheme` automatisch
4. `color-mix()` fuer subtile Akzent-Hintergruende

**Token-Migration bei Umbau:**
- Bestehende Tokens als Aliases behalten: `--old-token: var(--new-token);`
- Verhindert dass bestehende Components brechen

## 14. SVG-Diagramme statt Client-Side Rendering

Wenn eine Site Diagramme braucht (Flows, Skill Trees, Sequence Diagrams): Nicht Mermaid/client-side JS nutzen, sondern **template-generierte SVGs** committen.

### Warum
- **Performance:** Kein JavaScript-Plugin zur Laufzeit (Mermaid = ~300KB JS)
- **Konsistenz:** Einheitlicher Dark-Theme-Stil statt generischer Mermaid-Optik
- **Kontrolle:** Farben, Layout, Accessibility vollstaendig steuerbar
- **Zuverlaessigkeit:** Kein FOUC (Flash of Unstyled Content), kein Client-Rendering-Delay

### Pipeline
```
JSON-Daten → Node.js Generator → SVG-Dateien (committed) → Astro Image Import in MDX
```

### 3 Template-Typen (bewaehrt)

| Template | Einsatz | Layout |
|---|---|---|
| **Skill Tree** | Fortschrittsanzeige (9 Level) | Horizontal, parametrisiert nach Level + Variant |
| **Flow Diagram** | Overview/Combine Sections | @dagrejs/dagre Auto-Layout, Role-basierte Farben |
| **Sequence Diagram** | Interaktions-Ablaeufe (Tool Calling, Streaming) | Participants + Lifelines + Messages, manuell berechnet |

### Rollen-basiertes Farbsystem fuer Diagramme

| Rolle | Farbe | Gradient | Einsatz |
|---|---|---|---|
| `input` | Blau | #5B9FE6 → #3A7BD5 | Inputs, Daten, User |
| `process` | Gruen | #43C67A → #27AE60 | Verarbeitung, Core Logic |
| `output` | Orange | #F0944D → #E67E22 | Outputs, Ergebnisse, aktueller Fokus |
| `warning` | Rot | #EF6B6B → #E74C3C | Fehler, Ablehnungen |
| `neutral` | Grau | #64748b → #475569 | Deaktiviert, gesperrt |

**Konsistenz-Regel:** Gleiche Farbe = gleiche Bedeutung. Blau ist IMMER Input, nie dekorativ.

### Shared SVG Defs

Alle Templates teilen ein `<defs>` Modul mit:
- 5 Gradients (je Rolle)
- 4 Glow-Filter (Hervorhebung aktiver Nodes)
- 1 Shadow-Filter
- 1 Arrow-Marker

→ Ein Modul (`svg-defs.mjs`), importiert von allen Templates.

### Accessibility

Jede SVG bekommt:
- `role="img"` + `aria-label="..."` am `<svg>` Element
- Alt-Text im MDX `<Image>` Tag (lokalisiert: DE + EN)
- `title` + `desc` innerhalb der SVG (optional)

### i18n fuer Diagramme

SVGs sind **sprachneutral** — deutsche Labels funktionieren fuer beide Sprachen (technische Begriffe sind ohnehin englisch). Nur der `alt`-Text im MDX wird lokalisiert:
```mdx
<!-- DE -->
<Image src={diagram} alt="prompt fliesst in generateText, Ergebnis ist result.text" />
<!-- EN -->
<Image src={diagram} alt="prompt flows to generateText, result is result.text" />
```

### Migration bei bestehenden Mermaid-Sites

1. **Pilot:** Ein Level/Bereich komplett migrieren, visuell pruefen
2. **Batch:** Restliche Level in Chunks, 1 Commit pro Level
3. **Cleanup:** Mermaid-Plugin entfernen erst wenn 0 Bloecke verbleiben
4. **Automatisierung:** `npm run generate:diagrams` als prebuild Script

### Generator-Architektur (Referenz)

```
scripts/
  svg-defs.mjs              # Shared Gradients, Filter, Marker
  templates/
    skill-tree.mjs           # Parametrisiertes Skill-Tree Template
    flow.mjs                 # Dagre-Layout Flow Template
    sequence.mjs             # Sequence Diagram Template
  generate-diagrams.mjs      # Entry Point — liest JSON, generiert SVGs
src/
  diagrams/
    skill-trees.json         # Skill Tree Daten
    level-N/cX-type.json     # Flow/Sequence Daten pro Diagramm
  assets/diagrams/           # Generierte SVGs (committed!)
```

### Key Learning: Dagre fuer Auto-Layout

`@dagrejs/dagre` berechnet automatisch Node-Positionen und Edge-Pfade. Kein manuelles x/y fuer Flow-Diagramme. Einstellungen die gut funktionieren:
- `nodesep: 25` (vertikaler Abstand)
- `ranksep: 60` (horizontaler Abstand)
- `edgesep: 15`
- Node-Breite: `max(100, min(180, labelLength * 9 + 24))`

## 15. Interaktive Demos (aus Example CLI Tool)

Statische Seiten wirken "eingeschlafen". Interaktive Elemente machen den Unterschied zwischen "interessant" und "ich installiere das jetzt".

### Terminal-Animation (CSS-only)

Zeilen erscheinen nacheinander mit `animation-delay`. Blinkender Cursor am Ende. Kein JS noetig.

```css
.term-line { opacity: 0; animation: termAppear 0.3s ease forwards; }
.term-line-1 { animation-delay: 0.3s; }
.term-line-2 { animation-delay: 0.8s; }
/* ... gestaffelt */
@keyframes termAppear {
    from { opacity: 0; transform: translateY(4px); }
    to { opacity: 1; transform: translateY(0); }
}
.term-cursor { animation: blink 1s infinite; }
@keyframes blink { 0%, 50% { opacity: 1; } 51%, 100% { opacity: 0; } }
```

### Click-to-Mask Demo

User klickt Button, Secrets werden live durch Placeholders ersetzt. Gestaffelte Animation pro Zeile.

```html
<span class="secret" data-mask="[API_KEY_1]">sk-ant-api03-xYzAbCdEfG</span>
<button onclick="toggleMask()">Click to mask</button>
```

```javascript
function toggleMask() {
    document.querySelectorAll('.secret').forEach((el, i) => {
        setTimeout(() => {
            if (!el.classList.contains('is-masked')) {
                el.dataset.original = el.textContent;
                el.textContent = el.dataset.mask;
                el.classList.add('is-masked');
            } else {
                el.textContent = el.dataset.original;
                el.classList.remove('is-masked');
            }
        }, i * 150); // gestaffelt
    });
}
```

```css
.secret { color: #f87171; transition: all 0.4s ease; }
.secret.is-masked { color: var(--accent); background: var(--accent-dim); }
```

**Warum es funktioniert:** User ERLEBT den Effekt statt ihn zu lesen. Groesster Ueberzeugungsfaktor auf der ganzen Seite.

## 16. Scroll-Animationen (Lebendigkeit)

```javascript
const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
        if (entry.isIntersecting) entry.target.classList.add('visible');
    });
}, { threshold: 0.1 });
document.querySelectorAll('.animate-in').forEach(el => observer.observe(el));
```

```css
.animate-in {
    opacity: 0; transform: translateY(20px);
    transition: opacity 0.6s ease, transform 0.6s ease;
}
.animate-in.visible { opacity: 1; transform: translateY(0); }
.delay-1 { transition-delay: 0.15s; }
.delay-2 { transition-delay: 0.3s; }
```

**Tipp:** Feature-Cards mit Hover-Lift:
```css
.card:hover { transform: translateY(-2px); border-color: var(--accent); transition: all 0.2s; }
```

## 17. FAQ-Section (Details/Summary Pattern)

Beantwortet die 5 haeufigsten Bedenken BEVOR der User sie hat:

1. Geschwindigkeit ("Wird mein Tool langsamer?")
2. False Positives ("Was wenn es etwas Falsches maskiert?")
3. Sicherheit ("Ist das Tool selbst sicher?")
4. Qualitaet ("Funktioniert das Tool noch richtig mit maskierten Daten?")
5. Kompatibilitaet ("Funktioniert es nur mit X?")

```html
<details class="faq-item">
    <summary>Does it slow down my tool?</summary>
    <p>Barely. Less than 50ms per request...</p>
</details>
```

```css
.faq-item summary {
    padding: 18px 0; cursor: pointer; font-weight: 500;
    list-style: none; display: flex; justify-content: space-between;
}
.faq-item summary::after { content: '+'; font-size: 20px; }
.faq-item[open] summary::after { content: '−'; }
.faq-item summary::-webkit-details-marker { display: none; }
```

## 18. Big Picture Architektur (HTML/CSS statt SVG)

SVG-Diagramme die im Code geschrieben werden sehen immer "hand-coded" aus und rendern je nach System anders. Besser: HTML/CSS-basierte Diagramme.

**Pattern: Zwei-Zonen-Layout**
```
┌─ ─ ─ ─ ─ ─ ─ ─ ─ ─┐    ┌─ ─ ─ ─ ─ ─ ─ ─┐
  Your Machine              Cloud
  ┌─────────┐              ┌─────────┐
  │ Source   │  ──→         │ Target  │
  └─────────┘  sanitized   └─────────┘
  ┌─────────┐              ┌─────────┐
  │ Proxy   │  ←──         │ What    │
  │ ┌──┐┌──┐│  response    │ they see│
  │ └──┘└──┘│              │ vs not  │
  └─────────┘              └─────────┘
└─ ─ ─ ─ ─ ─ ─ ─ ─ ─┘    └─ ─ ─ ─ ─ ─ ─ ─┘
```

- Gestrichelte Rahmen fuer Zonen (`border: 2px dashed`)
- Zone-Labels als positioned pseudo-elements
- Animierte Pfeile zwischen den Zonen (`animation: arrowPulse`)
- 2x2 Grid innerhalb der Proxy-Box fuer Teilfunktionen
- "What they see" vs "What they don't see" Kaesten im Target

## 19. Story/Motivation Section

Jedes Tool braucht eine Seele. Am Ende der Page, als emotionaler Abschluss.

**Pattern:**
```html
<section class="story">
    <h2>Why this exists</h2>
    <p>Started with observation → heard a story → realized the stakes → built the tool</p>
</section>
```

- Max 3 kurze Absaetze
- Authentisch, nicht Marketing
- Ein starker Leitsatz als Anker ("Privacy tools need to exist before you need them")
- Kein "we" wenn es ein Solo-Projekt ist

## 20. SEO & Social Meta-Tags (Pflicht-Checkliste)

```html
<meta name="description" content="...">
<meta property="og:title" content="Name — Short Description">
<meta property="og:description" content="...">
<meta property="og:type" content="website">
<meta property="og:url" content="https://...">
<meta property="og:image" content="https://.../preview.png">
<meta name="twitter:card" content="summary">
<meta name="twitter:title" content="...">
<meta name="twitter:description" content="...">
```

**Wichtig:** `og:image` sollte ein PNG/JPG sein (1200x630px optimal), kein SVG. Viele Social-Previews unterstuetzen kein SVG.

## 21. Erweiterte Scroll-Narrative (optimierte Section-Reihenfolge)

Basierend auf Learnings aus mehreren Projekten — die Reihenfolge die am besten konvertiert:

1. **Hero** — Mascot + Name + One-Liner + Badges + CTA (5 Sekunden)
2. **Terminal-Demo** — Tool in Aktion zeigen (Show, Don't Tell)
3. **Why** — Emotionaler Hook / Blockquote (Motivation)
4. **Before/After** — Interaktiv wenn moeglich (Click to mask)
5. **How it works** — Big Picture Diagramm (Gesamtueberblick)
6. **What it catches/does** — Scannbares Grid (kein Text-Wall)
7. **Features** — Cards mit Icons + Hover
8. **FAQ** — Details/Summary, 5 Bedenken
9. **Quick Start** — Schritte MIT Erklaerungen
10. **Story** — Wer und warum (emotionaler Abschluss)
11. **Footer** — Links, Docs, Lizenz, Voraussetzungen

**Gegenueber Abschnitt 1:** Terminal-Demo kommt FRUEHER (direkt nach Hero), Why/Story sind getrennt (Why frueher, Story spaeter).

## 22. Bewertungs-Checkliste (Website Quality Score)

Fuer jedes Website-Projekt vor Launch pruefen:

- [ ] Versteht man in 5 Sekunden was das Tool tut?
- [ ] Gibt es eine interaktive Demo oder Terminal-Animation?
- [ ] Gibt es ein Before/After oder visuellen Vergleich?
- [ ] Sind die Headings gross genug um beim Scrollen aufzufallen? (28px+)
- [ ] Gibt es Scroll-Animationen die die Seite lebendig machen?
- [ ] Gibt es eine FAQ die Bedenken adressiert?
- [ ] Sind Meta/OG-Tags fuer Social Sharing gesetzt?
- [ ] Ist die Seite auf Mobile nutzbar und getestet?
- [ ] Gibt es eine Story/Motivation die erklaert WARUM?
- [ ] Wuerde ein Fremder nach dem Lesen installieren wollen?

**Scoring:** Jeder Punkt = 1. Score 8+ = publishable. Score 5-7 = needs work. Score <5 = draft.

## 23. Referenz-Seiten (Best Practices, erweitert)

| Seite | Was man lernen kann |
|---|---|
| linear.app | Dark Theme perfekt, Animationen, Visual Storytelling |
| warp.dev | Terminal-Tool zeigt Produkt IN ACTION |
| supabase.com | Developer-focused, interaktive Code-Beispiele |
| tailwindcss.com | Live-Code-Playground als Hero-Element |
| raycast.com | Features als Kurzvideos |
| fig.io | CLI-Tool Landing, Terminal-Animationen |
