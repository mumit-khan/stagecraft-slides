# Stagecraft — slide deck

A Slidev presentation for [Stagecraft](https://github.com/telus-labs/stagecraft), an AI dev pipeline orchestrator: multi-host, gate-enforced, on disk.

## Versions

| Commit | Description |
|--------|-------------|
| `v1` (initial) | First deck — 12 slides, overview format |
| `v2` (2026-06-18) | Reworked — 18 slides, restructured around mechanism and evidence: pipeline visual, gate artifacts, autonomous driver, multi-host routing, control moments, safety layers, audit trail, verify-yourself commands |

## Run locally

Requires Node.js 18+.

```bash
npm install
npm run dev
```

Opens at `http://localhost:3030`. Presenter notes available at `/presenter`.

## Build

```bash
npm run build     # static SPA → dist/
npm run export    # PDF
npm run export-pdf
npm run export-pptx
```

## License

[CC BY 4.0](LICENSE) — Mumit Khan, 2026.
