<!-- TEMPLATE: Checklist / Content Project README (Type 4)
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
  <!-- One strong sentence. What is this checklist + who is it for. -->
  <strong>{{TAGLINE}}</strong><br>
  <!-- One supporting sentence on scope or origin (optional). -->
  {{SUBTITLE}}
</p>

<p align="center">
  <!-- Adjust badge labels/colors to reflect actual state. -->
  <img src="https://img.shields.io/badge/items-{{ITEM_COUNT}}-blue" alt="Items">
  <img src="https://img.shields.io/badge/version-{{VERSION}}-orange" alt="Version">
  <img src="https://img.shields.io/badge/license-{{LICENSE}}-lightgrey" alt="License">
</p>

---

## Why This Exists

<!-- 3–5 sentences on context and origin.
     Answer: what gap does this fill? Where does the pain come from?
     Include the origin story if it's authentic and brief (one sentence max). -->

{{WHY_DESCRIPTION}}

<!-- Optional: a short motivating quote or principle in a blockquote. -->
<!-- > "{{MOTIVATING_QUOTE}}" -->

## Who This Is For

<!-- Describe the primary audience in 2–3 bullet points.
     Be specific. "Developers" is too broad. "Backend engineers deploying LLM-based agents" is good.
     Optionally add a "Not for" line to set expectations. -->

**This checklist is for:**

- {{AUDIENCE_1}}
- {{AUDIENCE_2}}
- {{AUDIENCE_3}}

<!-- Optional: prerequisites or assumed knowledge. -->
<!-- **Assumed knowledge:** {{PREREQUISITES}} -->

## The Categories

<!-- Overview table of all checklist sections.
     Item count should reflect the actual number of checkboxes in each category.
     Link anchors to the section headers in the actual checklist if it lives in this README,
     or link to the rendered version / website. -->

| Category | Items | What it covers |
|---|---|---|
| **{{CATEGORY_1}}** | {{CAT_1_COUNT}} | {{CAT_1_DESCRIPTION}} |
| **{{CATEGORY_2}}** | {{CAT_2_COUNT}} | {{CAT_2_DESCRIPTION}} |
| **{{CATEGORY_3}}** | {{CAT_3_COUNT}} | {{CAT_3_DESCRIPTION}} |
| **{{CATEGORY_4}}** | {{CAT_4_COUNT}} | {{CAT_4_DESCRIPTION}} |
| **{{CATEGORY_5}}** | {{CAT_5_COUNT}} | {{CAT_5_DESCRIPTION}} |
| **Total** | **{{TOTAL_COUNT}}** | |

## Quick Start

<!-- How does someone actually USE this checklist?
     Cover the 2–3 most common ways: copy-paste, fork, print, web.
     Keep each option to one command or one action. -->

**Option 1 — Use the interactive version (recommended):**
[{{INTERACTIVE_LINK_TEXT}}]({{INTERACTIVE_URL}})

**Option 2 — Clone and use locally:**

```bash
{{CLONE_COMMAND}}
```

**Option 3 — Copy the raw checklist:**
[{{RAW_CHECKLIST_LINK_TEXT}}]({{RAW_CHECKLIST_URL}})

<!-- Add any setup or customization note if needed. -->
{{QUICK_START_NOTE}}

## Quick Link

<!-- A prominent, single-line link to the finished, rendered checklist.
     This is the most important link in the README — make it impossible to miss. -->

**The checklist:** [{{CHECKLIST_DISPLAY_URL}}]({{CHECKLIST_URL}})

## Sources & Credits

<!-- List the authoritative sources that informed this checklist.
     Format: [Source Name](URL) — one-sentence description of relevance.
     Aim for 3–8 sources. Quality > quantity.
     Separate primary sources from community contributions if applicable. -->

### Primary Sources

- [{{SOURCE_1_NAME}}]({{SOURCE_1_URL}}) — {{SOURCE_1_DESCRIPTION}}
- [{{SOURCE_2_NAME}}]({{SOURCE_2_URL}}) — {{SOURCE_2_DESCRIPTION}}
- [{{SOURCE_3_NAME}}]({{SOURCE_3_URL}}) — {{SOURCE_3_DESCRIPTION}}

### Community Contributions

<!-- Remove this section if there are no community contributors yet. -->
- [{{CONTRIBUTOR_1}}]({{CONTRIBUTOR_1_URL}}) — {{CONTRIBUTOR_1_CONTRIBUTION}}

## Versioning

<!-- Short changelog. Most recent version first.
     Format: version number, date, 1–3 bullet points of changes.
     This section earns Gold tier — don't skip it. -->

### {{VERSION}} — {{RELEASE_DATE}}

- {{CHANGE_1}}
- {{CHANGE_2}}

### {{PREVIOUS_VERSION}} — {{PREVIOUS_DATE}}

- Initial release

## FAQ

<!-- Answer the 5 questions your audience will ask before trusting and using this.
     Typical concerns: completeness, maintenance, authority, how to contribute, format.
     Be honest and direct. -->

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

<!-- Specify what kinds of contributions are welcome.
     Be explicit about the process: issue first, what a good PR looks like,
     how sources should be cited, what earns a merge vs. a close. -->

Contributions welcome. To propose a change:

1. **Open an issue** describing the item to add, update, or remove — include a source link.
2. **Submit a PR** once the issue is acknowledged.
3. **New items** require a reference to an authoritative source.
4. **Removals** require a rationale.

<!-- Link to CONTRIBUTING.md if it exists. -->
<!-- See [CONTRIBUTING.md](CONTRIBUTING.md) for the full guide. -->

## License

{{LICENSE}}
