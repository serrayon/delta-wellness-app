# CrewAnchor

**A 100% anonymous, offline-first mental health and resilience app for airline flight crew.**

Portfolio case study built for Delta Air Lines Product Owner roles. Demonstrates the full product-ownership loop: translating an operational pain point into product vision, scoping an MVP under real constraints, writing build-ready user stories and acceptance criteria, and defining the metrics that prove it worked.

> 🔗 **[Try the interactive prototype →](https://serrayon.github.io/delta-wellness-app/prototype/)**
> *(If the link isn't live yet, see "Getting Started" below to preview it another way.)*

---

## Getting Started

The prototype is a single static HTML file — there's no build step, no `npm install`, no server required.

**Option 1 — Live link (once GitHub Pages is on):**
Visit `https://serrayon.github.io/delta-wellness-app/prototype/`. To turn this on: repo **Settings → Pages → Source → Deploy from a branch → `main` / `/ (root)` → Save**. Takes a minute or two to go live after saving.

**Option 2 — Preview locally, no setup:**
1. Clone or download the repo
2. Open `prototype/index.html` directly in any browser (double-click it, or drag it into a browser tab)
3. Click the arrows (or use your keyboard's ← / → keys) to move through the 6 storyboard panels

That's it — it's plain HTML/CSS/JS with no dependencies, so it works the same whether it's opened as a local file or served from Pages.

---

## The Problem

Flight crew operate inside a uniquely high-stress environment most consumer mental health apps aren't built for: irregular operations (IRROPS), unpredictable reassignments, layover isolation, and anxiety tied to FAA/company reporting. The tools that exist are either hard to reach mid-shift, require connectivity crew don't have on the tarmac or in-flight, or create a record crew don't want tied to their name.

## The Product

CrewAnchor meets a crew member in the exact 2–4 minute window they actually have between boarding calls, works with **zero network dependency**, and never asks for anything that could identify them. Three MVP capabilities, each chosen because it survives the worst case (no signal, no time, no willingness to create a paper trail):

1. **Offline-First Tactical Breathing Engine** — guided grounding exercises that run entirely from cached local assets
2. **Zero-Data Privacy Vault** — no login, no employee ID, nothing recoverable by the company, ever
3. **Anonymous Peer-to-Peer Bulletin Board** — lightweight, moderated, identity-stripped solidarity messages from other crew

## The Storyboard

A flight attendant (Sarah) hits an IRROPS trigger, opens the app in a quiet galley corner, selects "IRROPS Grounding," completes an offline breathing exercise, sees an anonymous peer message, and returns to the cabin grounded — in under 3 minutes. Walk through it yourself in the [interactive prototype](./prototype/index.html).

## Product Artifacts

| Doc | What's in it |
|---|---|
| [`docs/product-vision.md`](./docs/product-vision.md) | Problem statement, vision, target personas, explicit non-goals |
| [`docs/mvp-scope.md`](./docs/mvp-scope.md) | Prioritization framework and why each MVP cut line was drawn |
| [`docs/backlog.md`](./docs/backlog.md) | Full Agile backlog — 12 user stories across 4 epics, each with build-ready acceptance criteria |
| [`docs/okrs.md`](./docs/okrs.md) | Objectives & key results, and the metrics deliberately excluded and why |
| [`docs/definition-of-done.md`](./docs/definition-of-done.md) | The blanket "done means done" standard applied to every story, beyond its own acceptance criteria |
| [`docs/stakeholder-map.md`](./docs/stakeholder-map.md) | RACI across PO, Engineering, Design, Security, and a Crew Advisory Group — including where the PO is deliberately *not* the final word |
| [`docs/roadmap.md`](./docs/roadmap.md) | Now/Next/Later sequencing — the reasoning behind the order, including what's cut permanently, not just deferred |
| [`wireframes/index.html`](./wireframes/index.html) | Low-fidelity layout pass for the core flow, predating the visual design |

> ⚠️ See [`KNOWN_ISSUES.md`](./KNOWN_ISSUES.md) for the live prototype link's current status and other open items.

## Three Personas, Three Journeys

All three personas defined in the product vision now have a full 6-panel storyboard in the interactive prototype, switchable via the tabs at the top:
- **Flight Attendant (Sarah)** — IRROPS panic trigger → tactical breathing → resolution
- **Reserve Crew (Marcus)** — unplanned layover isolation → the Phase 2 Wellness Toolkit
- **Pilot (Captain Reyes)** — post-incident reporting anxiety → the Zero-Data Privacy Vault

## Why This Project

After eight years as a Southwest flight attendant, I know where crew support tools fall short: they assume signal, time, and a willingness to leave a record. This project applies product-ownership discipline (backlog ownership, build-ready requirements, agile delivery, data-informed prioritization) to that one internal customer group. It's built to show the work, not just describe it.

## Analytics & Privacy Note

The **demo page** (`prototype/index.html`) uses [Microsoft Clarity](https://clarity.microsoft.com) to collect anonymous usage analytics (session replays and heatmaps), so I can observe how real visitors move through the walkthrough. This is separate from the **CrewAnchor app concept**, which is designed to collect no data at all: no login, no identifiers, nothing recoverable. Measuring a product without breaking that promise is itself one of the open product questions; see `KNOWN_ISSUES.md`.

---
*Built as a portfolio project. Not an official Delta Air Lines product.*
