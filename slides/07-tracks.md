---
layout: default
transition: slide-left
---

# 6 tracks: right depth for the change type

<div class="track-grid">
  <div class="track track-full"><span class="track-name">full</span><span class="track-stages">Brief → Design → Build → Review → QA → Deploy → Retro</span></div>
  <div class="track track-quick"><span class="track-name">quick</span><span class="track-stages">Brief → Build → Review → QA → Deploy → Retro</span></div>
  <div class="track track-nano"><span class="track-name">nano</span><span class="track-stages">Build → Review → QA</span></div>
  <div class="track track-config"><span class="track-name">config-only</span><span class="track-stages">Build → Pre-review → conditional safety → QA → Sign-off → Deploy</span></div>
  <div class="track track-dep"><span class="track-name">dep-update</span><span class="track-stages">Build → Review → QA → Sign-off → Deploy</span></div>
  <div class="track track-hotfix"><span class="track-name">hotfix ⚡</span><span class="track-stages">Build → safety reviews → Peer → QA gates → Sign-off → Deploy → Retro</span></div>
</div>

<v-clicks>

- `devteam assess` **infers the right track** from description keywords + file heuristics
- `hotfix` skips upstream discovery but keeps red team, conditional safety, QA, and deploy controls
- lighter tracks are blocked for <span v-mark.box="3" style="color:#4B286D">auth · payments · migrations</span>; use `full` or the deliberate `hotfix` path

</v-clicks>

<style>
.slidev-layout { padding: 30px 50px 50px 50px; }
h1 { color: #4B286D; margin-bottom: 0.5em; font-size: 1.4em; }
.track-grid { display: flex; flex-direction: column; gap: 6px; margin-bottom: 0.6em; }
.track {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 6px 14px;
  border-radius: 6px;
  font-size: 0.82em;
}
.track-name {
  font-weight: bold;
  font-family: 'Fira Code', monospace;
  min-width: 90px;
  color: #fff;
}
.track-stages { color: #2C2E30; }
.track-full  { background: #4B286D; }
.track-full .track-stages { color: #D9C8F0; }
.track-quick { background: #613889; }
.track-quick .track-stages { color: #D9C8F0; }
.track-nano  { background: #7733BB; }
.track-nano .track-stages { color: #EDE0FA; }
.track-config { background: #F0EBF5; border: 1px solid #D9C8F0; }
.track-config .track-name { color: #4B286D; }
.track-dep   { background: #F0EBF5; border: 1px solid #D9C8F0; }
.track-dep .track-name { color: #4B286D; }
.track-hotfix { background: #FFF0EF; border: 2px solid #E5342A; }
.track-hotfix .track-name { color: #E5342A; }
p, li { color: #2C2E30; line-height: 1.5; margin-bottom: 0.35em; }
ul { margin-left: 1.2em; margin-bottom: 0.5em; }
code { background: #F4F4F7; padding: 0.1em 0.3em; border-radius: 3px; font-size: 0.9em; color: #4B286D; }
</style>

<!--
Walk the track rows top to bottom — 30 seconds.

"Full is end-to-end: all 18 stages. nano is just build, a single reviewer, and QA. Config-only still runs QA, sign-off, and deploy; it trims product discovery, not operational proof."

"Hotfix starts at build because the defect scope is already known. It still runs pre-review, red team, conditional security and migration checks, QA gates, sign-off, deploy, and retro."

"`devteam assess` runs heuristics on the description and changed files. Sensitive work is rejected on lighter tracks; full and hotfix are deliberate exceptions with deeper controls."

Transition: "Now — the mechanism that holds all of this together."
-->
