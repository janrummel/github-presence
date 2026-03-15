# Project Types & Quality Tiers

Five project types, each with specific requirements for README and website quality. Use the review skill (`/website-review`) to check your repo against the matching checklist.

## Project Types

### Type 1: CLI Tool / Dev Tool

Tools installed via package manager, used from the terminal.

**README:**
- Problem statement (why does this exist)
- Install + Usage instructions
- Quick Start (3 commands max)
- Configuration (YAML/ENV example)
- Feature overview (what it does/detects)
- Architecture overview
- Development (tests, setup)
- Before/After comparison (Gold)
- FAQ (Gold)
- Contributing guide (Gold)

**Website (Gold+):**
- Terminal animation (tool in action)
- Interactive demo (click-to-try)
- Architecture diagram (big picture)
- FAQ section (5 common concerns)
- Story/motivation section
- Dark theme, monospace aesthetic
- Meta/OG tags for social sharing
- Mobile responsive
- Scroll animations

### Type 2: Learning Path / Course

Tutorials, curricula, multi-lesson learning experiences.

**README:**
- What you'll learn (learning objectives)
- Who is this for (audience + prerequisites)
- Curriculum / table of contents
- How to start (entry point)
- License + Contributing
- Learning outcomes per chapter/level (Gold)
- Detailed prerequisites (Gold)
- FAQ (Gold)

**Website (Gold+):**
- Multi-page structure (Starlight or custom)
- Chapter/level navigation
- Progress indicators
- Illustrations per chapter
- Level color system (visual orientation)
- Responsive reading experience
- Meta/OG tags for social sharing

### Type 3: Framework / Starter Kit

Templates, scaffolds, and reusable project structures.

**README:**
- What it is + why you need it
- Quick Start (Clone → Configure → Run)
- Without/With comparison
- Architecture overview
- Component/skill reference
- Extensibility (build your own plugins/skills)
- Starter vs Full distinction (Gold)
- FAQ (Gold)
- Contributing guide (Gold)

**Website (Gold+):**
- Terminal/typewriter demo
- Architecture visualization (flow diagram)
- Feature cards (skills/components)
- Comparison table (starter vs full)
- FAQ section
- Story/motivation
- Meta/OG tags for social sharing
- Mobile responsive

### Type 4: Checklist / Content Project

Security checklists, guides, reference material.

**README:**
- What is the checklist + context
- Who is it for
- Quick link to the finished checklist
- How to contribute
- Sources/references
- FAQ (Gold)
- Versioning / changelog (Gold)

**Website (Gold+):**
- Single page, content-focused
- Checklist as interactive elements
- Printable version (@media print)
- Inline source references
- Minimal UI, focus on content
- Meta/OG tags for social sharing
- Mobile responsive

### Type 5: Mini Tool / Experiment

Small scripts, proof of concepts, one-off utilities.

**README:**
- What it does (1-2 sentences)
- How to run (1 command)
- Caveats / limitations
- Dependencies

**Website:** None needed.

## Quality Tiers

| Tier | When to target | README | Website |
|------|----------------|--------|---------|
| **Bronze** | Experiment, mini tool | Problem + Install + Usage | None needed |
| **Silver** | Active project, not public | + Architecture + Config + Tests | Optional |
| **Gold** | Public release | + Before/After + FAQ + Contributing | Full landing page |
| **Platinum** | Ecosystem component | + Cross-references + API docs | Ecosystem integration |

**Tiers are cumulative:** Gold includes everything from Bronze and Silver. A single FAIL in any tier means that tier is not reached.

## How the Review Skill Uses This

The review skill (`/website-review`) maps each project type to a checklist file:

| Type | Checklist |
|------|-----------|
| CLI Tool | `skill/checklists/cli-tool.md` |
| Learning Path | `skill/checklists/lernreise.md` |
| Framework | `skill/checklists/framework.md` |
| Checklist | `skill/checklists/checklist.md` |
| Mini Tool | `skill/checklists/mini-tool.md` |

Each checklist defines criteria grouped by tier (Bronze/Silver/Gold/Platinum) and section (README/Website). The skill evaluates each criterion as PASS or FAIL using static file analysis (Read + Grep).
