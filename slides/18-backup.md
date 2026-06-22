---
layout: default
transition: fade
---

# Backup: timing · Q&A primers

<div class="backup-grid">

<div class="backup-col">
<div class="col-head">Timing reference</div>

| Section | Slides | Min |
|---|---|---|
| Hook + framing + problem | 1–3 | 3 |
| Agenda + before/after | 4–5 | 2 |
| Pipeline + tracks | 6–7 | 4 |
| Mechanism: gate · artifacts · driver · routing | 8–11 | 7 |
| Control moments + safety | 12–13 | 4 |
| Evidence: comparative · strengths · audit · verify | 14–17 | 5 |
| Getting started + fit | 18–19 | 3 |
| What's next | 20 | 2 |
| **Total** | | **~30** |

</div>

<div class="backup-col">
<div class="col-head">Q&amp;A primers</div>

| Question | Short answer |
|---|---|
| vs LangGraph / CrewAI? | Different layer — they wire LLM API calls; Stagecraft orchestrates AI *coding* tools |
| Cost? | One host by default. Fanout and multi-host are opt-in. |
| LLM ignores rules? | PreToolUse hooks block at write time. Gate validator catches the rest. FAIL = halt. |
| vs Omnigent? | Omnigent is the runtime/session plane; Stagecraft is the ordered delivery/evidence plane. An adapter could combine both. |
| Reproducible run? | Partially. Optional host metadata plus gate, prompt, and artifact hashes improve replay and auditability. |
| Share results? | `devteam report` — self-contained HTML, no service required. |

</div>

</div>

<style>
.slidev-layout { padding: 22px 46px 36px 46px; }
h1 { color: #4B286D; margin-bottom: 0.45em; font-size: 1.1em; }
.backup-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 22px; }
.backup-col { display: flex; flex-direction: column; gap: 6px; }
.col-head { font-size: 0.65em; font-weight: 700; color: #9B7BB8; text-transform: uppercase; letter-spacing: 0.06em; margin-bottom: 2px; }
table { width: 100%; border-collapse: collapse; font-size: 0.67em; }
th { background: #4B286D; color: #FFFFFF; padding: 5px 8px; text-align: left; }
td { padding: 4px 8px; color: #2C2E30; border-bottom: 1px solid #E3E6E8; }
tr:nth-child(even) { background: #FAFAFA; }
code { background: #F0EBF5; color: #4B286D; padding: 0.1em 0.3em; border-radius: 3px; font-size: 0.9em; }
</style>

<!--
Backup slide — not presented, for your reference.
Have the Q&A primers loaded before the talk.
-->
