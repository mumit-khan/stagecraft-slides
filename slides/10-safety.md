---
layout: default
transition: slide-left
---

# Ten layers catch problems before merge

<div class="safety-table-wrap">
<table class="safety-table">
  <thead>
    <tr><th>Layer</th><th>What it catches</th></tr>
  </thead>
  <tbody>
    <tr><td>Per-role allowedWrites</td><td>Backend can't write <code>frontend/</code> — PreToolUse hook enforces</td></tr>
    <tr class="hl"><td><strong>Stoplist</strong></td><td><code>auth</code> · <code>payments</code> · <code>migrations</code> blocked on lighter tracks without <code>--force</code></td></tr>
    <tr><td>Secret scanning</td><td>Blocks writes of AWS / GitHub / Anthropic / Stripe credentials</td></tr>
    <tr class="hl"><td><strong>Security review</strong></td><td>Fires on sensitive paths — has <strong>veto power</strong></td></tr>
    <tr class="hl"><td><strong>Red team</strong></td><td>10 attack surfaces, always-on for full+hotfix — findings block peer-review</td></tr>
    <tr><td>Migration safety</td><td>Schema changes need a tested rollback — has <strong>veto power</strong></td></tr>
    <tr><td>Verification beyond tests</td><td>Property-based · mutation · formal — counterexamples block sign-off</td></tr>
    <tr><td>Accessibility audit</td><td>0 critical WCAG violations required</td></tr>
    <tr><td>Observability gate</td><td>Brief signals must appear in shipped code</td></tr>
    <tr><td>Spec drift detection</td><td>AC-N in brief ↔ spec.feature ↔ test row — <code>devteam spec verify</code></td></tr>
  </tbody>
</table>
</div>

<style>
.slidev-layout { padding: 40px 60px 60px 60px; }
h1 { color: #4B286D; margin-bottom: 0.5em; }
.safety-table-wrap { overflow: hidden; }
.safety-table { width: 100%; border-collapse: collapse; font-size: 0.78em; }
.safety-table th { background: #4B286D; color: #FFFFFF; padding: 7px 14px; text-align: left; }
.safety-table td { padding: 5px 14px; color: #2C2E30; border-bottom: 1px solid #E3E6E8; }
.safety-table tr.hl { background: #F0EBF5; }
.safety-table tr.hl td { color: #2C2E30; }
.safety-table strong { color: #4B286D; }
code { background: #F4F4F7; padding: 0.1em 0.3em; border-radius: 3px; font-size: 0.9em; color: #2C2E30; }
</style>

<!--
Don't read every row — fast pass.

Land on three (highlighted rows):

1. STOPLIST: "Phrases like auth, payments, migrations block the lighter tracks. You cannot run nano-track on a change that mentions 'add auth middleware'. The framework refuses. --force exists but you have to mean it."

2. VETO STAGES (security + migration): "Both have veto power. A migration without a tested rollback halts the pipeline regardless of any other approval. Peer-review consensus cannot override."

3. RED TEAM: "Always on for full and hotfix tracks. 10 attack surfaces. It must produce concrete reproducers, not just 'might be risky'. Findings block peer-review — not advisory."

Transition: "So — is this the right tool for your team?"
-->
