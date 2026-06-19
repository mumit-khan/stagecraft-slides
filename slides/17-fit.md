---
layout: default
transition: slide-left
---

# Right for some teams. Not all.

<p class="subtitle">The two-week pilot in <code>docs/adoption-guide.md</code> tells you which, within two weeks.</p>

<div class="fit-grid">
  <div class="fit-col">
    <div class="fit-heading fit-good">Good fit ✅</div>
    <ul>
      <li>Non-trivial features needing structured review</li>
      <li>Role-owned code regions (backend ≠ frontend)</li>
      <li>Compliance or audit trail required</li>
      <li>Multiple AI models already in your stack</li>
      <li>Agentic AI work, not just completions</li>
      <li>Post-incident: "we need to know what shipped"</li>
    </ul>
  </div>
  <div class="fit-col">
    <div class="fit-heading fit-bad">Bad fit: save your time ❌</div>
    <ul>
      <li>Purely exploratory or prototype work</li>
      <li>AI for autocomplete / tab-completion only</li>
      <li>Solo projects with no review ceremony</li>
      <li>Teams not ready for gate discipline</li>
      <li>Simple changes where full process is overhead</li>
    </ul>
  </div>
</div>

<style>
.slidev-layout { padding: 35px 60px 55px 60px; }
h1 { color: #4B286D; margin-bottom: 0.3em; }
.subtitle { color: #676E73; font-size: 0.82em; margin-bottom: 0.8em; margin-top: 0; }
code { background: #F4F4F7; padding: 0.1em 0.3em; border-radius: 3px; font-size: 0.85em; color: #2C2E30; }
.fit-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 32px;
}
.fit-col {}
.fit-heading {
  font-weight: 600;
  font-size: 1.05em;
  margin-bottom: 0.5em;
  padding-bottom: 0.3em;
  border-bottom: 2px solid;
}
.fit-good { color: #2B8000; border-color: #2B8000; }
.fit-bad { color: #E5342A; border-color: #E5342A; }
li { color: #2C2E30; line-height: 1.65; margin-bottom: 0.35em; font-size: 0.92em; }
ul { margin-left: 1.2em; margin-bottom: 0.8em; }
</style>

<!--
This slide builds credibility — you're not overselling.

"The adoption guide is honest about this. If your team is doing exploratory work, if you're using AI only for autocomplete, if you're a solo dev — drop it. It's not the right tool."

"The two-week pilot tells you within that window. It has explicit success criteria and bad-fit signals."

"Post-incident fit: you had an incident, couldn't reconstruct what shipped, now you want structure. That's a real problem this solves."
-->
