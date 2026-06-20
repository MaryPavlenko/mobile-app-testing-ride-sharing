# IMP-101 — Verify a valid driving licence before allowing trip creation

| Field | Value |
|---|---|
| **ID** | IMP-101 (Taiga #101) |
| **Module** | Trip creation / Safety |
| **Type** | Improvement (not a defect) |
| **Platform** | Both |
| **Status** | Proposed → [improvements backlog](../../requirements-docs/improvements-backlog.md) |

## Summary
Require driving-licence verification before a user can publish trips as a driver.

## Rationale
No check is a safety risk for passengers and a reputational/liability risk if an unlicensed driver causes harm.

## Proposed behaviour
- On choosing the "I'm a driver" role for the first time, verify a valid driving licence before allowing trip creation.

> Filed as an enhancement, not a defect: it does not contradict any defined MVP behaviour. Kept separate to keep the defect list honest.
