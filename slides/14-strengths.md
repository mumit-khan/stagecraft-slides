---
layout: default
transition: slide-left
---

# 4 defensible strengths. All verifiable.

<div class="strength">
  <div class="num">01</div>
  <div class="body">
    <div class="title">Executable state contract</div>
    <div class="desc">Gate JSON drives deterministic next actions. <code>devteam verify</code> stamps what ran. Mechanical checks override model assertions. The model doesn't grade its own homework.</div>
  </div>
</div>

<div class="strength">
  <div class="num">02</div>
  <div class="body">
    <div class="title">Heterogeneous dispatch</div>
    <div class="desc">Roles in one run can use different host CLIs, including N-way review fanout. Models never share a context window. The interface is JSON on disk.</div>
  </div>
</div>

<div class="strength">
  <div class="num">03</div>
  <div class="body">
    <div class="title">Bounded autonomy with provenance</div>
    <div class="desc">Bounded by retries, scope gates, budget ceilings. Every decision recorded in an append-only run log. It won't self-modify its rules or extend its own grants.</div>
  </div>
</div>

<div class="strength">
  <div class="num">04</div>
  <div class="body">
    <div class="title">Full delivery depth</div>
    <div class="desc">Review, red team, a11y, observability, migration safety, deploy, retro: all first-class gates. Most spec-first tools end at implementation.</div>
  </div>
</div>

<style>
.slidev-layout { padding: 30px 60px 50px 60px; }
h1 { color: #4B286D; margin-bottom: 0.6em; }
.strength {
  display: flex;
  gap: 16px;
  margin-bottom: 14px;
  align-items: flex-start;
}
.num {
  font-size: 1.8em;
  font-weight: bold;
  color: #4B286D;
  opacity: 0.25;
  min-width: 48px;
  line-height: 1;
  margin-top: 2px;
}
.title { font-weight: bold; color: #4B286D; font-size: 0.95em; margin-bottom: 3px; }
.desc { color: #2C2E30; font-size: 0.82em; line-height: 1.55; }
code { background: #F0EBF5; padding: 0.1em 0.3em; border-radius: 3px; font-size: 0.9em; color: #4B286D; }
</style>

<!--
These survive adversarial questioning.

01: "Mechanical verification overrides model assertions. devteam verify runs the tests and stamps the gate — if 3 tests fail, the gate is FAIL regardless of what the model claimed."

02: "N-way review fanout can route reviewers to different hosts. They do not share a model context; structured artifacts and gates are the handoff."

03: "The autonomy is explicit. You know exactly what it will and won't do. It won't retry past the ceiling, self-modify rules, or extend its own grants."

04: "Most spec-first tools end at implementation. Stagecraft treats deploy, retro, and the full safety layer as first-class gates."
-->
