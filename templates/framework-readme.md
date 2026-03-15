<!-- TEMPLATE: Framework / Starter Kit README (Type 3)
     Target quality tier: Gold
     Replace all {{PLACEHOLDER}} values with project-specific content.
     Remove HTML comments before publishing.
-->

<p align="center">
  <!-- Replace src with your project's emoji image or logo (80px wide) -->
  <img src="{{EMOJI_IMAGE_URL}}" width="80" alt="{{PROJECT_NAME}}">
</p>

<h1 align="center">{{PROJECT_NAME}}</h1>

<p align="center">
  <!-- One strong sentence. What it is + what it gives you. -->
  <strong>{{TAGLINE}}</strong><br>
  <!-- One supporting sentence with more detail (optional). -->
  {{SUBTITLE}}
</p>

<p align="center">
  <!-- Nav links to major sections. Keep to 4–5 items. -->
  <a href="#the-problem">The Problem</a> ·
  <a href="#whats-inside">What's Inside</a> ·
  <a href="#quick-start">Quick Start</a> ·
  <a href="#component-reference">Components</a> ·
  <a href="#extensibility">Extensibility</a>
</p>

<p align="center">
  <!-- Adjust badge labels/colors to reflect your project's actual state. -->
  <img src="https://img.shields.io/badge/status-{{STATUS}}-{{STATUS_COLOR}}" alt="Status">
  <img src="https://img.shields.io/badge/components-{{COMPONENT_COUNT}}-orange" alt="Components">
  <img src="https://img.shields.io/badge/license-{{LICENSE}}-lightgrey" alt="License">
</p>

---

## The Problem

<!-- 2–4 sentences on WHY this framework exists.
     What painful, repetitive, or error-prone situation does it address?
     Write from the perspective of someone who has felt the pain. -->

{{PROBLEM_DESCRIPTION}}

## Without / With

<!-- Show the before/after contrast clearly.
     Left column: the messy reality without this framework.
     Right column: what life looks like with it.
     Keep each cell to one tight phrase. -->

| | Without {{PROJECT_NAME}} | With {{PROJECT_NAME}} |
|---|---|---|
| **{{DIMENSION_1}}** | {{WITHOUT_1}} | {{WITH_1}} |
| **{{DIMENSION_2}}** | {{WITHOUT_2}} | {{WITH_2}} |
| **{{DIMENSION_3}}** | {{WITHOUT_3}} | {{WITH_3}} |
| **{{DIMENSION_4}}** | {{WITHOUT_4}} | {{WITH_4}} |

## What's Inside

<!-- Overview of all major components / skills / modules.
     Status values: Ready / Beta / Planned.
     Path column should reflect actual directory structure. -->

| Component | Path | Status | Description |
|---|---|---|---|
| **{{COMPONENT_1_NAME}}** | `{{COMPONENT_1_PATH}}` | {{COMPONENT_1_STATUS}} | {{COMPONENT_1_DESCRIPTION}} |
| **{{COMPONENT_2_NAME}}** | `{{COMPONENT_2_PATH}}` | {{COMPONENT_2_STATUS}} | {{COMPONENT_2_DESCRIPTION}} |
| **{{COMPONENT_3_NAME}}** | `{{COMPONENT_3_PATH}}` | {{COMPONENT_3_STATUS}} | {{COMPONENT_3_DESCRIPTION}} |
| **{{COMPONENT_4_NAME}}** | `{{COMPONENT_4_PATH}}` | {{COMPONENT_4_STATUS}} | {{COMPONENT_4_DESCRIPTION}} |

## Quick Start

<!-- Exactly 3 steps: Clone → Configure → Run.
     Commands must be copy-pasteable and correct.
     Add a short explanatory sentence under each step if needed. -->

```bash
# Step 1 — Clone
{{CLONE_COMMAND}}
```

```bash
# Step 2 — Configure
# {{CONFIGURE_DESCRIPTION}}
{{CONFIGURE_COMMAND}}
```

```bash
# Step 3 — Run
{{RUN_COMMAND}}
```

<!-- Optional: what happens after the run command (expected output or next action). -->
{{QUICK_START_OUTCOME}}

## Architecture Overview

<!-- Replace this block with a real diagram.
     Recommended formats:
       - ASCII art (simple flows)
       - Mermaid code block (if your renderer supports it)
       - Path to a committed SVG/PNG: ![Architecture](docs/architecture.png)

     The diagram should show: inputs → core components → outputs.
     Keep it to one screen width. -->

