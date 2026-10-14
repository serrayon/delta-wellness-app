# CrewAnchor: Definition of Done

A Definition of Done (DoD) is distinct from a story's Acceptance Criteria. Acceptance Criteria verify *this specific story* behaves correctly. The DoD is a blanket standard applied to *every* story before it can be marked complete; it's how a PO, an engineer, and QA all mean the same thing when they say "done," which is where a lot of sprint-review surprises actually come from when it's left unwritten.

## Every Story Must Satisfy All of the Following

**Code & Testing**
- [ ] Code is merged to the main branch, not sitting in an open PR
- [ ] Automated tests exist for the new behavior and are passing
- [ ] No existing test was broken or silently skipped to make this pass

**Acceptance Criteria**
- [ ] Every AC listed in the story has been manually verified against actual behavior, not just read and assumed correct
- [ ] The Product Owner has personally exercised the feature before marking it complete in the sprint board (not delegated to "QA said it's fine")

**CrewAnchor-Specific Standards** *(the product's own non-negotiables, beyond generic agile hygiene)*
- [ ] Works correctly with the device in Airplane Mode, for any feature touching the core grounding or privacy flows; this product's entire value proposition depends on offline reliability, so this is checked explicitly, not assumed from "it worked on my test network"
- [ ] No new network call was introduced that transmits a user-identifying or device-identifying field, checked against `docs/product-vision.md`'s privacy non-goals before merge, not after
- [ ] If the story touches the bulletin board, the moderation path was exercised, not just the happy path

**Review & Sign-off**
- [ ] Reviewed by at least one other engineer before merge
- [ ] UI changes were visually checked against the existing design system (colors, spacing, type) rather than approved on logic alone

## What "Done" Explicitly Does NOT Mean
- "Works on my machine": must be verified in the actual offline/airplane-mode condition the story claims to support
- "The happy path works": a story is not done if only the success case was tested and the failure/edge case from its AC was skipped
- "I'm pretty sure this doesn't break anything else": regression testing is part of done, not an assumption

## Why This Exists
Without a written DoD, "done" silently means something different to whoever's saying it; the engineer means "it compiles," QA means "it passed my test cases," the PO means "it does the thing I actually asked for." This document exists so that gap can't happen by default.
