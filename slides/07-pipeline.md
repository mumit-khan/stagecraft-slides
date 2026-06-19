---
layout: default
transition: slide-left
---

# Seventeen stages — a track picks which ones run

```mermaid
%%{init: {'theme': 'base', 'themeVariables': {'primaryColor': '#4B286D', 'primaryTextColor': '#FFFFFF', 'secondaryColor': '#613889', 'lineColor': '#414547'}}}%%
flowchart LR
    A[Brief] --> B[Design] --> C[Build] --> D[Review] --> E[QA] --> F[Deploy]
```

<div class="track-hint"><code>full</code> all 17 &nbsp;·&nbsp; <code>quick</code> skips design &nbsp;·&nbsp; <code>nano</code> build+review+QA only &nbsp;·&nbsp; <code>hotfix</code> skips brief, keeps all safety</div>

<v-clicks>

- **Multi-role stages** — build + peer-review each dispatch 4 workstreams; gates merge with pessimistic status
- **Conditional stages** — security + migration-safety have <span v-mark.box="2" style="color:#4B286D">veto power</span>; no approval overrides them
- **Auto-complete** — sign-off folds at 100% criterion coverage; no human action

</v-clicks>

<style>
.slidev-layout { padding: 40px 60px 60px 60px; }
h1 { color: #4B286D; margin-bottom: 0.4em; }
p, li { color: #2C2E30; line-height: 1.6; margin-bottom: 0.3em; }
ul { margin-left: 1.2em; margin-bottom: 0.6em; }
.track-hint { color: #676E73; font-size: 0.78em; margin: 0.3em 0 0.7em 0; }
.track-hint code { background: #F4F4F7; padding: 0.1em 0.3em; border-radius: 3px; color: #4B286D; font-size: 0.95em; }
</style>

<!--
Point at the diagram first: "Six phases. Left to right. Brief → Design → Build → Review → QA → Deploy. The 17 stages live inside these phases — sub-stages, conditionals, workstreams."

Then the track hint: "A track is just a list of which stages run for a given change type. nano for a one-liner. full for anything touching auth, payments, or migrations. hotfix skips the brief because you already know what's broken — but keeps every safety stage."

Then the three properties with v-clicks as before.

Transition: "Let's talk about where you, the human, actually make decisions."
-->
