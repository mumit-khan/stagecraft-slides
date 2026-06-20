---
layout: default
transition: slide-left
---

# Where Stagecraft sits in the AI coding landscape

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
    <tr>
      <td>Copilot Workspace</td>
      <td>Spec → plan → implement</td>
      <td>❌ No gate enforcement</td>
      <td>❌ Core ends at implementation</td>
      <td>❌ GitHub Copilot only</td>
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
      <td>❌ Core ends at implement</td>
      <td>⚠ 30 integrations</td>
    </tr>
    <tr>
      <td>Kiro</td>
      <td>Integrated IDE + cloud</td>
      <td>⚠ Hooks + agent workflow</td>
      <td>⚠ Agent/hook dependent</td>
      <td>❌ Native Kiro surfaces only</td>
    </tr>
    <tr>
      <td>Agent OS</td>
      <td>Standards context</td>
      <td>❌ Not its focus</td>
      <td>❌ Outside scope</td>
      <td>⚠ Works alongside agents</td>
    </tr>
  </tbody>
</table>
</div>

<style>
.slidev-layout { padding: 25px 50px 45px 50px; }
h1 { color: #4B286D; margin-bottom: 0.5em; font-size: 1.3em; }
.comp-table-wrap { overflow: hidden; }
.comp-table { width: 100%; border-collapse: collapse; font-size: 0.72em; }
.comp-table th { background: #4B286D; color: #FFFFFF; padding: 7px 10px; text-align: left; }
.comp-table td { padding: 5px 10px; color: #2C2E30; border-bottom: 1px solid #E3E6E8; }
.comp-table tr.hl { background: #F0EBF5 !important; }
.comp-table tr.hl td { color: #2C2E30; }
.comp-table tr.hl td:first-child { color: #4B286D; font-weight: bold; }
.comp-table strong { color: #4B286D; }
</style>

<!--
"The useful distinction across these tools is the source of operational truth and post-build depth."

"Stagecraft is the only one that combines: mechanical gate enforcement (not just checklists), heterogeneous multi-host routing, AND full post-build depth through deploy and retro."

"Concrete differences:
- vs Copilot Workspace: Workspace takes a task and generates a plan + implementation. Ends there. No review, no red team, no deploy — and gates are a checklist you tick, not a validator that blocks.
- vs Spec Kit: Spec Kit ends at implementation. Stagecraft runs review, red team, QA, deploy.
- vs BMAD: BMAD is stronger at conversational product shaping. Stagecraft wins on deterministic execution — you can't argue your way past a gate validator.
- vs Kiro: Kiro is an integrated IDE environment. Stagecraft can compose with Kiro as a host.
- vs Agent OS: Standards context only, no pipeline structure."

"The highlighted row is us. Every ✅ is verifiable against the codebase — not marketing copy."
-->
