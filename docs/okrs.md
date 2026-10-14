# CrewAnchor: OKRs & Value-Realization Metrics

Connecting the product vision to measurable outcomes: every key result below is something that could be instrumented and tracked.

## Objective 1: Prove the "panic-to-grounded" loop works in the real operating environment
- **KR1:** 70%+ of users who start a grounding exercise complete it (not abandoned before the session timer ends)
- **KR2:** Median time from app launch to exercise start is under 15 seconds
- **KR3:** 0 crash or error-state reports tied to offline/airplane-mode usage in the first release

## Objective 2: Earn and keep crew trust on privacy
- **KR1:** 0 data-collection complaints or trust-related support tickets in first 90 days post-launch
- **KR2:** 100% of analytics events pass an automated PII-stripping check before transmission (CI-gated, not just policy)
- **KR3:** Voluntary opt-in rate to the "What we collect" disclosure screen used as a proxy for trust-seeking behavior (track views, not just completions)

## Objective 3: Build a self-sustaining peer support loop
- **KR1:** 30%+ of active users post or react on the bulletin board within their first week (community isn't just lurked, it's used)
- **KR2:** Average time-to-first-response on a new post under 10 minutes during peak IRROPS windows (storms, holidays)
- **KR3:** Moderation false-positive rate (legitimate posts incorrectly held) under 5%

## Why These Metrics, Not Others
Deliberately excluded: daily active users as a headline metric. A tool designed to be used in acute, hopefully-infrequent stress moments should not be optimized for daily engagement; that would be optimizing for the wrong outcome (more crew stress, not less). Completion rate and trust indicators are the honest signal of whether the product is doing its job.
