<!-- ============================================================
  TEMPLATE: Learning Path / Course README
  Type: Lernreise (Curriculum-style project)
  Based on: level-up-ai (primary) + ai-product-thinking (secondary)
  Version: 1.0.0

  HOW TO USE THIS TEMPLATE
  1. Replace all {{PLACEHOLDERS}} with your project's content.
  2. Remove comments (<!-- ... -->) before publishing.
  3. Delete sections that don't apply — don't leave them empty.
  4. Keep the centered hero block as-is; it sets the visual tone.
  ============================================================ -->

<!-- HERO: Centered block with emoji, title, tagline, badges, nav.
     - emoji: Pick one that represents the learning domain visually.
       Use the Apple emoji CDN: https://em-content.zobj.net/source/apple/391/
     - title: Short, punchy. The repo name, properly capitalized.
     - tagline line 1 (strong): The one-line value proposition. What transformation does this course deliver?
     - tagline line 2: Supporting detail — scope (chapters/lessons/etc.) + key differentiator.
     - nav links: 4-5 anchors to the most important sections below.
     - badges: Reflect scope (chapters/levels/lessons), languages, license.
       Generator: https://shields.io — use consistent color palette per project. -->

<p align="center">
  <img src="https://em-content.zobj.net/source/apple/391/{{EMOJI_SLUG}}" width="80" alt="{{PROJECT_NAME}}">
</p>

<h1 align="center">{{PROJECT_NAME}}</h1>

<p align="center">
  <strong>{{TAGLINE_LINE_1}}</strong><br>
  {{TAGLINE_LINE_2}}
</p>

<p align="center">
  <a href="{{WEBSITE_URL}}">Website</a> ·
  <a href="#curriculum">Curriculum</a> ·
  <a href="#who-is-this-for">Who is this for</a> ·
  <a href="#run-locally">Run locally</a> ·
  <a href="#{{FIFTH_NAV_ANCHOR}}">{{FIFTH_NAV_LABEL}}</a>
</p>

<!-- BADGES: Swap values and colors to match your project's scope.
     Recommended: scope metric (chapters/levels) · secondary metric (lessons/challenges) · language · license -->
<p align="center">
  <img src="https://img.shields.io/badge/{{SCOPE_LABEL}}-{{SCOPE_COUNT}}-{{BADGE_COLOR_1}}" alt="{{SCOPE_LABEL}}">
  <img src="https://img.shields.io/badge/{{UNIT_LABEL}}-{{UNIT_COUNT}}-{{BADGE_COLOR_2}}" alt="{{UNIT_LABEL}}">
  <img src="https://img.shields.io/badge/languages-EN%20%2B%20DE-58a6ff" alt="Languages">
  <img src="https://img.shields.io/badge/license-{{LICENSE_BADGE_LABEL}}-lightgrey" alt="License">
</p>

---

<!-- WHY / WHAT IS THIS: 2–4 sentence problem statement.
     Option A (level-up-ai style): Start with the pain point, then the solution.
       "X gets you to Y fast — but not to Z. This course closes the gap."
     Option B (ai-product-thinking style): Lead with scope, then differentiator in bold.
       "A complete, free curriculum for [audience]. N chapters, N lessons...
       **What makes it different:** [core differentiator]."
     Choose the style that fits your audience. Delete the other. -->

## Why?

