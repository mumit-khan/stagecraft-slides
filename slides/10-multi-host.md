---
layout: two-cols
transition: fade
---

# Right host per role. A small YAML routing block.

```yaml {1-2|3-6|7-8|all}
routing:
  default_host: claude-code
  roles:
    backend:  codex        # fast + cheap for bulk generation
    qa:       gemini-cli   # Gemini strong on adversarial tests
    security: claude-code  # nuanced security reasoning
  stages:
    stage-08: claude-code  # deploy runbook is CC-specific
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
    <div class="fact-body">Models never share a context window. Model A reads the prior gate file on disk. That's it. That's why multi-host works.</div>
  </div>
  <div class="fact">
    <div class="fact-title">Adding a new host</div>
    <div class="fact-body">One directory under <code>hosts/</code>, implementing the small host-adapter contract.</div>
  </div>
  <div class="fact">
    <div class="fact-title">Works today</div>
    <div class="fact-body">Claude Code · Codex · Gemini CLI · generic (no host, prompts for manual use)</div>
  </div>
  <div class="fact fact-cross">
    <div class="fact-title">Cross-model review</div>
    <div class="fact-body">Codex builds. Claude reviews. The model that wrote the code never grades its own work: different host CLI, different context window, different blind spots.</div>
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
Click 2 — roles: "Claude for design and review. Codex for backend bulk generation. Gemini for adversarial QA."
Click 3 — stage override: "Stage overrides beat role overrides. Deploy always runs on Claude Code because the runbook has CC-specific instructions. One line of config."

Right column: "The core never invokes a model. Model-specific behavior stays inside the host adapter. The contract between hosts is structured JSON on disk."
-->
