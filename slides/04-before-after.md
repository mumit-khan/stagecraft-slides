---
layout: two-cols-header
transition: slide-left
---

# Same work — radically different output

::left::

**Before**

- One chat log per feature
- Approvals in messages
- Scope = what the agent did
- Tests if the agent remembered
- Audit = scrollback search

::right::

<v-click>

**After — Stagecraft**

- 17 artifacts + gates per feature
- Approvals in `pipeline/gates/*.json`
- Scope = `pipeline/brief.md`, versioned
- Tests gated — 1:1 criterion mapping
- Audit = `cat pipeline/gates/*.json`

</v-click>

<style>
.slidev-layout { padding: 40px 60px 60px 60px; }
h1 { color: #4B286D; margin-bottom: 0.6em; }
h2 { color: #4B286D; margin-bottom: 0.5em; }
p, li { color: #2C2E30; line-height: 1.6; margin-bottom: 0.4em; }
ul { margin-left: 1.2em; margin-bottom: 0.8em; }
strong { color: #4B286D; }
code { background: #F4F4F7; padding: 0.1em 0.3em; border-radius: 3px; font-size: 0.85em; color: #2C2E30; }
</style>

<!--
Walk the rows by pairing them left-to-right. Spend a beat on three:

1. "1:1 criterion mapping" — Stage 6's gate requires all_acceptance_criteria_met: true and a 1:1 mapping. The validator rejects gates that claim PASS without it.

2. "Right model per role" — Claude for design, Codex for backend, Gemini for QA. The seam between them is JSON, not a model API.

3. "Audit = cat pipeline/gates/*.json" — this is the payoff. Everything on disk.

Transition: "Here's what one of those gates actually looks like — and then I'll show you a real one."
-->