```
{{ARCHITECTURE_DIAGRAM_PLACEHOLDER}}
```

<!-- Add 1–3 sentences explaining the diagram if it is not self-evident. -->
{{ARCHITECTURE_DESCRIPTION}}

## Component / Skill Reference

<!-- List every component or skill a user would interact with directly.
     Group by category if there are more than 8.
     Link to individual docs files if they exist. -->

### {{CATEGORY_1}}

| Name | Purpose | Usage |
|---|---|---|
| `{{ITEM_1}}` | {{ITEM_1_PURPOSE}} | `{{ITEM_1_USAGE}}` |
| `{{ITEM_2}}` | {{ITEM_2_PURPOSE}} | `{{ITEM_2_USAGE}}` |

### {{CATEGORY_2}}

| Name | Purpose | Usage |
|---|---|---|
| `{{ITEM_3}}` | {{ITEM_3_PURPOSE}} | `{{ITEM_3_USAGE}}` |
| `{{ITEM_4}}` | {{ITEM_4_PURPOSE}} | `{{ITEM_4_USAGE}}` |

## Extensibility

<!-- Explain how a user adds their own components/skills/plugins.
     This should be a short walkthrough, not a full API reference.
     Cover: where to put the file, what shape it needs, how it gets picked up. -->

{{PROJECT_NAME}} is designed to be extended. To add your own {{COMPONENT_TYPE}}:

1. **Create** a new file in `{{EXTENSION_PATH}}/`
2. **Follow** the structure in `{{EXAMPLE_FILE}}`
3. **Register** it by {{REGISTRATION_STEP}}
4. **Verify** with `{{VERIFY_COMMAND}}`

<!-- Link to a more detailed guide if one exists. -->
See [`{{EXTENSION_DOCS_PATH}}`]({{EXTENSION_DOCS_PATH}}) for the full extension guide.

## Starter vs Full

<!-- Use this section if your framework ships in two modes: a lightweight starter
     and a complete/opinionated full version. Remove this section if not applicable.
     Examples: "starter kit" vs "production config", "minimal" vs "batteries included". -->

| | {{STARTER_NAME}} | {{FULL_NAME}} |
|---|---|---|
| **Size** | {{STARTER_SIZE}} | {{FULL_SIZE}} |
| **Setup time** | {{STARTER_SETUP}} | {{FULL_SETUP}} |
| **{{FEATURE_DIMENSION_1}}** | {{STARTER_F1}} | {{FULL_F1}} |
| **{{FEATURE_DIMENSION_2}}** | {{STARTER_F2}} | {{FULL_F2}} |
| **Best for** | {{STARTER_BEST_FOR}} | {{FULL_BEST_FOR}} |

## Roadmap

<!-- Keep this short and honest. Only include items you intend to ship.
     Use checkboxes so progress is visible over time. -->

- [x] {{DONE_ITEM_1}}
- [x] {{DONE_ITEM_2}}
- [ ] {{PLANNED_ITEM_1}}
- [ ] {{PLANNED_ITEM_2}}
- [ ] {{PLANNED_ITEM_3}}

## FAQ

<!-- Answer the 5 questions your target audience will have before adopting this.
     Typical concerns: compatibility, learning curve, maintenance, constraints, alternatives.
     Be direct. No marketing language. -->

**{{FAQ_Q1}}**
{{FAQ_A1}}

**{{FAQ_Q2}}**
{{FAQ_A2}}

**{{FAQ_Q3}}**
{{FAQ_A3}}

**{{FAQ_Q4}}**
{{FAQ_A4}}

**{{FAQ_Q5}}**
{{FAQ_A5}}

## Contributing

<!-- Specify where contributions are most needed.
     Mention the process (issue first, PR format, tests required).
     Keep it to 5 lines or less unless you have a CONTRIBUTING.md to link. -->

Contributions welcome. Priority areas:

- {{CONTRIBUTION_AREA_1}}
- {{CONTRIBUTION_AREA_2}}
- {{CONTRIBUTION_AREA_3}}

<!-- Uncomment and link if you have a separate contributing guide. -->
<!-- See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed guidelines. -->

Please open an issue before submitting large changes.

## License

{{LICENSE}}
