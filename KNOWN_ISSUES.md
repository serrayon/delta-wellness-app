# Known Issues / Open Items

Tracked here so nothing has to be rediscovered by stumbling into it.

## Active

*(nothing currently blocking)*

## Known Limitations (by design, not bugs — noting so they're not mistaken for gaps)

- The prototype is a static, scripted demo — tapping through shows the intended flow, but nothing is wired to real audio/video content, a backend, or real data. This is expected for a portfolio concept piece, not a shipped product.
- Wireframes (`wireframes/index.html`) currently cover only the Flight Attendant persona's core flow. The Reserve Crew and Pilot storyboards exist in the high-fidelity prototype but don't have a corresponding low-fi wireframe pass.
- Tested in Chromium only. Not verified on Safari/Firefox or real mobile devices — likely fine given it's plain CSS/JS with no exotic APIs, but not confirmed.

## Candidate Improvements (open decisions, not bugs)

- **AI/automation framing** — upgrade the bulletin board's "automated keyword/toxicity filter" (currently US-303 in the backlog) from a plain keyword list to an on-device ML toxicity classifier, framed explicitly as a deliberate PO scoping decision: real AI/automation substance, zero conflict with the Zero-Data Privacy Vault since it classifies message content, not user behavior. Agreed in discussion to be the stronger AI feature over a personalization/"pin your most-used button" idea, which was considered and rejected as thin/checkbox-AI. Not yet written into the docs.
- **Wireframes — persona coverage gap.** Only the Flight Attendant flow has a wireframe pass; Reserve Crew and Pilot personas exist in the high-fidelity prototype but not in wireframe form.

## Resolved

- ~~GitHub Pages not enabled, live prototype link 404'd~~ — enabled 2026-10-12, confirmed live at `serrayon.github.io/delta-wellness-app/prototype/`
- ~~Wireframes — style/depth decision~~ — decided 2026-10-12: keep the plain low-fidelity box style as-is, no restyle or annotations needed.
- ~~Definition of Done doc~~ — written, see `docs/definition-of-done.md`
- ~~Stakeholder map / roadmap sequencing doc~~ — written as two separate docs: `docs/stakeholder-map.md` and `docs/roadmap.md`
