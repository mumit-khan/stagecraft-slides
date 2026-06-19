---
layout: default
transition: slide-left
---

# You make 3 decisions. The framework handles the rest.

<div class="decisions">
  <div class="decision">
    <div class="num">01</div>
    <div class="body">
      <div class="title">At the start</div>
      <div class="desc">Choose a track. Write one paragraph. That's your brief.</div>
    </div>
  </div>
  <div class="decision">
    <div class="num">02</div>
    <div class="body">
      <div class="title">At escalations</div>
      <div class="desc">Pipeline halts and waits. Nothing moves without your call. Dispatch with <code>devteam ruling --topic "..."</code></div>
    </div>
  </div>
  <div class="decision">
    <div class="num">03</div>
    <div class="body">
      <div class="title">At the end</div>
      <div class="desc">Review the output. Accept or reject. <code>pipeline-complete</code> is verifiable: gates on disk, chain tamper-evident.</div>
    </div>
  </div>
</div>

<div class="callout">
  Between decisions: the orchestrator dispatches, collects gates, auto-retries code-defect failures, and advances. <strong>5–10 min of active decisions over 30–60 min wall-clock.</strong>
</div>

<style>
.slidev-layout { padding: 30px 60px 55px 60px; }
h1 { color: #4B286D; margin-bottom: 0.7em; }
.decisions { display: flex; flex-direction: column; gap: 16px; margin-bottom: 1em; }
.decision { display: flex; gap: 16px; align-items: flex-start; }
.num { font-size: 2em; font-weight: bold; color: #4B286D; opacity: 0.25; min-width: 50px; line-height: 1; }
.title { font-weight: bold; color: #4B286D; font-size: 1em; margin-bottom: 3px; }
.desc { color: #2C2E30; font-size: 0.88em; line-height: 1.5; }
.callout {
  background: #F0EBF5;
  border-left: 4px solid #4B286D;
  padding: 12px 16px;
  border-radius: 0 6px 6px 0;
  color: #2C2E30;
  font-size: 0.88em;
  line-height: 1.5;
}
.callout strong { color: #4B286D; }
code { background: #E8E0F0; padding: 0.1em 0.3em; border-radius: 3px; font-size: 0.88em; color: #4B286D; }
</style>

<!--
Land on the callout — it's the key value proposition for tech leads.

"You don't write boilerplate, shuffle files between agents, track who reviewed what, or compute aggregate status. You decide what to build, whether each gate is good enough, and what to do when the pipeline halts. That's it."

This is the answer to 'why not just prompt Claude yourself?'
-->
