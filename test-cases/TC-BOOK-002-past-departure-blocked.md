# TC-BOOK-002 — Booking is blocked on an already-departed trip

| Field | Value |
|---|---|
| **Module** | Trip details & booking |
| **Type** | Negative, time boundary |
| **Priority** | High |
| **Requirement** | REQ-BOOK-04 |
| **Preconditions** | A trip exists whose departure time passed recently; it has a free seat and instant booking; passenger authenticated |

## Steps
| # | Action | Expected result |
|---|---|---|
| 1 | Open the list of bookable trips | The list loads |
| 2 | Select the trip whose departure has already passed | Trip details open |
| 3 | Attempt to book a seat | Booking is unavailable (button disabled or an explanatory message) |

## Postconditions
- No booking is created for an already-departed trip.

## Notes
- **Current build fails this** (BUG-071): booking succeeds on a departed trip. Surfaced via exploratory charter EXP-02.
