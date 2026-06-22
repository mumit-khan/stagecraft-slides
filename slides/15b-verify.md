---
layout: default
transition: fade
---

# Every claim here is verifiable in under 5 minutes

<div class="verify-list">

  <div class="verify-item">
    <div class="v-cmd"><code>npm test</code></div>
    <div class="v-result">Runs the full offline suite. The current output supplies the exact test total and exposes any failure.</div>
  </div>

  <div class="verify-item">
    <div class="v-cmd"><code>devteam verify-chain</code></div>
    <div class="v-result">Walks every gate's SHA-256 <code>prev_hash</code>. Exits non-zero if any link is missing or tampered. Wire it into CI in two lines.</div>
  </div>

  <div class="verify-item">
    <div class="v-cmd"><code>cat pipeline/gates/stage-04.json</code></div>
    <div class="v-result">Workstream status, host, timestamp, blockers, and warnings. Optional reproducibility fields appear when the host supplies them.</div>
  </div>

  <div class="verify-item">
    <div class="v-cmd"><code>devteam doctor</code></div>
    <div class="v-result">Checks the installed adapter, required files, host CLI, hooks where supported, and gate workspace. Non-green explains why.</div>
  </div>

</div>

<style>
.slidev-layout { padding: 28px 60px 50px 60px; display: flex; flex-direction: column; }
h1 { color: #4B286D; margin-bottom: 0.7em; font-size: 1.3em; flex-shrink: 0; }
.verify-list { display: flex; flex-direction: column; gap: 14px; flex: 1; justify-content: center; }
.verify-item {
  display: grid;
  grid-template-columns: 280px 1fr;
  align-items: center;
  gap: 0;
  background: #fff;
  border-radius: 8px;
  overflow: hidden;
  border: 1px solid #E3E6E8;
}
.v-cmd {
  background: #2C2E30;
  padding: 14px 18px;
  display: flex;
  align-items: center;
  align-self: stretch;
}
.v-cmd code {
  color: #66CC00;
  font-size: 0.85em;
  font-family: 'Fira Code', monospace;
  background: none;
  padding: 0;
}
.v-result {
  padding: 14px 18px;
  color: #2C2E30;
  font-size: 0.82em;
  line-height: 1.5;
}
.v-result code {
  background: #F0EBF5;
  color: #4B286D;
  padding: 0.1em 0.35em;
  border-radius: 3px;
  font-size: 0.9em;
}
</style>

<!--
This slide is the answer to "how do I know any of this is true?"

The format is deliberate — left side is a command, right side is what you'll see. The audience can copy any of these right now.

"You don't have to take my word for any of this. Clone the repo. Run these four commands. Everything I've said about mechanical gating, tamper-evidence, and audit completeness is observable from the terminal."

This is the slide that most directly addresses tech leadership skepticism. It reframes the conversation from "trust me" to "check it."
-->
