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
  "orchestrator": "devteam@0.4.0",
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

Completed stage progression is reconstructable from `pipeline/gates/`. Active autonomous runs also retain bounded run state and an append-only decision log.

</v-click>

<style>
.slidev-layout { padding: 30px 60px 50px 60px; }
h1 { color: #4B286D; margin-bottom: 0.4em; }
p { color: #2C2E30; line-height: 1.5; margin-bottom: 0.5em; font-size: 0.9em; }
code { background: #F4F4F7; padding: 0.1em 0.3em; border-radius: 3px; font-size: 0.85em; color: #2C2E30; }
</style>

<!--
Don't read the JSON. Point at three regions, one click each:

Click 1 — Identity: "Every gate carries the same envelope: stage, status, orchestrator, track, timestamp. Optional reproducibility fields can record model and prompt metadata when the host supplies them."

Click 2 — Blockers/warnings/chain: "Status FAIL means blockers MUST be non-empty — the validator enforces this. Chain is tamper-evident: `devteam verify-chain` walks every gate and checks prev_hash integrity."

Click 3 — Workstreams: "Build is multi-role. Backend ran on Codex, QA on Gemini, frontend on Claude Code. Each wrote its own gate; the orchestrator merged them. Aggregate status is pessimistic: any FAIL → merged FAIL."

Click 4 — the key claim: "Completed stage progression is on disk in pipeline/gates/. During an autonomous run, run-state.json and the append-only run log retain retry, budget, authority, and resume details. No hidden model session is the source of truth."

Then: "Let me show you a real one." → switch to terminal.
-->