<!-- Option A: Pain → Solution -->
{{PAIN_POINT}} — but not {{MISSING_CAPABILITY}}. This course closes the gap: {{SOLUTION_DESCRIPTION}}. Free, open source{{#if BILINGUAL}}, bilingual{{/if}}.

<!-- Option B: Scope + Differentiator (comment out Option A if using this) -->
<!--
A complete, free curriculum for {{TARGET_AUDIENCE}}. {{CHAPTER_COUNT}} chapters, {{LESSON_COUNT}} lessons{{#if CASE_STUDIES}}, {{CASE_STUDY_COUNT}} real-world case studies{{/if}} — fully bilingual (EN + DE).

**What makes it different:** {{DIFFERENTIATOR_STATEMENT}}
-->

---

<!-- CURRICULUM TABLE: The backbone of the README. One row per chapter/level.
     Columns: use the pair that best fits your content type.
     - Engineering/code courses: Level | Topic | What you'll build
     - Concept/PM/decision courses: Chapter | Topic | Lessons (or key concepts)
     Keep topic names short. The "What you'll build / Lessons" column is the hook. -->

## Curriculum

{{CURRICULUM_TABLE}}

<!-- EXAMPLE (code course style, from level-up-ai):
| Level | Topic | What you'll build |
|-------|-------|-------------------|
| 1 | {{LEVEL_1_TOPIC}} | {{LEVEL_1_DELIVERABLE}} |
| 2 | {{LEVEL_2_TOPIC}} | {{LEVEL_2_DELIVERABLE}} |
| ... | ... | ... |
| Ref | Reference | {{REFERENCE_DESCRIPTION}} |
-->

<!-- EXAMPLE (concept course style, from ai-product-thinking):
| Chapter | Topic | Lessons |
|---------|-------|---------|
| 01 | **{{CHAPTER_1_TOPIC}}** | {{CHAPTER_1_LESSONS}} |
| 02 | **{{CHAPTER_2_TOPIC}}** | {{CHAPTER_2_LESSONS}} |
| ... | ... | ... |
-->

---

<!-- WHAT YOU'LL LEARN: Per-chapter learning outcomes.
     Include this section when the course is concept-heavy (PM, strategy, soft skills).
     Skip it for hands-on engineering courses where "What you'll build" already carries the outcome.
     Each outcome: 2–3 action verbs. "Understand X, evaluate Y, decide when Z." -->

## What you'll learn

{{LEARNING_OUTCOMES_TABLE}}

<!-- EXAMPLE:
| Chapter | Learning Outcomes |
|---------|------------------|
| 01 | {{CHAPTER_1_OUTCOMES}} |
| 02 | {{CHAPTER_2_OUTCOMES}} |
-->

---

<!-- HOW EACH LESSON WORKS: Explain the pedagogical pattern.
     This is a trust-builder — readers want to know the format before committing.
     Format: list the steps in the repeating lesson structure, then describe the capstone/synthesis.
     - Engineering courses: name the hands-on step (TRY, COMBINE, Boss Fight).
     - Concept courses: name the decision/reflection step (Scenario, Decide, Synthesize). -->

## How each {{LESSON_UNIT}} works

Every {{LESSON_UNIT}} follows the same {{STEP_COUNT}}-step pattern:

**{{STEP_1}}** ({{STEP_1_DESCRIPTION}}) → **{{STEP_2}}** ({{STEP_2_DESCRIPTION}}) → **{{STEP_3}}** ({{STEP_3_DESCRIPTION}}) → **{{STEP_4}}** ({{STEP_4_DESCRIPTION}}) → **{{STEP_5}}** ({{STEP_5_DESCRIPTION}}){{#if STEP_6}} → **{{STEP_6}}** ({{STEP_6_DESCRIPTION}}){{/if}}

<!-- Describe the capstone/synthesis that closes each chapter/level: -->
Each {{CHAPTER_UNIT}} ends with a **{{CAPSTONE_NAME}}** — {{CAPSTONE_DESCRIPTION}}.

---

<!-- WHO IS THIS FOR: Audience bullets + prerequisites + time estimate.
     - 3–4 audience bullets. Be specific. Name the job title or mindset.
     - Prerequisites: toolchain only (Node version, API key, etc.). No fluff.
     - Time: give a range. Mention standalone-chapter option if applicable. -->

## Who is this for?

- **{{AUDIENCE_1_LABEL}}** {{AUDIENCE_1_DESCRIPTION}}
- **{{AUDIENCE_2_LABEL}}** {{AUDIENCE_2_DESCRIPTION}}
- **{{AUDIENCE_3_LABEL}}** {{AUDIENCE_3_DESCRIPTION}}

**Prerequisites:** {{PREREQUISITES}}

**Time:** {{TIME_ESTIMATE}}

---

<!-- CASE STUDIES (optional): Social proof through real-world examples.
     Include when the course is grounded in real company decisions or events.
     Skip for purely technical/code courses unless you reference specific open-source projects.
     Format: single line, company names as anchor points. -->

## Case Studies

<!-- Remove this section if not applicable. -->
Real {{CASE_STUDY_DOMAIN}}: **{{CASE_STUDY_1}}** · **{{CASE_STUDY_2}}** · **{{CASE_STUDY_3}}** · **{{CASE_STUDY_4}}**

---

<!-- BUILT ON / VERSION INFO: Establishes credibility and currency.
     Include: version/date of referenced technology or framework, number of diagrams/scenarios,
     quality signal (peer-reviewed, tested code), and any notable production signals. -->

## Built on

{{BUILT_ON_STATEMENT}}

<!-- EXAMPLE (engineering): Based on the [{{FRAMEWORK}} v{{VERSION}}]({{FRAMEWORK_URL}}) (as of {{DATE}}). {{DIAGRAM_COUNT}} generated SVG diagrams. Every code example tested. All concepts linked to official documentation. -->
<!-- EXAMPLE (concept): Content as of {{DATE}}. {{SCENARIO_COUNT}} decision scenarios with real numbers. Peer-reviewed curriculum ({{REVIEW_SCORE}}). {{DIAGRAM_COUNT}} SVG architecture diagrams. Fully bilingual with native-quality translations. -->

---

<!-- RUN LOCALLY: Minimal quickstart. No explanation, just the commands.
     Use git clone + install + dev for courses that need a local server.
     Skip clone if the course is purely browser-based or has a live site. -->

## Run locally

```bash
git clone {{REPO_URL}}
cd {{REPO_DIRNAME}}
npm install
npm run dev
```

<!-- Add build command if relevant: -->
<!-- npm run build      # Production build -->

---

<!-- TECH STACK: One line. Link the main framework, list the rest inline.
     Pattern: [Primary Framework](url) + [Secondary](url) · Runtime · Format · Feature -->

## Tech Stack

{{TECH_STACK_LINE}}

<!-- EXAMPLE: [Astro](https://astro.build) + [Starlight](https://starlight.astro.build) · TypeScript · MDX · i18n (EN/DE) -->

---

<!-- SOURCES (optional for engineering courses): Credit upstream curricula and docs.
     Required when your course is derived from or built on existing open-source material.
     Skip for fully original content. -->

## Sources

<!-- Remove this section if not applicable. -->
Built on {{SOURCE_DESCRIPTION}} and official docs from {{SOURCE_DOCS_LIST}}.

---

<!-- RELATED PROJECTS: Cross-link sibling projects in the same ecosystem.
     1–3 entries. Bold the project name, then one sentence on how it relates.
     Pattern: **[Name](url)** — [What it is and how it complements this course]. -->

## Related Projects

**[{{RELATED_PROJECT_1_NAME}}]({{RELATED_PROJECT_1_URL}})** — {{RELATED_PROJECT_1_DESCRIPTION}}

<!-- Add more if applicable: -->
<!-- **[{{RELATED_PROJECT_2_NAME}}]({{RELATED_PROJECT_2_URL}})** — {{RELATED_PROJECT_2_DESCRIPTION}} -->

---

<!-- FAQ: 5 questions. Answer the real objections, not softball questions.
     Question types that convert skeptics:
     1. "Do I need [background X]?" — Lowers the barrier to entry.
     2. "How long does it take?" — Manages time expectations.
     3. "How is this different from [existing alternative]?" — Justifies switching.
     4. "Can I skip / start mid-course?" — Shows structural flexibility.
     5. Project-specific question (Boss Fight, Case Studies, licensing, teams, etc.)
     Keep answers to 2–4 sentences each. -->

## FAQ

**{{FAQ_1_QUESTION}}**
{{FAQ_1_ANSWER}}

**{{FAQ_2_QUESTION}}**
{{FAQ_2_ANSWER}}

**{{FAQ_3_QUESTION}}**
{{FAQ_3_ANSWER}}

**{{FAQ_4_QUESTION}}**
{{FAQ_4_ANSWER}}

**{{FAQ_5_QUESTION}}**
{{FAQ_5_ANSWER}}

---

<!-- CONTRIBUTING: 1–3 sentences. List the types of contributions you actually want.
     Typos, broken examples, translation fixes, new scenarios — be specific.
     Don't add a full CONTRIBUTING.md link unless you have one. -->

## Contributing

Found an error? Have a suggestion? Issues and pull requests are welcome — whether it's {{CONTRIBUTION_TYPES}}.

---

<!-- LICENSE: State the license(s) clearly.
     Two-tier license is common for learning content: content under CC, code under MIT.
     Use a single MIT if you don't distinguish between content and code. -->

## License

<!-- Option A: Two-tier (content + code) -->
Content: [{{CONTENT_LICENSE_NAME}}]({{CONTENT_LICENSE_URL}}) · Code: MIT

<!-- Option B: Single license -->
<!-- {{LICENSE_NAME}} -->
