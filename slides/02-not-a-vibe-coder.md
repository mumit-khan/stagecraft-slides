---
layout: default
transition: slide-left
---

# Stagecraft is not a chat-to-code loop

<div class="compare-grid">
  <div class="compare-col col-left">
    <div class="col-heading">Chat-driven AI tools</div>
    <ul>
      <li>Chat-driven: one prompt, one session</li>
      <li>Context is the conversation window</li>
      <li>Output: code, maybe tests</li>
      <li>Audit: scrollback</li>
      <li>One model, end-to-end</li>
    </ul>
  </div>
  <div class="compare-col col-right">
    <div class="col-heading">Stagecraft</div>
    <ul>
      <li>Pipeline-driven: 18 ordered stages</li>
      <li>Context is structured artifacts on disk</li>
      <li>Output: brief + design + code + gates + retro</li>
      <li>Audit: <code>cat pipeline/gates/*.json</code></li>
      <li>Right model per role, by config</li>
    </ul>
  </div>
</div>

<style>
.slidev-layout { padding: 40px 60px 60px 60px; }
h1 { color: #4B286D; margin-bottom: 0.8em; }
.compare-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 0;
  height: calc(100% - 80px);
}
.compare-col { padding: 0 2em; }
.col-left { border-right: 3px solid #E3E6E8; padding-left: 0; }
.col-right {}
.col-heading { color: #4B286D; font-size: 1.05em; font-weight: 600; margin-bottom: 0.6em; }
li { color: #2C2E30; line-height: 1.7; margin-bottom: 0.35em; font-size: 0.95em; }
ul { margin-left: 1.2em; }
code { background: #F4F4F7; padding: 0.1em 0.3em; border-radius: 3px; font-size: 0.85em; color: #2C2E30; }
</style>

<!--
Address the skepticism directly — don't wait for Q&A.

"You've seen a dozen AI coding tools this quarter. Most of them are a better autocomplete, or a smarter chat window — a Cursor session, a Copilot Workspace task. Stagecraft is a different category: it's an *orchestration layer*. The AI tools (Claude, Codex, Gemini) are still doing the work — Stagecraft is the process layer that runs them through a structured pipeline."

"The core design principle: the core never calls a model. It emits prompts and validates JSON. Model-agnosticism follows from that directly."

Land on: "If you're happy with chat-driven AI coding for your use case — great, this isn't for you. If you need gated process, multi-model routing, and an on-disk audit trail — keep listening."
-->
