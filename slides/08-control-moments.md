---
layout: default
transition: slide-left
---

# You make 3 decisions. The rest is the framework's job.

<v-clicks>

- **At the start** — choose a track (`full` / `quick` / `nano` / `hotfix`) and write one paragraph. Track = which stages run.

- **At every gate** — read the output. `PASS` → next. `FAIL` → fix. `ESCALATE` → decide.

- **At escalations** — pipeline halts and waits. You make the call; nothing moves without you.

</v-clicks>

<v-click>

> 5–10 min of active decisions over 30–60 min wall-clock.

</v-click>

<style>
.slidev-layout { padding: 40px 60px 60px 60px; }
h1 { color: #4B286D; margin-bottom: 0.6em; }
p, li { color: #2C2E30; line-height: 1.6; margin-bottom: 0.4em; }
ul { margin-left: 1.2em; margin-bottom: 0.8em; }
blockquote { border-left: 4px solid #4B286D; padding-left: 1em; color: #4B286D; margin-top: 1em; font-size: 1.1em; }
code { background: #F4F4F7; padding: 0.1em 0.3em; border-radius: 3px; font-size: 0.85em; color: #2C2E30; }
</style>

<!--
Land on the blockquote — it's the key value proposition for tech leads especially.

"You don't write boilerplate, shuffle files between agents, track who reviewed what, or compute aggregate status. You decide what to build, whether each gate is good enough, and what to do when the pipeline halts."

This is the answer to 'why not just prompt Claude yourself?'

Transition: "Now — a word on how Stagecraft stays model-agnostic."
-->
