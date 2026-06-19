---
layout: default
transition: slide-left
---

# `devteam run`: bounded autonomous driver

<div class="loop-container">
  <div class="loop-track">
    <div class="loop-node lp">devteam run</div>
    <div class="loop-arrow">→</div>
    <div class="loop-node lp">next?</div>
    <div class="loop-arrow">→</div>
    <div class="loop-node lp">dispatch<br><small>host CLI</small></div>
    <div class="loop-arrow">→</div>
    <div class="loop-node lp">gate</div>
    <div class="loop-back">↩ PASS / WARN: auto-advance to next stage</div>
  </div>

  <div class="outcome-grid">
    <div class="outcome-card retry">
      <div class="oc-icon">↺</div>
      <div class="oc-body"><strong>code-defect FAIL</strong><br>auto-retry, bounded by max_retries</div>
    </div>
    <div class="outcome-card halt">
      <div class="oc-icon">⚠</div>
      <div class="oc-body"><strong>ESCALATE</strong><br>halt: ruling required from human</div>
    </div>
    <div class="outcome-card halt">
      <div class="oc-icon">⚠</div>
      <div class="oc-body"><strong>external-blocked</strong><br>halt: blocked on external dependency</div>
    </div>
    <div class="outcome-card done">
      <div class="oc-icon">🎉</div>
      <div class="oc-body"><strong>pipeline-complete</strong><br>commit artifacts, sign-off gate written</div>
    </div>
    <div class="outcome-card stop">
      <div class="oc-icon">⏸</div>
      <div class="oc-body"><strong>budget / --until</strong><br>clean stop, state preserved and resumable</div>
    </div>
    <div class="outcome-card note-card">
      <div class="oc-body">Not a <code>while true</code>. Bounded:<br><strong>max_retries · --budget-usd · --until</strong><br>Every decision in an append-only run log.</div>
    </div>
  </div>
</div>

<div class="legend-row">
  <span class="leg leg-loop">🟣 Auto-advance (loop)</span>
  <span class="leg leg-retry">🟠 Auto-retry (bounded)</span>
  <span class="leg leg-halt">🔴 Halt: human required</span>
  <span class="leg leg-done">🟢 Success</span>
  <span class="leg leg-stop">⚫ Bounded stop</span>
</div>

<style>
.slidev-layout {
  padding: 25px 50px 40px 50px;
  display: flex;
  flex-direction: column;
}
h1 { color: #4B286D; margin-bottom: 0.6em; font-size: 1.3em; flex-shrink: 0; }
.loop-container { display: flex; flex-direction: column; gap: 18px; }
.loop-track {
  display: flex;
  align-items: center;
  gap: 0;
  background: #F4F4F7;
  border-radius: 10px;
  padding: 16px 20px;
  flex-wrap: wrap;
  gap: 8px;
}
.loop-node {
  background: #4B286D;
  color: #fff;
  border-radius: 8px;
  padding: 8px 16px;
  font-size: 0.85em;
  font-weight: 600;
  text-align: center;
  line-height: 1.3;
}
.loop-node small { font-size: 0.8em; opacity: 0.85; font-weight: 400; }
.loop-arrow { color: #4B286D; font-size: 1.3em; font-weight: bold; margin: 0 2px; }
.loop-back {
  margin-left: auto;
  background: #EBF5EB;
  color: #2B8000;
  border-radius: 6px;
  padding: 6px 14px;
  font-size: 0.78em;
  font-weight: 600;
  white-space: nowrap;
}
.outcome-grid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 10px;
}
.outcome-card {
  display: flex;
  align-items: flex-start;
  gap: 10px;
  border-radius: 8px;
  padding: 12px 14px;
  font-size: 0.78em;
  line-height: 1.4;
}
.oc-icon { font-size: 1.3em; flex-shrink: 0; margin-top: 1px; }
.oc-body { color: #2C2E30; }
.oc-body strong { display: block; margin-bottom: 2px; }
.retry { background: #FFF3E0; border-left: 3px solid #E07C00; }
.retry .oc-body strong { color: #E07C00; }
.halt { background: #FDECEA; border-left: 3px solid #E5342A; }
.halt .oc-body strong { color: #E5342A; }
.done { background: #EBF5EB; border-left: 3px solid #2B8000; }
.done .oc-body strong { color: #2B8000; }
.stop { background: #F4F4F7; border-left: 3px solid #676E73; }
.stop .oc-body strong { color: #676E73; }
.note-card { background: #F0EBF5; border-left: 3px solid #4B286D; }
.note-card .oc-body { color: #4B286D; }
.note-card .oc-body strong { color: #4B286D; }
code { background: #fff; padding: 0.1em 0.3em; border-radius: 3px; font-size: 0.9em; }
.loop-container { flex: 1; display: flex; flex-direction: column; gap: 18px; }
.legend-row {
  display: flex;
  gap: 14px;
  flex-wrap: wrap;
  margin-top: auto;
  flex-shrink: 0;
}
.leg { font-size: 0.68em; font-weight: 600; padding: 3px 10px; border-radius: 12px; }
.leg-loop  { background: #F0EBF5; color: #4B286D; }
.leg-retry { background: #FFF3E0; color: #E07C00; }
.leg-halt  { background: #FDECEA; color: #E5342A; }
.leg-done  { background: #EBF5EB; color: #2B8000; }
.leg-stop  { background: #F4F4F7; color: #676E73; }
</style>

<!--
Walk the loop track at the top first.

"devteam run loops: next → dispatch → gate → advance or handle. PASS/WARN advances automatically — no human in the loop."

"FAIL has two flavors. code-defect FAIL clears the gate, propagates the blocker, retries — bounded by max_retries. external-blocked means the pipeline waits for a human."

"ESCALATE is for judgment calls the system can't make — it halts and prompts you with devteam ruling --topic '...'. You make the call, pipeline resumes."

"Budget ceiling and --until give you a clean stop. State is preserved. Resume from exactly where it stopped."

"This is not `while true`. The autonomy is explicit: max_retries, --budget-usd X, --until <stage>. Every decision is recorded in an append-only run log."
-->
