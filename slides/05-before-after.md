---
layout: two-cols-header
transition: slide-left
---

# Same feature — radically different artifact trail

::left::

**Before (chat-driven)**

- 1 chat log
- Approvals: in messages
- Scope: what the agent did
- Tests: if the agent remembered
- Review: "looks good 👍"
- Audit: scrollback search
- Model: one, end-to-end

::right::

**After: Stagecraft**

- 18+ artifacts + gates
- Approvals: `pipeline/gates/stage-05.json`
- Scope: `pipeline/brief.md`, versioned
- Tests: gated; AC mapping on spec-driven tracks
- Review: `REVIEW: APPROVED` or `CHANGES REQUESTED`
- Audit: `cat pipeline/gates/*.json`
- Model: configurable per role and stage

<style>
.slidev-layout { padding: 40px 60px 60px 60px; }
h1 { color: #4B286D; margin-bottom: 0.6em; }
p, li { color: #2C2E30; line-height: 1.55; margin-bottom: 0.35em; }
ul { margin-left: 1.2em; margin-bottom: 0.6em; }
strong { color: #4B286D; display: block; margin-bottom: 0.4em; }
code { background: #F4F4F7; padding: 0.1em 0.3em; border-radius: 3px; font-size: 0.82em; color: #2C2E30; }
.col-left { border-right: 3px solid #E3E6E8; padding-right: 2em; opacity: 0.75; }
.col-right { padding-left: 2em; }
</style>

<!--
Walk rows by pairing left → right. Spend a beat on three:

1. "AC mapping" — on full and quick tracks, the executable spec maps AC-N → Scenario → test evidence. Stage 6's PASS contract requires acceptance criteria to be met.

2. "REVIEW: APPROVED / CHANGES REQUESTED" — not a thumbs up in Slack. A structured verdict in a file the pipeline reads.

3. "Configurable per role and stage" — the contract between hosts is JSON, not a shared model context. A small YAML routing block configures it.
-->
