---
layout: default
transition: fade
---

# Route any role to any model — 12 lines of YAML

```yaml {1-2|3-6|7-8|all}
routing:
  default_host: claude-code        # fallback for any role
  roles:
    backend: codex                 # backend workstream → Codex
    qa: gemini-cli                 # QA workstream → Gemini
  stages:
    stage-08: claude-code          # deploy always on Claude Code
pipeline:
  default_track: full
```

<v-click>

Adding a new host (Cursor, Aider, Cline) is ~200 lines — one directory under `hosts/`.

</v-click>

<style>
.slidev-layout { padding: 40px 60px 60px 60px; }
h1 { color: #4B286D; margin-bottom: 0.6em; }
p, li { color: #2C2E30; line-height: 1.6; margin-bottom: 0.4em; }
code { background: #F4F4F7; padding: 0.1em 0.3em; border-radius: 3px; font-size: 0.85em; color: #2C2E30; }
</style>

<!--
Walk the three click regions:

Click 1 — default_host: "Any workstream not explicitly routed falls through to here."

Click 2 — roles: "Claude is strong at design and review. Codex is fast and cheap for backend. Gemini is good at QA. Route the right model to the right role."

Click 3 — stages override: "Stage overrides beat role overrides beat default. Deploy always runs on Claude Code here because the runbook has Claude-specific instructions."

Click 4 — the 200-line point: "The core never invokes a model. All model-specific code lives in the host adapter — five methods against a 150-line contract. That's the full extensibility surface."

Transition: "What does all that structure actually catch?"
-->
