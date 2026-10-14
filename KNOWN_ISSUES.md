# Known Issues / Open Items

Tracked here so nothing has to be rediscovered by stumbling into it.

## Active

*(nothing currently blocking)*

## Known Limitations (by design, not bugs — noting so they're not mistaken for gaps)

- The prototype is mostly a scripted walkthrough. Two things are genuinely interactive: the breathing exercise (Flight Attendant and Pilot, panel 4) runs a real timed session, and the Wellness Toolkit cards respond to taps with a "launches in Phase 2" note. Everything else is narrative, and nothing is wired to real audio/video content, a backend, or real data. Expected for a portfolio concept piece, not a shipped product.
- Analytics on the demo page (Microsoft Clarity) will only reflect a handful of visitors, so any observation drawn from it is anecdotal, not statistically meaningful. The app concept's zero-data promise also means true DAU/retention tracking is deliberately not possible; usage would be measured as aggregate event counts only.
- Wireframes (`wireframes/index.html`) currently cover only the Flight Attendant persona's core flow. The Reserve Crew and Pilot storyboards exist in the high-fidelity prototype but don't have a corresponding low-fi wireframe pass.
- Tested in Chromium only. Not verified on Safari/Firefox or real mobile devices — likely fine given it's plain CSS/JS with no exotic APIs, but not confirmed.

## Candidate Improvements (open decisions, not bugs)

- **AI/automation framing** — upgrade the bulletin board's "automated keyword/toxicity filter" (currently US-303 in the backlog) from a plain keyword list to an on-device ML toxicity classifier, framed explicitly as a deliberate PO scoping decision: real AI/automation substance, zero conflict with the Zero-Data Privacy Vault since it classifies message content, not user behavior. Agreed in discussion to be the stronger AI feature over a personalization/"pin your most-used button" idea, which was considered and rejected as thin/checkbox-AI. Not yet written into the docs. *(Directly related to Active item below — fixing that properly closes this too.)*
- **Wireframes — persona coverage gap.** Only the Flight Attendant flow has a wireframe pass; Reserve Crew and Pilot personas exist in the high-fidelity prototype but not in wireframe form.

## Active — Found in 2026-10-13 Full-Project Scrutiny Pass

Reviewed as a skeptical PO would, looking for exactly what a sharp interviewer might catch. Ranked by severity; none fixed yet.

1. **[Critical] Dead cross-reference.** `roadmap.md` cites "see `product-vision.md`'s AI/automation framing," but that section doesn't exist in `product-vision.md`. The real reasoning lives in `mvp-scope.md`'s Phase 2 table instead. Fix: either add the section to `product-vision.md`, or correct the citation.
2. **[Critical] Roadmap overclaims what's built.** `roadmap.md` says MVP ships with "an on-device moderation classifier (see `backlog.md` US-303)," but US-303 as written only specifies a plain keyword/toxicity wordlist filter, not a classifier. Same underlying gap as the AI/automation candidate improvement above — fixing US-303 properly resolves both.
3. **[Significant] Push notifications vs. the privacy promise, unaddressed.** OKRs target "<10 min average time-to-first-response" and "30%+ weekly engagement" on the bulletin board, but nothing in the backlog explains how a user learns a new post/reply exists without a push notification — and push requires a device token registered with Apple/Google, in tension with US-201's "no device identifier is ever transmitted" promise. No story or doc currently resolves this.
4. **[Significant] Unrealistic acceptance criterion.** US-102 AC2 demands the breathing exercise "begins playback/animation within 500ms of tap on a cold app start." Real mobile cold starts routinely take 1–3+ seconds even for simple apps; this number reads as technically naive on close read.
5. **[Minor] Uncoordinated duplicate moderation logic.** US-301 AC2 and US-303 both independently describe content filtering via two different, uncross-referenced mechanisms (wordlist vs. toxicity filter), as if written separately rather than as one pipeline.

Judgment calls (not errors, but worth being ready to defend): the 30%-engagement-in-first-week OKR target may be aggressive for a product whose core use case is rare acute-panic events, not daily engagement; and publicly shipping `KNOWN_ISSUES.md` itself is a deliberate transparency choice that could read as unfinished to a non-technical reviewer, even though it reads as mature practice to a technical one.

## Resolved

- ~~Prototype had no real interaction to measure~~ — 2026-10-14: breathing exercise is now a working timed session (Flight Attendant and Pilot), toolkit cards are tappable, and the demo page is instrumented with Microsoft Clarity.
- ~~Stale "Product Owner, Reservations" references~~ — 2026-10-14: footer and README reworded to apply to Delta Product Owner roles generally.
- ~~"Nothing recorded" wording could read as contradicting the demo page's analytics~~ — 2026-10-14: scoped the claim to the app, and added a disclosure to the footer and README.
- ~~GitHub Pages not enabled, live prototype link 404'd~~ — enabled 2026-10-12, confirmed live at `serrayon.github.io/delta-wellness-app/prototype/`
- ~~Wireframes — style/depth decision~~ — decided 2026-10-12: keep the plain low-fidelity box style as-is, no restyle or annotations needed.
- ~~Definition of Done doc~~ — written, see `docs/definition-of-done.md`
- ~~Stakeholder map / roadmap sequencing doc~~ — written as two separate docs: `docs/stakeholder-map.md` and `docs/roadmap.md`
