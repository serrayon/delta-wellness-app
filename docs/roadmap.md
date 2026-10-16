# CrewAnchor: Roadmap (Now / Next / Later)

A roadmap is a sequencing argument, not a date-filled Gantt chart; the actual PO skill it demonstrates is *why this order and not another one*, especially when priorities compete. Dates are deliberately left loose; the reasoning is the point.

## Now: MVP
**Goal:** Prove the core "panic-to-grounded" loop actually works and earns crew trust before building anything else on top of it.
- Offline-First Tactical Breathing Engine
- Zero-Data Privacy Vault
- Peer-to-Peer Bulletin Board (with automated keyword/toxicity filtering and one-tap reporting; see `backlog.md` US-303)

*Why first:* everything else in this roadmap is worthless if the core promise (works offline, never logs usage, works in under 4 minutes) doesn't hold up. No amount of added features fixes a broken foundation, and trust lost early (a logged session, a crash in airplane mode) is expensive to earn back with this user.

## Next (Phase 2): Wellness Toolkit
**Goal:** Extend from acute panic-interrupt to ongoing operational wellness, once the core loop is validated.
- Layover Fitness Library (hotel-room, no-equipment workouts)
- Guided Meditation Library (sleep, jet lag, pre-flight anxiety)

*Why second, not first:* this is a content and licensing effort more than an engineering one (sourcing/producing enough workout and meditation content to not feel thin). It's sequenced after MVP specifically so content production can run in parallel with MVP's engineering build without competing for the same team's attention, and because it's genuinely lower-stakes to launch late than a broken core loop is.

*Why not later still:* it's also the single most common thing crew will actually want day-to-day (acute panic is rare; layover boredom/exhaustion is constant), so it's the next priority the moment MVP is stable, not a someday idea.

## Later: Under Evaluation, Not Committed
**Goal:** Ideas worth tracking, deliberately not yet scoped, because scoping them now would be guessing ahead of real usage data.
- **Scheduled 1:1 Peer Chat**: cut from MVP for connectivity reasons and because scheduling implies a usage record (see `mvp-scope.md`); revisit only if the bulletin board shows demand for deeper connection than the display-label posts provide
- **On-device pattern-based content suggestions**: evaluated and intentionally *not* committed; the cloud-based version of personalization was cut outright for conflicting with the Zero-Data Privacy Vault (see the Phase 2 table in `mvp-scope.md`), and even an on-device version needs real MVP usage data before it's worth building
- **Mood tracking / journaling history**: cut from MVP as "not an in-the-moment tool"; would need its own privacy model work before Phase 3, since trend data is inherently more identifying than a single unlogged session

## What's Explicitly Not on This Roadmap
No company-integrated EAP referral, ever, regardless of phase; see `mvp-scope.md`'s cut-line reasoning. Some features aren't "later," they're "no," and a roadmap that doesn't say that out loud isn't being honest about its own constraints.
