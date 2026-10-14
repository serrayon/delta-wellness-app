# CrewAnchor: Stakeholder Map

A PO doesn't just own the backlog; they own the conversation between everyone who has a stake in what ships. This maps who those people are for CrewAnchor and what decision rights they'd actually have, using a RACI model (Responsible, Accountable, Consulted, Informed).

## RACI by Workstream

| Workstream | Product Owner | Engineering Lead | Design | Security/Privacy Review | Crew Advisory Group* |
|---|---|---|---|---|---|
| Backlog prioritization | **A/R** | C | C | C | C |
| User story & AC authoring | **A/R** | C | I | I | I |
| Sprint planning & ceremonies | **A/R** | R | I | I | n/a |
| Visual design / UI | C | I | **A/R** | I | C |
| Privacy architecture (Zero-Data Vault) | A | R | I | **A/R** | I |
| Bulletin board moderation policy | A | C | I | C | **A/R** |
| Release go/no-go | **A** | R | C | R | I |

*\*Crew Advisory Group: a small, rotating panel of actual flight attendants/pilots, not a real org yet, but the kind of stakeholder a PO would insist on having before launch, since no one on the engineering or design side has lived the IRROPS/reporting-anxiety problem firsthand.*

## Why This Matters (and why it's not just a chart)
Two rows are worth calling out because they're where a PO earns their keep, not where they rubber-stamp:

- **Privacy architecture is Accountable to the PO, Responsible to Engineering, but Security has A/R too.** That's deliberate; this isn't a normal feature where the PO just signs off on engineering's call. The Zero-Data Privacy Vault is the product's core trust promise, so any change to it needs a second accountable party (Security) who isn't optimizing for shipping speed, the same way the PO sometimes is.
- **The Crew Advisory Group owns moderation policy**, not engineering and not the PO alone. A PO who writes community moderation rules without input from the actual community they're moderating is guessing. This row exists specifically to prevent that guess.

## Escalation Path
When Engineering and Design disagree on a UI tradeoff, the PO is the tiebreaker, informed by acceptance criteria already written, not vibes. When Security and the PO disagree on a privacy tradeoff, Security wins by default; the product's entire value proposition is built on a trust promise that isn't the PO's to spend down for velocity.
