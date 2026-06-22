---
layout: default
transition: slide-left
---

# What's next

<div class="roadmap-grid">

<div class="roadmap-col">
<div class="col-head">Near-horizon · proposed or evidence-gated</div>

<div class="roadmap-card purple">
  <div class="rcard-title">Safe pipeline acceleration</div>
  <div class="rcard-body">Measure the critical path, reuse hash-bound verification receipts, run independent suites concurrently, and schedule review/audit waves without removing a gate.</div>
</div>

<div class="roadmap-card purple">
  <div class="rcard-title">Cloud runner adapter</div>
  <div class="rcard-body">A provider-neutral remote workstream worker for long audits and large test suites. Routing, validation, authority, gate stamping, and state remain local. Proposed; ADR required.</div>
</div>

<div class="roadmap-card purple">
  <div class="rcard-title">Continuous adaptive routing</div>
  <div class="rcard-body">Propose—and eventually apply—next-run host changes from durable dispatch evidence. Automatic action remains gated on cross-project sample depth.</div>
</div>

</div>

<div class="roadmap-col">
<div class="col-head">Evidence-gated extensions</div>

<div class="roadmap-card orange">
  <div class="rcard-title">Recipe factory</div>
  <div class="rcard-body">Turn repeatedly accepted, hash-bound resolutions into deterministic fix recipes. Reuse only after recurrence, derivability, and cross-project evidence thresholds are met.</div>
</div>

<div class="roadmap-card orange">
  <div class="rcard-title">Conversational upstream stages</div>
  <div class="rcard-body">Optional requirements Q&amp;A before the brief locks. Unlock only if real pilots show that the current upstream gate loop is too rigid.</div>
</div>

<div class="roadmap-card orange">
  <div class="rcard-title">Omnigent host adapter</div>
  <div class="rcard-body">Evaluate Omnigent as an execution runtime for harness choice, sandboxing, cloud workers, and collaboration—while Stagecraft retains stage progression, validation, and evidence ownership.</div>
</div>

</div>

</div>

<div class="posture-bar">
  <strong>Roadmap posture:</strong> Stagecraft stays the delivery and evidence plane; execution runtimes such as Omnigent can sit beneath it.
</div>

<style>
.slidev-layout { padding: 16px 46px 20px 46px; display: flex; flex-direction: column; }
h1 { color: #4B286D; margin-bottom: 0.35em; font-size: 1.3em; flex-shrink: 0; }
.roadmap-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
.roadmap-col { display: flex; flex-direction: column; gap: 4px; }
.col-head { font-size: 0.63em; font-weight: 700; color: #9B7BB8; text-transform: uppercase; letter-spacing: 0.06em; margin-bottom: 1px; }
.roadmap-card { border-radius: 6px; padding: 5px 10px; border-left: 3px solid transparent; }
.rcard-title { font-size: 0.76em; font-weight: 700; margin-bottom: 2px; }
.rcard-body { font-size: 0.66em; line-height: 1.4; color: #2C2E30; }
.purple { background: #F0EBF5; border-left-color: #4B286D; }
.purple .rcard-title { color: #4B286D; }
.green { background: #EBF5EB; border-left-color: #2B8000; }
.green .rcard-title { color: #2B8000; }
.orange { background: #FFF3E0; border-left-color: #E07C00; }
.orange .rcard-title { color: #E07C00; }
code { background: rgba(255,255,255,0.7); padding: 0.1em 0.3em; border-radius: 3px; font-size: 0.9em; color: #2C2E30; }
.posture-bar {
  background: #F0EBF5;
  border-left: 4px solid #4B286D;
  padding: 5px 12px;
  border-radius: 0 6px 6px 0;
  font-size: 0.65em;
  color: #4B286D;
  line-height: 1.5;
  flex-shrink: 0;
  margin-top: 32px;
}
.posture-bar strong { color: #4B286D; }
</style>

<!--
Not a commitment list. The cloud-runner and speed documents are proposed plans; evidence-gated capabilities keep explicit unlock conditions.

Near-horizon:
- Pipeline acceleration: measure first, then remove duplicate work and parallelize only stages or suites whose contracts are independent.
- Cloud runner: remote execution, not remote orchestration. The local process retains every routing, gating, authority, and state decision. The current Phase 21 plan is provider-neutral and requires an ADR before implementation.
- Adaptive routing: durable dispatch history exists; automatic rerouting remains evidence-gated and cross-project.

Evidence-gated extensions:
- Recipe factory: accepted resolutions become reusable only after recurrence and derivability thresholds are satisfied.
- Conversational upstream: useful only if pilots show requirements need dialogue before the gate is written.
- Omnigent adapter: investigate integration before duplicating its session, sandbox, cloud-host, and collaboration infrastructure. Stagecraft must remain the sole owner of routing authority, gate validation, and pipeline state.
-->
