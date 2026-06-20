# IMP-099 — Add currency selection when the driver sets the price

| Field | Value |
|---|---|
| **ID** | IMP-099 (Taiga #99) |
| **Module** | Trip creation / Payment |
| **Type** | Improvement (not a defect) |
| **Platform** | Both |
| **Status** | Proposed → [improvements backlog](../../requirements-docs/improvements-backlog.md) |

## Summary
On the "Payment" step, currently the price can only be set in TJS; allow choosing the currency.

## Rationale
The app targets Tajikistan and Uzbekistan; Uzbekistan trips need UZS.

## Proposed behaviour
- At least TJS (Tajik somoni) and UZS (Uzbek sum) selectable.
- The chosen currency is shown in the price input, the "per 1 passenger" total, the trip card, search results and at booking.

> Filed as an enhancement, not a defect: it does not contradict any defined MVP behaviour. Kept separate to keep the defect list honest.
