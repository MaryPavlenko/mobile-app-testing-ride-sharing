# IMP-075 — Booking & rating enhancements

| Field | Value |
|---|---|
| **ID** | IMP-075 (Taiga #75) |
| **Module** | Booking |
| **Type** | Improvement (not a defect) |
| **Platform** | Both |
| **Status** | Proposed → [improvements backlog](../../requirements-docs/improvements-backlog.md) |

## Summary
A set of booking/reputation improvements raised during testing.

## Rationale
Improves trust signals and prevents double-booking confusion.

## Proposed behaviour
- Warn the user if they book several seats at the same date/time on different routes.
- Surface driver cancellation statistics (e.g. an "often cancels" flag), factoring in time-to-departure.
- Surface passenger reliability info for no-shows / lateness.
- Allow sorting trips by price (lower/higher).
- Allow editing a created trip at least within the same date (departure time, price, conditions) with notification to passengers about critical changes.

> Filed as an enhancement, not a defect: it does not contradict any defined MVP behaviour. Kept separate to keep the defect list honest.
