---
layout: default
transition: slide-left
---

# The origin story

The third iteration—not the third wrapper

<div class="lineage">
  <div class="lineage-step">
    <div class="step-num">01</div>
    <div class="step-name">claude-dev-team</div>
    <div class="step-body">Proved a complete role-based delivery pipeline inside Claude Code.</div>
    <div class="step-link">github.com/mumit/claude-dev-team</div>
  </div>

  <div class="lineage-arrow">→</div>

  <div class="lineage-step">
    <div class="step-num">02</div>
    <div class="step-name">codex-dev-team</div>
    <div class="step-body">Rebuilt the method with Codex-native skills, scripts, JSON gates, and worktrees.</div>
    <div class="step-link">github.com/mumit/codex-dev-team</div>
  </div>

  <div class="lineage-arrow">→</div>

  <div class="lineage-step current">
    <div class="step-num">03</div>
    <div class="step-name">Stagecraft</div>
    <div class="step-body">Extracted stages, roles, artifacts, gates, routing, authority, and evidence into one host-neutral core.</div>
    <div class="step-link">github.com/telus-labs/stagecraft</div>
  </div>
</div>

<div class="lineage-callout">
  Building the system twice revealed the durable product: <strong>the delivery contract, not the host-specific files.</strong>
</div>

<style>
.slidev-layout { padding: 35px 50px 55px 50px; display: flex; flex-direction: column; }
h1 { color: #4B286D; margin-bottom: 0.8em; font-size: 1.5em; }
.lineage { display: grid; grid-template-columns: 1fr 42px 1fr 42px 1fr; align-items: stretch; gap: 8px; }
.lineage-step { background: #F4F4F7; border-top: 4px solid #9B7BB8; border-radius: 7px; padding: 18px 16px 15px; min-height: 190px; display: flex; flex-direction: column; }
.lineage-step.current { background: #F0EBF5; border-top-color: #4B286D; }
.step-num { color: #9B7BB8; font-size: 0.72em; font-weight: 700; letter-spacing: 0.08em; }
.step-name { color: #4B286D; font-size: 1.05em; font-weight: 700; margin-top: 8px; }
.step-body { color: #2C2E30; font-size: 0.82em; line-height: 1.5; margin-top: 12px; }
.step-link { color: #676E73; font-family: 'Fira Code', monospace; font-size: 0.58em; margin-top: auto; overflow-wrap: anywhere; }
.lineage-arrow { display: flex; align-items: center; justify-content: center; color: #9B7BB8; font-size: 1.6em; font-weight: 700; }
.lineage-callout { margin-top: 22px; background: #EBF5EB; border-left: 4px solid #2B8000; border-radius: 0 6px 6px 0; padding: 12px 16px; color: #2C2E30; font-size: 0.9em; line-height: 1.5; }
.lineage-callout strong { color: #2B8000; }
</style>

<!--
This is the origin story in one minute.

"Stagecraft did not begin model-agnostic. claude-dev-team proved that a role-based, gated software team could work deeply inside Claude Code. codex-dev-team rebuilt the same method around Codex-native primitives."

"Maintaining both made the real abstraction obvious. The product was not the installed prompts or host-specific files. It was the ordered stages, artifacts, gates, authority boundaries, and evidence. Stagecraft owns that contract once and lets adapters preserve each host's native experience."

Land on: "Stagecraft is the third iteration, not the third wrapper."
-->
