---
layout: default
transition: slide-left
---

# AI tools give you a chat log, not a process

- **Context drifts:** model forgets your architecture mid-session
- **Scope drifts:** "quick fix" becomes 600 changed lines
- **Tests follow code:** acceptance criteria become an afterthought
- **Review is unstructured:** approvals in chat, nothing on disk
- **No audit trail:** six months later, you can't reconstruct what shipped

> None of these are model problems. They're **orchestration problems**.

<style>
.slidev-layout { padding: 35px 60px 50px 60px; }
h1 { color: #4B286D; margin-bottom: 0.5em; }
p, li { color: #2C2E30; line-height: 1.6; margin-bottom: 0.35em; font-size: 1em; }
ul { margin-left: 1.2em; margin-bottom: 0.6em; }
blockquote { border-left: 4px solid #4B286D; padding-left: 1em; margin-top: 1em; background: #F8F5FC; border-radius: 0 6px 6px 0; padding: 14px 16px; }
blockquote p { color: #4B286D !important; font-style: italic; font-size: 1.05em; }
strong { color: #4B286D; }
</style>

<!--
Read the bullets briefly — one beat each.

"None of these are model problems. Claude is fine. Codex is fine. Gemini is fine. The gap is between the model and the codebase. We've built structure for human teams — PRs, code review, CI, design docs, runbooks. We have almost none of it for AI work."

The blockquote is the pivot. Pause before and after it.
-->
