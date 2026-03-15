# Shared Design System

Dark-theme CSS kit for developer tool landing pages. Extracted from proven Gold-tier websites.

## Files

| File | Description |
|------|-------------|
| `github-presence.css` | Complete CSS kit — variables, components, animations, responsive |

## Usage

```html
<link rel="stylesheet" href="github-presence.css">
```

## Customize

Override the accent color for your project:

```css
:root {
    --accent: #a78bfa;        /* purple for your project */
    --accent-dim: rgba(167, 139, 250, 0.12);
    --accent-glow: rgba(167, 139, 250, 0.25);
}
```

## Components Included

- **Hero** — centered layout with tagline, badges, CTA
- **Terminal mockup** — macOS-style terminal with line-by-line animation
- **Feature cards** — 2x2 grid with hover lift
- **FAQ** — details/summary accordion
- **Quick Start** — numbered steps with code blocks
- **Badges** — inline labels
- **Buttons** — primary (filled) + secondary (outline)
- **Sections** — alternating backgrounds, scroll-in animations
- **Footer** — centered links

## Default Palette

Based on GitHub Dark theme:

| Token | Value | Usage |
|-------|-------|-------|
| `--bg` | `#0d1117` | Page background |
| `--card` | `#161b22` | Cards, panels |
| `--border` | `#30363d` | Borders |
| `--text` | `#c9d1d9` | Body text |
| `--dim` | `#848d97` | Secondary text |
| `--accent` | `#58a6ff` | Links, highlights (override this) |
