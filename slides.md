---
theme: default
title: "Stagecraft"
author: "Mumit Khan"
date: "2026-06-22"
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

<div class="presenter-info">Mumit Khan, AI Accelerator · June 2026</div>

<style>
h1 { color: #4B286D; font-size: 2.8em; margin-top: 120px; }
p { color: #676E73; }
.presenter-info { color: #676E73; font-size: 0.9em; margin-top: 0.5em; }
</style>

<!--
Open strong — don't rush past the frustration:
"Most AI coding tools give you a chat log. You're three hours in — no brief, no design, no tests. Just a transcript. Stagecraft asks: what happens if you run an AI coding tool through an actual software dev process instead?"
Keep it short. The rest of the talk earns the claim.
-->

---
src: ./slides/02-not-a-vibe-coder.md
---

---
src: ./slides/03-problem.md
---

---
src: ./slides/04-agenda.md
---

---
src: ./slides/05-before-after.md
---

---
src: ./slides/06-pipeline.md
---

---
src: ./slides/07-tracks.md
---

---
src: ./slides/08-gate-json.md
---

---
src: ./slides/08b-artifacts.md
---

---
src: ./slides/09-autonomous-driver.md
---

---
src: ./slides/10-multi-host.md
---

---
src: ./slides/11-control-moments.md
---

---
src: ./slides/12-safety.md
---

---
src: ./slides/13-comparative.md
---

---
src: ./slides/14-strengths.md
---

---
src: ./slides/15-audit.md
---

---
src: ./slides/15b-verify.md
---

---
src: ./slides/16-getting-started.md
---

---
src: ./slides/17-fit.md
---

---
src: ./slides/17b-roadmap.md
---

---
layout: center
class: text-center
transition: fade
---

# Questions

<div class="repo-link">github.com/telus-labs/stagecraft</div>

<div class="cta-note">Two-week pilot guide: <code>docs/adoption-guide.md</code></div>

<style>
h1 { color: #4B286D; font-size: 3em; }
.repo-link { color: #2B8000; font-size: 1.1em; margin-top: 0.8em; }
.cta-note { color: #676E73; font-size: 0.85em; margin-top: 0.6em; font-family: 'Fira Code', monospace; }
</style>

<!--
Q&A primers — have these ready:

Q: How does this compare to LangGraph / CrewAI / AutoGen?
A: Different problem. Those are Python libraries for coordinating LLM calls in your code. Stagecraft is a pipeline scaffold for AI *coding* tools and runtimes — the model invocation happens inside Claude / Codex / Gemini / Omnigent / openai-compat, not in the core orchestrator.

Q: What if the LLM doesn't follow the rules?
A: Hook-enforceable rules (allowedWrites, secret scanning) are enforced at tool-call time via Claude Code PreToolUse hooks. The gate validator catches the rest post-hoc. A FAIL gate halts the pipeline — there's no silently moving forward.

Q: Cost — adversarial review sounds expensive.
A: Default config is one host per pipeline. Fanout is opt-in. Route bulk work to cheaper models (Codex for backend), reserve expensive ones for Principal/Security.

Q: Can I add Cursor / Aider / Cline / Windsurf?
A: Yes. Implement a host adapter against the contract. Omnigent and openai-compat are recent examples: one runtime-backed, one HTTP-native.

Q: Is "reproducible LLM run" actually a thing?
A: Partially. Gates record model_version, temperature, seed, system_prompt_hash — enough for audit, not bit-for-bit reproduction. The docs are explicit about the limit.
-->

---
src: ./slides/18-backup.md
---
