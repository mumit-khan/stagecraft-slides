---
theme: default
title: "Stagecraft"
author: "Mumit Khan"
date: "2026-06-02"
confidentiality: "Public"
language: "en"
aspectRatio: "16/9"
canvasWidth: 980
fonts:
  sans: "Helvetica Neue"
  mono: "Fira Code"
colorSchema: light
highlighter: shiki
lineNumbers: false
drawings:
  enabled: false
transition: fade
---

<img src="/images/telus-logo-en.png" style="position: absolute; top: 30px; left: 40px; width: 160px;" />

# Stagecraft

An AI dev pipeline. Multi-host, gate-enforced, on disk.

<div class="presenter-info">Mumit Khan, AI Accelerator · June 2026 <br />
github.com/telus-labs/stagecraft</div>

<style>
h1 { color: #4B286D; font-size: 2.8em; margin-top: 120px; }
p { color: #676E73; }
.presenter-info { color: #676E73; font-size: 0.9em; margin-top: 0.5em; }
</style>

<!--
Open with the frustration — don't rush past it:
"Most AI coding tools give you a chat log. You're three hours in. You don't have a brief, a design, or tests — just a transcript. Stagecraft asks: what happens if you run an AI coding tool through an actual software dev process instead?"

Keep it short. The demo is more interesting than the intro.
-->

---
src: ./slides/02-agenda.md
---

---
src: ./slides/03-problem.md
---

---
src: ./slides/04-before-after.md
---

---
src: ./slides/05-gate-json.md
---

---
src: ./slides/06-demo.md
---

---
src: ./slides/07-pipeline.md
---

---
src: ./slides/08-control-moments.md
---

---
src: ./slides/09-multi-host.md
---

---
src: ./slides/10-safety.md
---

---
src: ./slides/11-fit.md
---

---
src: ./slides/12-getting-started.md
---

---
layout: center
class: text-center
transition: fade
---

# Questions

<div class="repo-link">github.com/telus-labs/stagecraft</div>

<style>
h1 { color: #4B286D; font-size: 3em; }
.repo-link { color: #2B8000; font-size: 1em; margin-top: 0.8em; }
</style>

<!--
Q&A primers — have these ready:

Q: How does this compare to LangGraph / CrewAI / AutoGen?
A: Different problem. Those are Python libraries for coordinating LLM calls. Stagecraft is a pipeline scaffold for AI coding tools — model invocation happens inside Claude / Codex / Gemini, not via a framework SDK.

Q: What if my LLM doesn't follow the rules?
A: Hook-enforceable rules (allowedWrites, secret scanning) are enforced at tool-call time via Claude Code PreToolUse hooks. Gate validator catches the rest post-hoc. A FAIL gate halts the pipeline.

Q: Cost — adversarial review sounds expensive.
A: Default config is one host per pipeline. Fanout is opt-in. Route bulk work to cheaper models; reserve expensive ones for Principal and Security.

Q: Can I add Cursor / Aider / Cline / Windsurf?
A: Yes. ~200 lines. Implement 5 methods against the host-adapter contract. CONTRIBUTING.md has the recipe.

Q: Is "reproducible LLM run" actually a thing?
A: Partially. Gates record model_version, temperature, seed, system_prompt_hash. Enough for an audit trail — not bit-for-bit reproduction. The docs are explicit about this.
-->

---
layout: default
transition: fade
---

# Backup: timing reference

| Section | Slides | Time |
|---|---|---|
| Hook + problem | 1–3 | 4 min |
| Before/after + gate JSON | 4–5 | 5 min |
| Terminal demo | 6 | 11 min |
| Pipeline + control | 7–8 | 4 min |
| Multi-host · safety · fit | 9–11 | 5 min |
| Getting started | 12 | 2 min |
| **Total** | | **31 min** |

<style>
.slidev-layout { padding: 40px 60px 60px 60px; }
h1 { color: #4B286D; margin-bottom: 0.6em; }
table th { background: #4B286D; color: #FFFFFF; padding: 10px 16px; }
table td { padding: 8px 16px; color: #2C2E30; }
table tr:nth-child(even) { background: #FAFAFA; }
table { width: 100%; border-collapse: collapse; }
p, li { color: #2C2E30; line-height: 1.6; }
</style>

<!--
Backup slide — not presented, for your reference.
-->
