---
layout: default
transition: fade
---

# The 18-stage full track: contract → build → verify → ship

<div class="pipeline-wrap">

  <div class="pipe-row">
    <div class="phase-tag">Contract</div>
    <div class="pipe-stages">
      <div class="stage s-std"><span class="ico">📋</span><b>Brief</b><span class="sn">01</span></div>
      <div class="sarr">→</div>
      <div class="stage s-std"><span class="ico">🏗</span><b>Design</b><span class="sn">02</span></div>
      <div class="sarr">→</div>
      <div class="stage s-std"><span class="ico">❓</span><b>Clarify</b><span class="sn">03</span></div>
      <div class="sarr">→</div>
      <div class="stage s-std"><span class="ico">📝</span><b>Exec Spec</b><span class="sn">03b</span></div>
    </div>
  </div>

  <div class="pipe-bridge">
    <div class="pb-space"></div>
    <div class="pb-curve"></div>
    <div class="pb-arrow">▼</div>
  </div>

  <div class="pipe-row">
    <div class="phase-tag">Build &amp;<br>Review</div>
    <div class="pipe-stages">
      <div class="stage s-std"><span class="ico">⚙️</span><b>Build ×4</b><span class="sn">04</span></div>
      <div class="sarr">→</div>
      <div class="stage s-std"><span class="ico">✔</span><b>Pre-review</b><span class="sn">04a</span></div>
      <div class="sarr sarr-veto">→</div>
      <div class="stage s-veto"><span class="ico">🔴</span><b>Security</b><span class="sn">04b</span></div>
      <div class="sarr sarr-veto">→</div>
      <div class="stage s-veto"><span class="ico">🔴</span><b>Red Team</b><span class="sn">04c</span></div>
      <div class="sarr sarr-veto">→</div>
      <div class="stage s-veto"><span class="ico">🔴</span><b>Migration</b><span class="sn">04d</span></div>
      <div class="sarr">→</div>
      <div class="stage s-std"><span class="ico">🔍</span><b>Peer ×4</b><span class="sn">05</span></div>
    </div>
  </div>

  <div class="pipe-bridge">
    <div class="pb-space"></div>
    <div class="pb-curve"></div>
    <div class="pb-arrow">▼</div>
  </div>

  <div class="pipe-row">
    <div class="phase-tag">Verify &amp;<br>Ship</div>
    <div class="pipe-stages">
      <div class="stage s-std"><span class="ico">✅</span><b>QA</b><span class="sn">06</span></div>
      <div class="sarr">→</div>
      <div class="stage s-std"><span class="ico">🛡</span><b>Quality Gates</b><span class="sn">06b–06e</span></div>
      <div class="sarr sarr-green">→</div>
      <div class="stage s-green"><span class="ico">✍️</span><b>Sign-off</b><span class="sn">07</span></div>
      <div class="sarr sarr-green">→</div>
      <div class="stage s-green"><span class="ico">🚀</span><b>Deploy</b><span class="sn">08</span></div>
      <div class="sarr">→</div>
      <div class="stage s-std"><span class="ico">🎭</span><b>Retro</b><span class="sn">09</span></div>
    </div>
  </div>

</div>

<div class="legend-row">
  <span class="chip chip-purple">■ Standard stages</span>
  <span class="chip chip-veto">■ Veto power: peer-review cannot override</span>
  <span class="chip chip-green">■ Consequence boundary: explicit authority may be required</span>
</div>

<style>
.slidev-layout {
  padding: 25px 50px 45px 50px;
  display: flex;
  flex-direction: column;
}
h1 { color: #4B286D; margin-bottom: 0.5em; font-size: 1.3em; flex-shrink: 0; }

.pipeline-wrap {
  display: flex;
  flex-direction: column;
  flex: 1;
  justify-content: center;
  gap: 0;
}

/* Phase row */
.pipe-row {
  display: flex;
  align-items: stretch;
  gap: 0;
}
.phase-tag {
  width: 72px;
  min-width: 72px;
  font-size: 0.62em;
  font-weight: 700;
  color: #9B7BB8;
  text-transform: uppercase;
  letter-spacing: 0.06em;
  line-height: 1.3;
  padding-right: 10px;
  display: flex;
  align-items: center;
  flex-shrink: 0;
}
.pipe-stages {
  flex: 1;
  display: flex;
  align-items: stretch;
  gap: 0;
}

/* Stage boxes */
.stage {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 14px 6px;
  border-radius: 10px;
  text-align: center;
  line-height: 1.25;
  gap: 3px;
}
.ico { font-size: 1.3em; line-height: 1; }
.stage b { font-size: 0.78em; font-weight: 700; }
.sn { font-size: 0.62em; opacity: 0.7; }

.s-std  { background: #4B286D; color: #fff; }
.s-veto { background: #C41A10; color: #fff; }
.s-green { background: #2B8000; color: #fff; }

/* Stage arrows */
.sarr {
  display: flex;
  align-items: center;
  padding: 0 5px;
  font-size: 1.1em;
  color: #9B7BB8;
  flex-shrink: 0;
}
.sarr-veto  { color: #E5342A; }
.sarr-green { color: #2B8000; }

/* Serpentine bridge connector */
.pipe-bridge {
  display: flex;
  height: 52px;
  position: relative;
  align-items: stretch;
  padding-top: 8px;
  padding-bottom: 8px;
  box-sizing: border-box;
}
.pb-space {
  width: 72px;
  flex-shrink: 0;
}
.pb-curve {
  flex: 1;
  border-right: 2.5px solid #C8A8E8;
  border-bottom: 2.5px solid #C8A8E8;
  border-bottom-right-radius: 20px;
}
.pb-arrow {
  position: absolute;
  left: 72px;
  bottom: 4px;
  color: #9B7BB8;
  font-size: 13px;
  line-height: 1;
}

/* Legend — flush bottom */
.legend-row {
  display: flex;
  gap: 20px;
  font-size: 0.72em;
  flex-wrap: wrap;
  margin-top: 10px;
  flex-shrink: 0;
}
.chip { padding: 3px 10px; border-radius: 4px; font-weight: 500; }
.chip-purple { background: #F0EBF5; color: #4B286D; }
.chip-veto   { background: #FDECEA; color: #C41A10; }
.chip-green  { background: #EBF5EB; color: #2B8000; }
</style>

<!--
Walk row by row — 45 seconds.

"The contract is explicit before implementation: brief, design, clarification, executable spec. Build then fans out to specialist workstreams."

"Pre-review decides whether security and migration gates apply; the full track also runs red team before peer review. Veto findings cannot be averaged away by reviewer consensus."

"After QA and the quality gates, sign-off comes before deploy. Consequence ceilings keep high-impact actions under explicit operator authority; retrospective closes the documentary loop."
-->
