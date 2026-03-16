<p align="center">
  <img src="https://em-content.zobj.net/source/apple/391/gem-stone_1f48e.png" width="80" alt="GitHub Presence">
</p>

<h1 align="center">GitHub Presence</h1>

<p align="center">
  <strong>Quality framework for GitHub repos.</strong><br>
  Type-specific checklists, a design playbook, and a review skill for Claude Code.
</p>

<p align="center">
  <a href="https://janrummel.github.io/github-presence/">Website</a> ·
  <a href="#quick-start">Quick Start</a> ·
  <a href="#whats-inside">What's Inside</a> ·
  <a href="#project-types">Project Types</a> ·
  <a href="#quality-tiers">Quality Tiers</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/phase-1--3%20✓-blue" alt="Phase">
  <img src="https://img.shields.io/badge/types-5-orange" alt="Types">
  <img src="https://img.shields.io/badge/license-MIT-lightgrey" alt="License">
</p>

---

## The Problem

Every GitHub repo starts from scratch when it comes to README and website quality. There's no shared standard for what a CLI tool README needs vs. a learning path vs. a checklist project. Quality depends on the day, not on the type.

## Without / With

| | Without | With GitHub Presence |
|---|---|---|
| **README** | Ad-hoc, whatever feels right | Type-specific checklist (CLI tool ≠ course ≠ checklist) |
| **Quality** | Inconsistent across repos | Tiered scoring: Bronze → Silver → Gold → Platinum |
| **Review** | Manual, subjective | Automated skill checks every criterion |
| **Improvement** | "I should probably add a FAQ..." | "For Gold you need 3 more points: FAQ, Contributing, Mobile" |

## What's Inside

| Component | Status | Description |
|---|---|---|
| **Review Skill** (`skill/`) | Ready | Claude Code skill that checks your repo against type-specific checklists |
| **Playbook** (`playbook.md`) | Ready | 24-section design knowledge base for GitHub Pages landing pages |
| **Project Types** (`project-types.md`) | Ready | 5 project types with README + website requirements per quality tier |
| **Templates** (`templates/`) | Ready | 5 README templates + landing page HTML template per project type |
| **Design System** (`design-system/`) | Ready | Shared CSS kit (dark theme, terminals, cards, FAQ, grids) |
| **Website** (`docs/`) | Live | [Landing page](https://janrummel.github.io/github-presence/) with all components in action |

## Quick Start

The review skill is a [Claude Code](https://docs.anthropic.com/en/docs/claude-code) skill. To install:

```bash
# Clone this repo
git clone https://github.com/janrummel/github-presence.git

# Copy the skill to your Claude Code skills directory
cp -r github-presence/skill/ ~/.claude/skills/website-review/

# Navigate to any of your repos and run the review
cd ~/your-project
# In Claude Code, type: /website-review
```

The skill will:
1. Detect your project type (CLI tool, learning path, framework, checklist, or mini tool)
2. Suggest a target quality tier
3. Check every criterion and report PASS/FAIL
4. Show what's missing for the next tier

> **Note:** `/website-review` is a Claude Code skill command, not a CLI command. You need [Claude Code](https://docs.anthropic.com/en/docs/claude-code) to use it.

## Project Types

| Type | Examples | Key Difference |
|------|----------|----------------|
| **CLI Tool / Dev Tool** | Build tools, proxies, linters | Terminal demos, before/after comparisons |
| **Learning Path / Course** | Tutorials, curricula | Chapter navigation, progress indicators |
| **Framework / Starter Kit** | Templates, scaffolds | Architecture diagrams, starter vs. full comparison |
| **Checklist / Content** | Security checklists, guides | Interactive elements, printable version |
| **Mini Tool / Experiment** | Scripts, proof of concepts | Minimal — just problem + run command |

See [project-types.md](project-types.md) for the full requirements per type.

## Quality Tiers

| Tier | When to target | README | Website |
|------|----------------|--------|---------|
| **Bronze** | Experiment, mini tool | Problem + Install + Usage | None needed |
| **Silver** | Active project | + Architecture + Config + Tests | Optional |
| **Gold** | Public release | + Before/After + FAQ + Contributing | Full landing page |
| **Platinum** | Ecosystem component | + Cross-references + API docs | Ecosystem integration |

Tiers are cumulative — Gold includes everything from Bronze and Silver.

## Roadmap

- [x] **Phase 1:** Review skill with 5 type-specific checklists
- [x] **Phase 2:** README templates per project type (5 templates)
- [x] **Phase 3:** Shared design system + landing page template
- [x] **Website:** Landing page showcasing the framework in action

## FAQ

**What is this exactly?**
A quality framework that defines what a good GitHub repo looks like for different project types (CLI tools, courses, frameworks, checklists, mini tools) and provides a Claude Code skill to automatically check your repos against those standards.

**Do I need Claude Code?**
For the automated review skill, yes. The playbook, project types, and checklists are useful on their own as reference material — no tools needed.

**Can I add my own project type?**
Yes. Create a new checklist file in `skill/checklists/` following the same format (criteria grouped by tier, with IDs). The skill will pick it up automatically.

**What counts as Gold?**
All Bronze + Silver + Gold criteria for your project type must PASS. One FAIL means the tier is not reached. The review skill shows exactly what's missing.

**How do I contribute?**
See [Contributing](#contributing) below. New checklists, playbook improvements, and templates are all welcome.

## Contributing

Contributions welcome! Priority areas:

- New project type checklists
- Playbook additions (new patterns, reference sites)
- README/website templates (Phase 2)
- Design system components (Phase 3)

Please open an issue before submitting large changes.

## License

MIT
