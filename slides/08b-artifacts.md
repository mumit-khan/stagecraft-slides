---
layout: default
transition: fade
---

# What lands on disk after a pipeline run

<div class="artifacts-wrap">

<div class="art-col">
<div class="art-heading">Filesystem after stage-04</div>

```
pipeline/
├── brief.md              ← stage-01 output
├── design-spec.md        ← stage-02 output
├── spec.feature          ← stage-03b executable spec
└── gates/
    ├── stage-01.json     PASS  Brief
    ├── stage-02.json     PASS  Design
    ├── stage-03.json     PASS  Clarification
    ├── stage-03b.json    PASS  Executable spec
    └── stage-04.json     PASS  Build (4 workstreams)
```

</div>

<div class="art-col">
<div class="art-heading">devteam next output</div>

```bash
$ devteam next

  gate stage-04: PASS
    backend   ✅  codex
    frontend  ✅  claude-code
    platform  ⚠   claude-code  (1 warning)
    qa        ✅  claude-code

▶ run-stage pre-review  (stage-04a)
```

</div>

</div>

<div class="note-bar note-resume">
  Gates reconstruct completed stage progression. Autonomous runs additionally preserve bounded resume, retry, budget, and authority state in <code>run-state.json</code> and the append-only run log.
</div>
<div class="note-bar note-report">
  After a complete run: <code>devteam report</code> opens a self-contained HTML summary — per-stage timing, workstream breakdown, all artifacts (brief, spec, code reviews, test report) embedded inline. No service. Share the file or open it in CI.
</div>

<style>
.slidev-layout { padding: 25px 50px 45px 50px; display: flex; flex-direction: column; }
h1 { color: #4B286D; margin-bottom: 0.5em; font-size: 1.3em; flex-shrink: 0; }
.artifacts-wrap { display: grid; grid-template-columns: 1fr 1fr; gap: 24px; flex: 1; align-content: start; }
.art-col { display: flex; flex-direction: column; gap: 8px; }
.art-heading { font-size: 0.72em; font-weight: 700; color: #9B7BB8; text-transform: uppercase; letter-spacing: 0.06em; }
.note-bar {
  border-left: 4px solid;
  padding: 10px 16px;
  border-radius: 0 6px 6px 0;
  color: #2C2E30;
  font-size: 0.78em;
  flex-shrink: 0;
}
.note-resume {
  background: #F0EBF5;
  border-color: #4B286D;
  margin-top: auto;
}
.note-report {
  background: #EBF5EB;
  border-color: #2B8000;
  margin-top: 6px;
}
code { background: #F4F4F7; padding: 0.1em 0.3em; border-radius: 3px; font-size: 0.85em; color: #2C2E30; }
</style>

<!--
Point at three things:

1. "Every artifact has a filename you can cat. brief.md, design-spec.md, the gate files — no database, no service, just files in a directory. Any CI system can read them."

2. "devteam next reads the gate chain and tells you exactly what runs next. Here, build is followed by the mechanically stamped pre-review stage."

3. "That warning on platform workstream: it doesn't block progress — it's recorded. You can inspect the gate to see exactly what the model flagged."

4. "devteam report at the end: opens a browser tab. Three tabs — Summary (status badge, AC count), Pipeline (per-stage timing and dispatch counts), Documents (every artifact embedded). Self-contained HTML, no server."

Transition: "That loop — gate → next → run — is what devteam run automates."
-->
