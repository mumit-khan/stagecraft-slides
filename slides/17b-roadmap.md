---
layout: default
transition: slide-left
---

# What's next

<div class="roadmap-grid">

<div class="roadmap-col">
<div class="col-head">Near-horizon · planned or evidence-gated</div>

<div class="roadmap-card purple">
  <div class="rcard-title">Cloud runner adapter</div>
  <div class="rcard-body">Route workstreams to AWS Lambda/Bedrock — long-running stages off the laptop. Local orchestrator retains full routing, gating, and state ownership.</div>
</div>

<div class="roadmap-card purple">
  <div class="rcard-title">Continuous adaptive routing</div>
  <div class="rcard-body">Auto-reroute the <em>next</em> run based on prior dispatch outcomes. D5 today proposes swaps; the mature form acts automatically — evidence-gated on ≥5 dispatches per (role, host) across ≥2 projects.</div>
</div>

<div class="roadmap-card purple">
  <div class="rcard-title">Recipe factory (H3)</div>
  <div class="rcard-body">Resolved escalations index as fix-recipes in the embedding store. Recurring derivable failures resolve deterministically — no escalation on second occurrence.</div>
</div>

<div class="roadmap-card green">
  <div class="rcard-title">API-direct adapter</div>
  <div class="rcard-body">No host CLI required — talk to Anthropic, OpenAI, or Google directly. Lighter footprint for restricted or cloud-native environments.</div>
</div>

</div>

<div class="roadmap-col">
<div class="col-head">Innovation bets · speculative</div>

<div class="roadmap-card orange">
  <div class="rcard-title">Conversational upstream stages</div>
  <div class="rcard-body"><code>devteam stage requirements --interactive</code> — Q&amp;A with the PM subagent refines the brief before it renders. Unlocks when five real teams report the gate loop is too rigid upstream.</div>
</div>

<div class="roadmap-card orange">
  <div class="rcard-title">Multi-modal stages</div>
  <div class="rcard-body">Design specs include architecture diagrams as images. Stage 2 and stage 5 accept image inputs; Principal can output a system diagram, not just prose. Visual reasoning inline.</div>
</div>

<div class="roadmap-card orange">
  <div class="rcard-title">Self-modifying pipeline</div>
  <div class="rcard-body">Retrospective stage proposes changes to <code>stages.js</code> / <code>roles/</code> / <code>rules/</code> based on what worked — queued for human approval. The pipeline learns its own shape from operation.</div>
</div>

</div>

</div>

<div class="posture-bar">
  <strong>Six positioning bets:</strong> models keep getting smarter · diversity beats monoculture · evals are the rate-limit · memory is the next frontier · tool depth beats raw intelligence · compliance is coming fast
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
  margin-top: 50px;
}
.posture-bar strong { color: #4B286D; }
</style>

<!--
Not a commitment list — each item has an explicit unlock condition.

Near-horizon:
- Cloud runner: the key shift is that a 2-hour red-team sweep or full test suite no longer blocks the dev's laptop. The local orchestrator still makes every routing, gating, and state decision — the remote worker receives only one rendered prompt and one bounded workspace snapshot.
- Adaptive routing (D5 maturation): Phase 17 made dispatch history durable during real runs. The gate opens when ≥5 dispatches per (role, host) pair land across ≥2 real projects. Until then D5 is still advisory (proposals, not automatic).
- H3 recipe factory: Phase 18 made explicit hash-bound acceptance measurable. The gate opens when ≥2 projects each show ≥5 autonomous fix/retry runs with the same failure accepted ≥3 times and ≥80% derivability. GitHub #142.
- API-direct: useful for regulated environments that can't install Claude Code — reduces the dependency footprint to just a network call.

Innovation bets:
- Conversational upstream: the pipeline loop is intentionally rigid for build/review/QA; for requirements it can feel premature to lock the brief before Q&A. E9 unlocks when five real teams report that. Discovery-gated at 2026-06-19.
- Multi-modal: stage 2 already writes prose design specs — the next step is attaching architecture diagrams that stage 5 (peer review) can reason about visually.
- Self-modifying pipeline (G9): premature until multiple teams run different configurations. The retrospective stage becomes the right vehicle once there's diversity of real operation to learn from.
-->
