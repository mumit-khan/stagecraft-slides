---
layout: default
transition: slide-left
---

# Where Stagecraft sits in the AI coding landscape

<p class="as-of">Directional comparison · validate against current vendor docs before external use · June 2026</p>

<div class="comp-table-wrap">
<table class="comp-table">
  <thead>
    <tr>
      <th>Tool</th>
      <th>Design center</th>
      <th>Mechanical gating</th>
      <th>Post-build depth</th>
      <th>Multi-host</th>
    </tr>
  </thead>
  <tbody>
    <tr class="hl">
      <td><strong>Stagecraft</strong></td>
      <td>Process + gate control</td>
      <td>✅ Schema validator + hook enforcement</td>
      <td>✅ review, red team, QA, deploy, retro</td>
      <td>✅ Per-role + per-stage routing</td>
    </tr>
    <tr class="near">
      <td><strong>Omnigent</strong></td>
      <td>Agent runtime + meta-harness</td>
      <td>✅ ALLOW / DENY / ASK action policies</td>
      <td>⚠ Workflow-defined; Polly plans, builds, reviews</td>
      <td>✅ Per-agent harness + model</td>
    </tr>
    <tr>
      <td>AI-DLC</td>
      <td>Adaptive delivery methodology</td>
      <td>⚠ Evaluator + human approvals</td>
      <td>✅ Construction + Operations</td>
      <td>⚠ Rules for multiple coding agents</td>
    </tr>
    <tr>
      <td>BMAD</td>
      <td>Persona / workflow</td>
      <td>⚠ Workflow-guided</td>
      <td>⚠ Method-dependent</td>
      <td>⚠ Installs into multiple tools</td>
    </tr>
    <tr>
      <td>GitHub Spec Kit</td>
      <td>Spec → plan → tasks → implement</td>
      <td>⚠ Checklists + extensions</td>
      <td>⚠ Core ends at implement; extensions can add gates</td>
      <td>⚠ 30 integrations</td>
    </tr>
    <tr>
      <td>Kiro</td>
      <td>Integrated IDE + CLI + web</td>
      <td>⚠ Hooks + agent workflow</td>
      <td>⚠ Agent/hook dependent</td>
      <td>❌ Native Kiro surfaces only</td>
    </tr>
  </tbody>
</table>
</div>

<div class="closest"><strong>Closest overlap:</strong> multi-host execution and policy enforcement. <strong>Boundary:</strong> Omnigent governs agent sessions; Stagecraft governs an ordered SDLC and its evidence.</div>
<div class="sources">Source map: Stagecraft <code>docs/comparative-analysis.md</code> · first-party comparator docs reviewed 2026-06-22</div>

<style>
.slidev-layout { padding: 25px 50px 45px 50px; }
h1 { color: #4B286D; margin-bottom: 0.5em; font-size: 1.3em; }
.as-of { color: #676E73; font-size: 0.62em; margin: -0.45em 0 0.45em; }
.comp-table-wrap { overflow: hidden; }
.comp-table { width: 100%; border-collapse: collapse; font-size: 0.72em; }
.comp-table th { background: #4B286D; color: #FFFFFF; padding: 7px 10px; text-align: left; }
.comp-table td { padding: 5px 10px; color: #2C2E30; border-bottom: 1px solid #E3E6E8; }
.comp-table tr.hl { background: #F0EBF5 !important; }
.comp-table tr.hl td { color: #2C2E30; }
.comp-table tr.hl td:first-child { color: #4B286D; font-weight: bold; }
.comp-table tr.near { background: #F5FAF2; }
.comp-table tr.near td:first-child { color: #2B8000; }
.comp-table strong { color: #4B286D; }
.closest { margin-top: 9px; padding: 7px 10px; background: #F0EBF5; border-left: 3px solid #4B286D; color: #2C2E30; font-size: 0.67em; line-height: 1.4; }
.closest strong { color: #4B286D; }
.sources { margin-top: 5px; color: #676E73; font-size: 0.56em; }
.sources a { color: #4B286D; text-decoration: underline; }
</style>

<!--
"The useful distinction across these tools is the source of operational truth and post-build depth."

"Stagecraft's distinctive combination is mechanical gate enforcement, heterogeneous host routing, and post-build depth through deploy and retro."

"Concrete differences:
- vs Omnigent: this is the closest overlap. Omnigent is a broad agent runtime and collaboration control plane: multiple harnesses, cross-vendor review, action policies, OS sandboxes, cloud hosts, and shared sessions. Stagecraft is narrower and more opinionated: its source of truth is the ordered SDLC, schema-validated gates, delivery artifacts, and tamper-evident evidence chain. An Omnigent adapter could make the products complementary.
- vs AI-DLC: the closest methodological comparator. AI-DLC is broader as an organization-oriented methodology and evaluator; Stagecraft is more executable as a local delivery control plane.
- vs Spec Kit: its core process ends at implementation, while current extensions and workflows can add governance and gates. Stagecraft makes post-build controls part of the core contract.
- vs BMAD: BMAD is stronger at conversational product shaping. Stagecraft wins on deterministic execution — you can't argue your way past a gate validator.
- vs Kiro: Kiro spans IDE, CLI, and web. Stagecraft can compose with it as a host rather than imitate the integrated environment."

"The highlighted row is us. Stagecraft's row is verifiable against the codebase. Revalidate competitor rows against current vendor documentation before presenting externally."
-->
