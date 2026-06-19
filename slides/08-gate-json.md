---
layout: default
transition: fade
---

# Gate JSON: the shared contract between stages

`devteam` renders the prompt. Your AI tool runs it. The model writes this back to disk.

```json {1-5|6-8|9-15|all}
{
  "stage": "stage-04",
  "status": "PASS",
  "track": "full",
  "timestamp": "2026-06-18T14:32:11Z",
  "blockers": [],
  "warnings": ["runbook references stale endpoint"],
  "chain": { "prev_hash": "sha256:a3f8..." },
  "workstreams": [
    { "workstream": "backend",  "host": "codex",       "status": "PASS" },
    { "workstream": "frontend", "host": "claude-code", "status": "PASS" },
    { "workstream": "platform", "host": "claude-code", "status": "WARN" },
    { "workstream": "qa",       "host": "gemini-cli",  "status": "PASS" }
  ]
}
```

<v-click>

`pipeline-complete` is reconstructable from `pipeline/gates/` **alone.** No model state required.

</v-click>

<style>
.slidev-layout { padding: 30px 60px 50px 60px; }
h1 { color: #4B286D; margin-bottom: 0.4em; }
p { color: #2C2E30; line-height: 1.5; margin-bottom: 0.5em; font-size: 0.9em; }
code { background: #F4F4F7; padding: 0.1em 0.3em; border-radius: 3px; font-size: 0.85em; color: #2C2E30; }
</style>

<!--
Don't read the JSON. Point at three regions, one click each:

Click 1 — Identity: "Every gate carries the same envelope: stage, status, track, timestamp. Audit a deploy six months from now — you know exactly what produced this artifact, what model version, what prompt hash."

Click 2 — Blockers/warnings/chain: "Status FAIL means blockers MUST be non-empty — the validator enforces this. Chain is tamper-evident: `devteam verify-chain` walks every gate and checks prev_hash integrity."

Click 3 — Workstreams: "Build is multi-role. Backend ran on Codex, QA on Gemini, frontend on Claude Code. Each wrote its own gate; the orchestrator merged them. Aggregate status is pessimistic: any FAIL → merged FAIL."

Click 4 — the key claim: "The orchestrator stores no state outside these files. The full pipeline is reconstructable from pipeline/gates/ alone — you can shut down the machine, come back in a month, and resume."

Then: "Let me show you a real one." → switch to terminal.
-->
