---
layout: two-cols-header
transition: slide-left
---

# Right for some teams. Deliberately not for all.

The two-week pilot in `docs/adoption-guide.md` tells you which within two weeks.

::left::

**Good fit**

<v-clicks :depth="1">

- Non-trivial features needing structured review
- Role-owned code regions (backend ≠ frontend)
- Compliance or audit trail required
- Multiple models already in your stack
- Teams doing agentic AI, not just completions

</v-clicks>

::right::

<v-click>

**Bad fit**

- Purely exploratory or prototype work
- AI for autocomplete only
- Solo projects with no review ceremony
- Teams not ready for gate discipline
- Simple changes where full process is overhead

</v-click>

<style>
.slidev-layout { padding: 40px 60px 60px 60px; }
h1 { color: #4B286D; margin-bottom: 0.6em; }
p, li { color: #2C2E30; line-height: 1.6; margin-bottom: 0.4em; }
ul { margin-left: 1.2em; margin-bottom: 0.8em; }
strong { color: #4B286D; }
</style>

<!--
This slide builds credibility — you're not overselling.

"The adoption guide is honest about this. If your team is doing exploratory work, if you're using AI only for autocomplete, if you're a solo dev — drop it. It's not the right tool. The two-week pilot in docs/adoption-guide.md tells you within that window whether it's helping or not."

For tech leads: this is the slide that makes the rest of the talk credible. You're not pitching a silver bullet.

Transition: "If it looks like a fit, here's how to try it in 30 minutes."
-->
