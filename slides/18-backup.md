---
layout: default
transition: fade
---

# Backup: timing reference

| Section | Slides | Time |
|---|---|---|
| Hook + not-a-vibe-coder + problem | 1–3 | 4 min |
| Agenda + before/after | 4–5 | 3 min |
| Pipeline + tracks | 6–7 | 5 min |
| Gate JSON + autonomous driver + multi-host | 8–10 | 6 min |
| Control moments + safety | 11–12 | 4 min |
| Comparative + strengths + audit | 13–15 | 5 min |
| Getting started + fit | 16–17 | 3 min |
| **Total** | | **~30 min** |

<v-click>

**Q&A primers**

| Question | Short answer |
|---|---|
| vs LangGraph/CrewAI/AutoGen? | Different layer — they wire LLM calls in code; Stagecraft orchestrates AI *coding* tools |
| Cost? | Default is one host. Fanout and multi-host are opt-in. |
| LLM doesn't follow rules? | PreToolUse hooks enforce at tool-call time. Gate validator catches the rest. FAIL = halt. |
| Add Cursor/Cline/Windsurf? | ~200 lines, one directory under `hosts/`. Five methods against the contract. |
| Reproducible LLM run? | Partially. Gate records model_version, temp, seed, prompt_hash. Audit-grade, not bit-for-bit. |

</v-click>

<style>
.slidev-layout { padding: 30px 60px 50px 60px; }
h1 { color: #4B286D; margin-bottom: 0.5em; }
table th { background: #4B286D; color: #FFFFFF; padding: 8px 14px; }
table td { padding: 6px 14px; color: #2C2E30; }
table tr:nth-child(even) { background: #FAFAFA; }
table { width: 100%; border-collapse: collapse; margin-bottom: 1em; font-size: 0.82em; }
</style>

<!--
Backup slide — not presented, for your reference.
Have the Q&A primers loaded before the talk.
-->
