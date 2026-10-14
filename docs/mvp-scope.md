# CrewAnchor: MVP Scope

## MVP Prioritization Framework
Each candidate feature was scored against three constraints unique to this user: **must work offline**, **must preserve total anonymity**, and **must be usable in under 4 minutes**. Anything that failed any one of the three was cut from MVP, regardless of how valuable it looked on paper.

| Feature | Offline? | Anonymous? | <4 min? | MVP? |
|---|---|---|---|---|
| Offline-First Tactical Breathing Engine | Y | Y | Y | **Yes** |
| Zero-Data Privacy Vault | Y | Y | Y | **Yes** |
| Anonymous Peer-to-Peer Bulletin Board | Partial (cached last sync) | Y | Y | **Yes** |
| Scheduled 1:1 Peer Chat | N (needs live connectivity) | At risk (identity leakage via scheduling) | N | Cut: Phase 2 |
| Company-Integrated EAP Referral Deep-Link | Y | N (breaks anonymity boundary) | Y | Cut: violates core constraint |
| Mood Tracking / Journaling History | Y | Y | N (not an in-the-moment tool) | Cut: Phase 2 |

## The 3 MVP Capabilities

### 1. Offline-First Tactical Breathing Engine ("IRROPS Grounding")
Guided, timed breathing/pacing exercises that run entirely from cached local assets; no network call on launch, no spinner, no failure state if the device is in airplane mode. This is the core "panic loop interrupt" of the product and the one capability that must work with zero exceptions, since it's used in the worst-case moment (mid-IRROPS, no connectivity, under time pressure).

### 2. Zero-Data Privacy Vault
No login tied to a real identity, no employee ID, no device fingerprint persisted to a server. All personal state (streaks, saved exercises, preferences) lives in an on-device encrypted store. Nothing about usage is ever recoverable by the company, by design; this is the trust foundation the rest of the product depends on.

### 3. Anonymous Peer-to-Peer Bulletin Board
A lightweight, moderated, identity-stripped message board where crew can post and read short solidarity messages ("412 of us are delayed right now"). Syncs opportunistically when connectivity returns and caches the last pulled state for offline reading, and it never blocks the core grounding flow if it can't reach the network.

## MVP Cut Lines (and why)
- **No real-time chat**: live connectivity can't be guaranteed on a tarmac, and MVP optimizes for the worst-connectivity case, not the best.
- **No EAP integration**: any link to a company system, however well-intentioned, undermines the anonymity guarantee that drives adoption in a high-stakes-for-reporting population.
- **No long-term mood tracking**: valuable for Phase 2, but it's a "manage over time" feature competing for engineering budget against the "survive this moment" features that define the product's reason to exist.

## Phase 2: The Wellness Toolkit (Layover Fitness + Meditation Library)

MVP solves the *acute* problem: the panic spike in the next 60 seconds. It doesn't yet solve the *chronic* one: a crew member with a few hours in a hotel room, exhausted, jet-lagged, and unable to justify a $70/month subscription to a consumer wellness app for a lifestyle most of those apps weren't designed around. Phase 2 extends CrewAnchor from a panic-interrupt tool into a full operational wellness toolkit, while holding the same three MVP constraints (offline-first, anonymous, fast-access) that made the core product trustworthy in the first place.

| Feature | Offline? | Anonymous? | Fits the model? | Phase |
|---|---|---|---|---|
| Layover Fitness Library (hotel-room, no-equipment workouts) | Y (pre-bundled video/audio) | Y | Y | **Phase 2** |
| Guided Meditation Library (sleep, jet lag, pre-flight anxiety) | Y (pre-bundled audio) | Y | Y | **Phase 2** |
| Personalized AI Coaching / Adaptive Programs | N (requires server-side inference on usage data) | At risk (adaptive personalization implies a usage profile) | N | Cut: conflicts with Zero-Data Privacy Vault |

### 4. Layover Fitness Library
Short (10–20 min), zero-equipment bodyweight routines filmed/designed specifically for a hotel room: an "Energy Reset," a "Low-Impact / Sore Joints" track for turbulence days, and a "Sleep-Prep Stretch" for crossing time zones. Content is pre-bundled with app updates (not streamed) so it meets the same offline-first bar as the breathing engine; this is a scoping decision, not a nice-to-have, since video is the one asset type genuinely at risk of blowing past local storage constraints, so library size and update cadence have to be managed deliberately.

### 5. Guided Meditation Library
Longer-form audio than the acute tactical breathing engine (which stays a 2–4 minute panic-interrupt tool): nightly wind-down, pre-flight anxiety, and jet-lag reset tracks. The explicit value proposition: the same category of content crew would otherwise pay Calm/Headspace-style subscriptions for, free and already on the device, with zero data trail.

### Why This Is Phase 2, Not MVP
Both features are high-value but neither is load-bearing for the product's core promise (interrupt an active panic loop in under 4 minutes). Building them well, especially sourcing or producing enough workout/meditation content to not feel thin, is a content and licensing effort, not just an engineering one, so it's sequenced after the MVP proves the core grounding loop actually works and earns crew trust.
