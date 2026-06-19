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
├── feature-spec.md       ← stage-03a output
└── gates/
    ├── stage-01.json     PASS  Brief
    ├── stage-02.json     PASS  Design
    ├── stage-03a.json    PASS  Spec
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

▶ run-stage peer-review  (stage-05)
```

</div>

</div>

<div class="note-bar">
  Gate files are the only state the orchestrator reads. Shut down, come back in a week, <code>devteam next</code> picks up exactly here.
</div>

<style>
.slidev-layout { padding: 25px 50px 45px 50px; display: flex; flex-direction: column; }
h1 { color: #4B286D; margin-bottom: 0.5em; font-size: 1.3em; flex-shrink: 0; }
.artifacts-wrap { display: grid; grid-template-columns: 1fr 1fr; gap: 24px; flex: 1; align-content: start; }
.art-col { display: flex; flex-direction: column; gap: 8px; }
.art-heading { font-size: 0.72em; font-weight: 700; color: #9B7BB8; text-transform: uppercase; letter-spacing: 0.06em; }
.note-bar {
  background: #F0EBF5;
  border-left: 4px solid #4B286D;
  padding: 10px 16px;
  border-radius: 0 6px 6px 0;
  color: #2C2E30;
  font-size: 0.8em;
  margin-top: auto;
  flex-shrink: 0;
}
code { background: #F4F4F7; padding: 0.1em 0.3em; border-radius: 3px; font-size: 0.85em; color: #2C2E30; }
</style>

<!--
Point at two things:

1. "Every artifact has a filename you can cat. brief.md, design-spec.md, the gate files — no database, no service, just files in a directory. Any CI system can read them."

2. "devteam next reads the last gate and tells you exactly what runs next. In headless mode it runs it. In interactive mode you approve first."

3. "That warning on platform workstream: it doesn't block progress — it's recorded. You can inspect the gate to see exactly what the model flagged."

Transition: "That loop — gate → next → run — is what devteam run automates."
-->
