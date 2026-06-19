---
layout: default
transition: fade
---

# Gates live on disk — auditable, portable, version-controlled

`devteam` renders the prompt. Your AI tool runs it. The model writes this file back.

```json {1-5|6-7|8-14|all}
{
  "stage": "stage-04",
  "status": "PASS",
  "track": "full",
  "timestamp": "2026-05-28T14:32:11Z",
  "blockers": [],
  "warnings": [],
  "workstreams": [
    { "workstream": "backend",  "host": "codex",       "status": "PASS" },
    { "workstream": "frontend", "host": "claude-code", "status": "PASS" },
    { "workstream": "platform", "host": "claude-code", "status": "WARN",
      "warnings": ["runbook references stale endpoint"] },
    { "workstream": "qa",       "host": "claude-code", "status": "PASS" }
  ]
}
```

<style>
.slidev-layout { padding: 40px 60px 60px 60px; }
h1 { color: #4B286D; margin-bottom: 0.6em; }
p, li { color: #2C2E30; line-height: 1.6; }
</style>

<!--
Don't read the JSON. Point at three regions, one click each:

Click 1 — Identity: "Every gate carries the same envelope: stage, status, track, timestamp. Audit a deploy six months from now and you know exactly what produced this artifact."

Click 2 — Blockers/warnings: "If status is FAIL, blockers must be non-empty — the validator enforces it. Warnings are informational; they don't block."

Click 3 — Workstreams: "Build is multi-role. Backend ran on Codex, the others on Claude Code. Each wrote its own gate; the orchestrator merged them. Aggregate status is pessimistic: any FAIL gives merged FAIL."

Final click — all highlighted: "The orchestrator stores no state outside these files. The pipeline is reconstructable from pipeline/gates/ alone."

Then: "Let me show you a real one." → switch to terminal.
-->
