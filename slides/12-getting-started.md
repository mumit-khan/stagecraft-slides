---
layout: two-cols
transition: fade
---

# Running a pipeline in 30 minutes

```bash {1-2|3-4|5|6|all}
# 1. Install (one time, anywhere)
git clone https://github.com/telus-labs/stagecraft && npm install && npm link

# 2. Initialize your project
cd ~/your-project && devteam init --host claude-code && devteam doctor

# 3. Run your first stage
devteam stage requirements --feature "a feature you understand" --headless

# 4. Follow the pipeline
devteam next
```

<v-click>

Two-week pilot guide: `docs/adoption-guide.md` — includes success criteria and honest bad-fit signals.

</v-click>

::right::

<v-click>

# Live stages

<img src="/images/devteam-ui-snapshot.png" />

</v-click>

<style>
.slidev-layout.two-columns {
  column-gap: 20px; /* Adjust pixel gap size as needed */
}
.slidev-layout { padding: 40px 60px 60px 60px; }
h1 { color: #4B286D; margin-bottom: 0.6em; }
p, li { color: #2C2E30; line-height: 1.6; margin-bottom: 0.4em; }
code { background: #F4F4F7; padding: 0.1em 0.3em; border-radius: 3px; font-size: 0.85em; color: #2C2E30; }
</style>

<!--
Walk the four steps — 60 seconds total.

"Install takes two minutes. init lays down 40 files — role subagents, rules, hooks, commands. doctor verifies everything is green. Then one command and you're running."

On --headless: "Headless mode pipes the prompt directly to Claude Code and waits for the gate file. No copy-paste. Good for first-timers."

On the pilot guide: "It's honest — it tells you within two weeks whether this is helping or not. And it tells you the signals that mean 'stop, this isn't the right fit.'"

Transition: → closing slide.
-->
