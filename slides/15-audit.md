---
layout: default
transition: fade
---

<div class="stat-page">

<div class="big-stat">
  <div class="big-num">2,056</div>
  <div class="big-label">runtime tests: gate validation, CLI commands, hook enforcement. Not assertions, not mocks.</div>
</div>

<div class="sub-grid">
  <div class="sub-stat">
    <div class="sub-num">18</div>
    <div class="sub-label">ordered stages</div>
  </div>
  <div class="sub-stat">
    <div class="sub-num">100</div>
    <div class="sub-label">test files</div>
  </div>
  <div class="sub-stat">
    <div class="sub-num">6</div>
    <div class="sub-label">change tracks</div>
  </div>
  <div class="sub-stat">
    <div class="sub-num">4</div>
    <div class="sub-label">first-party host adapters</div>
  </div>
</div>

<div class="chain-callout">
  <div class="chain-label">Tamper-evident audit trail</div>
  <div class="chain-body">Every gate is SHA-256 chained to its predecessor. <code>devteam verify-chain</code> exits non-zero on any tampered link. CI-usable. No service required. Optional: set <code>DEVTEAM_SIGNING_SECRET</code> to authenticate each gate with HMAC-SHA256 — <code>--require-signed</code> makes unsigned history fail in CI.</div>
</div>

</div>

<style>
.slidev-layout { background: #F4F4F7; padding: 0; }
.stat-page {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100%;
  padding: 40px 60px 50px;
  gap: 20px;
}
.big-stat { text-align: center; }
.big-num { font-size: 5em; font-weight: bold; color: #4B286D; line-height: 1; }
.big-label { color: #676E73; font-size: 0.88em; margin-top: 0.35em; max-width: 560px; line-height: 1.4; }
.sub-grid { display: flex; gap: 48px; }
.sub-stat { text-align: center; }
.sub-num { font-size: 2.5em; font-weight: bold; color: #4B286D; line-height: 1; }
.sub-label { color: #676E73; font-size: 0.8em; margin-top: 4px; }
.chain-callout {
  background: #fff;
  border: 1.5px solid #D9C8F0;
  border-left: 4px solid #4B286D;
  border-radius: 0 8px 8px 0;
  padding: 14px 20px;
  max-width: 640px;
  width: 100%;
}
.chain-label { font-weight: 700; color: #4B286D; font-size: 0.82em; margin-bottom: 4px; text-transform: uppercase; letter-spacing: 0.05em; }
.chain-body { color: #2C2E30; font-size: 0.82em; line-height: 1.5; }
code { color: #4B286D; background: #F0EBF5; padding: 0.1em 0.4em; border-radius: 3px; }
</style>

<!--
Let the 2,056 land. Then clarify what "runtime tests" means — not unit assertions, but tests that actually invoke CLI commands, write gate files, fire hooks.

"The SHA-256 chain is the bit most people don't expect. Every gate references its predecessor's hash. devteam verify-chain walks the full chain — one tampered file fails the whole audit. You can wire it into CI in two lines."

"For teams with stricter compliance requirements: set DEVTEAM_SIGNING_SECRET and each gate gets an HMAC-SHA256 signature on top of the hash chain. --require-signed in CI means any unsigned gate fails the audit."

Transition: Next slide — every one of these claims is something you can verify yourself in under five minutes.
-->
