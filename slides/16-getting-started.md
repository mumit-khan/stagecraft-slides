---
layout: two-cols
transition: fade
---

# Running a pipeline in 30 minutes

```bash {1-2|3-5|6-8|9-10|all}
# 1. Install (one time, anywhere)
git clone <repo> && npm install && npm link

# 2. Initialize your project
cd ~/your-project
devteam init --host claude-code
devteam doctor   # should be all green

# 3. Run your first stage
devteam stage requirements \
  --feature "a feature you understand" --headless

# 4. Follow the pipeline
devteam next     # → "▶️ run-stage design (stage-02)"
```

Or run the whole pipeline:

```bash
devteam run --feature "Add SMS opt-in" \
  --track quick --budget-usd 5 --headless
```

::right::

**What `devteam init` installs**

- `.claude/agents/*.md` (12 role subagents)
- `.claude/skills/` (13 task helpers)
- `.devteam/rules/` (10 pipeline rules + per-stage docs)
- `settings.local.json` (hooks: validator, secret-scan, approval-derivation)
- `pipeline/gates/` (workspace for gate files)

**Two-week pilot guide**

`docs/adoption-guide.md`: success criteria, honest bad-fit signals. Know within two weeks.

**`devteam doctor` output when healthy**

```
✅ hooks wired (Stop, SubagentStop, PreToolUse)
✅ 12 agent files present
✅ host CLI on PATH: claude
✅ gate workspace exists
```

<style>
.slidev-layout { padding: 25px 30px 45px 30px; column-gap: 24px; }
h1 { color: #4B286D; margin-bottom: 0.4em; font-size: 1.25em; }
p, li { color: #2C2E30; line-height: 1.5; margin-bottom: 0.3em; font-size: 0.82em; }
ul { margin-left: 1.2em; margin-bottom: 0.6em; }
strong { color: #4B286D; display: block; margin-top: 0.8em; margin-bottom: 0.3em; }
code { background: #F4F4F7; padding: 0.1em 0.3em; border-radius: 3px; font-size: 0.85em; color: #2C2E30; }
</style>

<!--
Walk the four code steps — 60 seconds.

"Install takes two minutes. init lays down 40 files — role subagents, rules, hooks, commands. doctor verifies everything is green."

"Headless mode pipes the prompt directly to the host CLI and waits for the gate file. No copy-paste, no switching windows."

"devteam run runs the whole pipeline: advances on PASS, retries code-defect FAILs, halts for escalations. --budget-usd 5 caps cost — useful for first runs."
-->
