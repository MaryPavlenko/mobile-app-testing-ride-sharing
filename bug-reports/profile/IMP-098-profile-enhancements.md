# IMP-098 — Profile enhancements

| Field | Value |
|---|---|
| **ID** | IMP-098 (Taiga #98) |
| **Module** | Profile |
| **Type** | Improvement (not a defect) |
| **Platform** | Both |
| **Status** | Proposed → [improvements backlog](../../requirements-docs/improvements-backlog.md) |

## Summary
Improvements for the Profile / Edit profile screens.

## Rationale
Prevents unusable data and clarifies account behaviour.

## Proposed behaviour
- Cap the "Name" length (currently accepts up to ~5000 characters) and show a clear error past the limit.
- Clarify the business rule for changing email: whether changing the profile email changes the login email.

> Filed as an enhancement, not a defect: it does not contradict any defined MVP behaviour. Kept separate to keep the defect list honest.
