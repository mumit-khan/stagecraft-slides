---
layout: default
transition: slide-left
---

# 10 layers catch problems before merge

<div class="safety-grid">

<div class="layer hook">
  <div class="layer-title">PreToolUse hooks</div>
  <div class="layer-body">Role-scoped allowedWrites: backend can't write <code>frontend/</code></div>
</div>

<div class="layer hook">
  <div class="layer-title">Secret scanning</div>
  <div class="layer-body">Blocks AWS / GitHub / Anthropic / Stripe credentials on write</div>
</div>

<div class="layer stoplist">
  <div class="layer-title">⛔ Stoplist</div>
  <div class="layer-body"><code>auth · payments · migrations</code>: blocked on lighter tracks without <code>--force</code></div>
</div>

<div class="layer veto">
  <div class="layer-title">🔴 Security review</div>
  <div class="layer-body">Fires on sensitive paths. Veto power: cannot be overridden</div>
</div>

<div class="layer veto">
  <div class="layer-title">🔴 Migration safety</div>
  <div class="layer-body">Schema changes need a tested rollback. Veto power.</div>
</div>

<div class="layer veto">
  <div class="layer-title">🔴 Red team</div>
  <div class="layer-body">10 attack surfaces, always-on for full + hotfix. Concrete reproducers required.</div>
</div>

<div class="layer gate">
  <div class="layer-title">Spec drift detection</div>
  <div class="layer-body">AC-N in brief ↔ spec.feature ↔ test row: <code>devteam consistency analyze</code></div>
</div>

<div class="layer gate">
  <div class="layer-title">Verification beyond tests</div>
  <div class="layer-body">Property-based · mutation · formal: counterexamples block sign-off</div>
</div>

<div class="layer gate">
  <div class="layer-title">Accessibility gate</div>
  <div class="layer-body">0 critical WCAG violations required</div>
</div>

<div class="layer gate">
  <div class="layer-title">Observability gate</div>
  <div class="layer-body">Brief signals must appear in shipped code, checked mechanically</div>
</div>

</div>

<div class="legend-row">
  <span class="leg leg-hook">🟣 Runtime hook</span>
  <span class="leg leg-veto">🔴 Veto / hard block</span>
  <span class="leg leg-gate">🟢 Quality gate</span>
</div>

<style>
.slidev-layout {
  padding: 20px 50px 40px 50px;
  display: flex;
  flex-direction: column;
}
h1 { color: #4B286D; margin-bottom: 0.5em; font-size: 1.35em; flex-shrink: 0; }
.safety-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 7px 20px;
  flex: 1;
  align-content: start;
}
.layer {
  border-left: 3px solid #E3E6E8;
  padding: 5px 10px;
  border-radius: 0 4px 4px 0;
  background: #FAFAFA;
}
.layer-title { font-size: 0.78em; font-weight: bold; color: #4B286D; }
.layer-body { font-size: 0.72em; color: #2C2E30; margin-top: 2px; line-height: 1.4; }
.veto { border-left-color: #E5342A; background: #FFF5F5; }
.veto .layer-title { color: #E5342A; }
.stoplist { border-left-color: #E5342A; background: #FFF5F5; }
.stoplist .layer-title { color: #E5342A; }
.hook { border-left-color: #7733BB; background: #F8F4FF; }
.hook .layer-title { color: #7733BB; }
.gate { border-left-color: #2B8000; background: #F0F8F0; }
.gate .layer-title { color: #2B8000; }
code { background: rgba(255,255,255,0.6); padding: 0.1em 0.3em; border-radius: 3px; font-size: 0.9em; color: #2C2E30; }
.legend-row {
  display: flex;
  gap: 16px;
  margin-top: auto;
  padding-top: 10px;
  flex-shrink: 0;
}
.leg { font-size: 0.72em; font-weight: 600; padding: 3px 12px; border-radius: 12px; }
.leg-hook { background: #F8F4FF; color: #7733BB; }
.leg-veto { background: #FFF5F5; color: #E5342A; }
.leg-gate { background: #F0F8F0; color: #2B8000; }
</style>

<!--
Fast pass — don't read every row. Land on three:

1. RED VETO (3 items): "These three cannot be overridden by peer-review consensus. A migration without a tested rollback halts the pipeline. Full stop."

2. STOPLIST: "The word 'auth' in your feature description forces full track. You can't run nano on an auth change. --force exists but you have to mean it."

3. RED TEAM: "Always on for full and hotfix. Must produce concrete reproducers — not 'might be risky'. Findings block peer-review, not advisory."
-->
