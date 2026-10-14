# CrewAnchor — Agile Backlog
### Epic 1: Offline-First Tactical Breathing Engine

**US-101 — Offline Grounding Access**
> As a stranded Flight Attendant, I want to access grounding exercises while my phone is in Airplane Mode, so that I can manage my anxiety even when I have no data connection on the tarmac.

Acceptance Criteria:
1. The "IRROPS Grounding" tab utilizes cached local data assets exclusively upon application initialization — no network call is made to render the exercise list.
2. All guided audio files do not exceed a compressed size of 5MB each, to stay within local device storage constraints for crew who may not clear app cache between trips.
3. If network connectivity drops (`navigator.onLine == false`) mid-session, a localized "Offline Mode Active" banner renders cleanly instead of a spinning loader or application crash.

**US-102 — Fast Entry Under Time Pressure**
> As a Flight Attendant with a 4-minute window before boarding, I want the breathing exercise to start within one tap from the home screen, so that I can use the tool without burning my limited window on navigation.

Acceptance Criteria:
1. From app launch, the "Breathe & Box" / "IRROPS Grounding" action is reachable in a single tap — no intermediate screen, login, or confirmation dialog.
2. The exercise begins playback/animation within 500ms of tap on a cold app start.
3. A visible countdown/timer is present for the full duration of the exercise so the user can judge, mid-exercise, whether they have time to finish before boarding.

**US-103 — Session Interrupt Handling**
> As a crew member who gets called back to position mid-exercise, I want to be able to exit instantly without losing my place, so that an interruption doesn't feel like a failure or add friction to using the app again.

Acceptance Criteria:
1. A single, obvious exit action (not a multi-step "are you sure" flow) returns the user to the home screen from any point in an active exercise.
2. No error, crash, or data-loss state occurs if the app is backgrounded or force-closed mid-exercise.
3. Exiting early does not reset the user's local streak/usage state — partial use is still counted as a successful grounding session.

---

### Epic 2: Zero-Data Privacy Vault

**US-201 — No-Identity Onboarding**
> As a new user, I want to start using the app without creating an account tied to my identity, so that I can trust the tool before I trust the company with any data.

Acceptance Criteria:
1. The app is fully functional on first launch with zero required sign-up fields (no name, email, employee ID, or phone number collected).
2. No network call containing a device identifier, IP-linkable token, or advertising ID is made during onboarding.
3. All generated local state (streaks, preferences) is created with a random, non-reversible local identifier that never leaves the device.

**US-202 — On-Device Encrypted Storage**
> As a user, I want my usage history stored only on my device and encrypted at rest, so that no one — including Delta — can recover what I used the app for.

Acceptance Criteria:
1. All persisted user state is written to platform-native encrypted local storage (e.g., iOS Keychain/Secure Enclave-backed storage or Android EncryptedSharedPreferences) — never plaintext.
2. No usage analytics event is transmitted off-device without being fully stripped of any user- or device-identifying field.
3. Uninstalling the app permanently and irrecoverably deletes all local state — there is no server-side backup to restore from, by design.

**US-203 — Clear Privacy Disclosure**
> As a crew member evaluating whether to trust this tool, I want a plain-language explanation of exactly what is and isn't collected, so that I don't have to take "anonymous" on faith.

Acceptance Criteria:
1. A "What we collect" screen is reachable from the home screen in one tap and uses plain language, not legal boilerplate, as the primary explanation.
2. The disclosure explicitly states what is never collected (name, employee ID, GPS location, device identifiers) in addition to what is stored locally.
3. The screen is static content bundled with the app (no network fetch required) so it's available offline and can't be silently changed server-side without an app update.

---

### Epic 3: Anonymous Peer-to-Peer Bulletin Board

**US-301 — Anonymous Posting**
> As a delayed crew member, I want to post a short message to other crew without revealing who I am, so that I can feel supported without any risk to my professional record.

Acceptance Criteria:
1. Posting requires no identity field of any kind; posts are attributed only to a randomly generated, non-reversible session label (e.g., "Crew-4821") that resets periodically.
2. Message length is capped (e.g., 280 characters) and content is filtered against a moderation wordlist before being queued for sync.
3. A post made while offline is queued locally and clearly marked "Pending — will send when connected," never silently dropped.

**US-302 — Opportunistic Sync, Never Blocking**
> As a user on a spotty connection, I want the bulletin board to sync in the background without blocking the grounding tools, so that the app's core safety function is never degraded by a social feature.

Acceptance Criteria:
1. Bulletin board sync runs on a background thread/async task and never blocks or delays the Breathing Engine (Epic 1) from being tap-to-start.
2. If sync fails, the last successfully cached set of messages remains visible, with a "Last updated Xm ago" timestamp rather than an empty or error state.
3. Sync retries use backoff and never retry more than once per 30 seconds, to avoid battery/data drain on crew with limited connectivity windows.

**US-303 — Lightweight Moderation**
> As a crew member reading the board, I want assurance that posts are moderated, so that the space stays safe and doesn't become a liability or a source of additional stress.

Acceptance Criteria:
1. All posts pass through an automated keyword/toxicity filter before being visible to other users; flagged posts are held for review rather than published.
2. Users can report a visible post in one tap; a reported post is hidden from that reporting user's view immediately, pending review.
3. No report or moderation action is ever linked back to a real identity — moderation operates only on the anonymous session label.

---

### Epic 4: Wellness Toolkit — Layover Fitness & Meditation Library *(Phase 2)*

**US-401 — Browse Hotel-Room Workouts Offline**
> As a crew member on a layover with no gym access, I want to browse and play no-equipment workout routines without needing a connection, so that I can use the time in my hotel room productively even with no Wi-Fi.

Acceptance Criteria:
1. The Layover Fitness Library renders its full catalog from locally bundled assets on load — no network call required to browse or play a routine already downloaded with the app.
2. Routines are tagged by category ("Energy Reset," "Low-Impact," "Sleep-Prep Stretch") and filterable by duration (10/15/20 min) so a crew member can match content to the time they actually have.
3. If a routine's video asset hasn't been downloaded yet (future content-pack update), the UI clearly labels it "Download on Wi-Fi" rather than silently failing or showing a broken player.

**US-402 — Guided Meditation Without a Subscription**
> As a crew member who can't justify a $70/month wellness subscription on this income, I want free guided meditation content built into a tool I already trust, so that I get the same category of support without the cost barrier.

Acceptance Criteria:
1. The Meditation Library is reachable from the home dashboard in one tap, alongside — not buried under — the core grounding tools.
2. Each track displays runtime and category (Sleep, Jet Lag Reset, Pre-Flight Anxiety) before playback so the user can choose based on the time and need they actually have.
3. No paywall, trial-expiration, or upsell prompt appears anywhere in the flow — the product's free-vs-paid positioning is a hard requirement, not a soft default.

**US-403 — Content Storage Stays Within Device Limits**
> As a user with limited phone storage, I want the fitness and meditation libraries to respect sensible storage limits, so that CrewAnchor doesn't become the app I have to delete to make room for something else.

Acceptance Criteria:
1. Total bundled Phase 2 content (video + audio) does not exceed a defined device storage budget (e.g., 250MB) for the initial content pack.
2. Users can selectively delete downloaded content packs from a storage-management screen without losing their MVP-tier data (streaks, preferences, vault state).
3. New content-pack updates are opt-in (user-initiated download), never auto-downloaded over cellular data.
