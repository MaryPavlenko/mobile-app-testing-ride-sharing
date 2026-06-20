# IMP-016 — Improve the unauthenticated-user flow

| Field | Value |
|---|---|
| **ID** | IMP-016 (Taiga #16) |
| **Module** | Cross-cutting / Onboarding |
| **Type** | Improvement (not a defect) |
| **Platform** | iOS |
| **Status** | Proposed → [improvements backlog](../../requirements-docs/improvements-backlog.md) |

## Summary
Two alternative UX approaches for guests on "My Trips" and "Add trip".

## Rationale
Today guests can tap into flows they cannot complete, causing confusion and dead-ends.

## Proposed behaviour
- Option A: show "My Trips" and "Add trip" (the central "+") in a disabled state (dark-grey, non-tappable) so the need to log in is obvious.
- Option B: let a guest walk the flow up to the final step, then show "Only a registered user can create requests and trips" with a route to login — preserving entered data and returning the user to the unfinished flow after sign-in.

> Filed as an enhancement, not a defect: it does not contradict any defined MVP behaviour. Kept separate to keep the defect list honest.
