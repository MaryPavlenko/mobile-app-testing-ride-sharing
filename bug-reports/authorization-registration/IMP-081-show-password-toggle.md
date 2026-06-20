# IMP-081 — Add a "show password" toggle

| Field | Value |
|---|---|
| **ID** | IMP-081 (Taiga #81) |
| **Module** | Authorization |
| **Type** | Improvement (not a defect) |
| **Platform** | Android |
| **Status** | Proposed → [improvements backlog](../../requirements-docs/improvements-backlog.md) |

## Summary
Add a show/hide-password toggle on the password fields.

## Rationale
Without it, a single mistyped character blocks login; combined with the missing recovery flow (BUG-067) this hurts conversion.

## Proposed behaviour
- A "show password" toggle on the right of the password field, on login, registration and change-password screens.

> Filed as an enhancement, not a defect: it does not contradict any defined MVP behaviour. Kept separate to keep the defect list honest.
