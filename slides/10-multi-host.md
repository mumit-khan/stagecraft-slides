---
layout: two-cols
transition: fade
---

<style>
.slidev-layout.two-columns {
  grid-template-columns: 45% 55%;
}
</style>

# Route each role to the right host

```yaml {1-2|3-6|7-8|all}
routing:
  default_host: claude-code
  roles:
    backend:  omnigent       # runtime host
    qa:       gemini-cli     # independent verifier
    security: claude-code    # native hooks
  stages:
    stage-08: claude-code    # deploy policy
pipeline:
  default_track: full
```

::right::

<div class="routing-facts">
  <div class="fact">
    <div class="fact-title">Stage beats role beats default</div>
    <div class="fact-body">Routing is deterministic. No ambiguity at dispatch time.</div>
  </div>
  <div class="fact">
    <div class="fact-title">Models connect through gate JSON</div>
    <div class="fact-body">Models never share a context window, each model reads the prior gate file on disk. That's it. That's why multi-host works.</div>
  </div>
  <div class="fact">
    <div class="fact-title">Adding a new host</div>
    <div class="fact-body">One directory under <code>hosts/</code>, implementing the host-adapter contract. Omnigent and <code>openai-compat</code> were both added without changing gate schemas.</div>
  </div>
  <div class="fact">
    <div class="fact-title">Works today</div>
    <div class="fact-body">Claude Code · Codex · Gemini CLI · Omnigent · openai-compat (<u>experimental</u>: Fuel iX, OpenRouter, Fireworks AI, DS4, GLM, Kimi, …) · generic (manual)</div>
  </div>
  <div class="fact fact-cross">
    <div class="fact-title">Cross-model review</div>
    <div class="fact-body">Route build and review to different hosts when independent review matters. Different host CLI, different context window, different blind spots.</div>
  </div>
</div>

<style>
.slidev-layout { padding: 30px 40px 50px 40px; column-gap: 28px; }
h1 { color: #4B286D; margin-bottom: 0.5em; font-size: 1.3em; }
.routing-facts { display: flex; flex-direction: column; gap: 14px; padding-top: 0.3em; }
.fact { border-left: 3px solid #4B286D; padding: 6px 12px; background: #FAF8FD; border-radius: 0 4px 4px 0; }
.fact-cross { border-left-color: #2B8000; background: #EBF5EB; }
.fact-cross .fact-title { color: #2B8000; }
.fact-title { font-weight: bold; color: #4B286D; font-size: 0.85em; margin-bottom: 3px; }
.fact-body { color: #2C2E30; font-size: 0.8em; line-height: 1.5; }
code { background: #F4F4F7; padding: 0.1em 0.3em; border-radius: 3px; font-size: 0.88em; color: #4B286D; }
</style>

<!--
Walk the YAML click regions:

Click 1 — default_host: "Any workstream not explicitly routed falls through to here."
Click 2 — roles: "These are policy choices, not universal model rankings. Teams can route by approved tools, availability, cost policy, or measured performance evidence. Omnigent can own the harness/session runtime for a workstream while Stagecraft still owns the ordered stage, gate path, write audit, and next-step decision."
Click 3 — stage override: "Stage overrides beat role overrides. Here, deploy uses a host selected by stage policy; the runbook itself remains host-neutral. One line of config."

Right column: "The core never invokes a model. Model-specific behavior stays inside the host adapter. The contract between hosts is structured JSON on disk."
-->
