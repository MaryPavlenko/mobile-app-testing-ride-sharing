# IMP-074 — Gender-based filtering for safety

| Field | Value |
|---|---|
| **ID** | IMP-074 (Taiga #74) |
| **Module** | Booking |
| **Type** | Improvement (not a defect) |
| **Platform** | Both |
| **Status** | Proposed → [improvements backlog](../../requirements-docs/improvements-backlog.md) |

## Summary
Let drivers set a preferred passenger gender and let passengers filter drivers by gender.

## Rationale
Personal-safety preference relevant for female drivers/passengers; culturally relevant for the target markets.

## Proposed behaviour
- A driver profile setting for preferred passenger gender, used in matching.
- A passenger option to choose a driver by gender at booking.
- When the filter is on, show only matching drivers and honestly warn that wait time may increase.
- Keep it optional and non-blocking for users who do not need it.

> Filed as an enhancement, not a defect: it does not contradict any defined MVP behaviour. Kept separate to keep the defect list honest.
