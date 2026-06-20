# TC-TRIP-001 — Trip cannot be published without car data

| Field | Value |
|---|---|
| **Module** | Trip creation (Driver) |
| **Type** | Negative, business rule |
| **Priority** | High |
| **Requirement** | REQ-TRIP-01 |
| **Preconditions** | User authenticated; profile car data NOT filled |

## Steps
| # | Action | Expected result |
|---|---|---|
| 1 | Select the "I'm a driver" role | Trip-creation flow starts |
| 2 | Set From (Khujand), To (Penjikent), date, time, seats, price | Each step accepts valid input |
| 3 | Tap "Publish trip" | Publishing is blocked; the draft is kept in a blocked/unpublishable state and is not lost |
| 4 | Observe the screen | The reason "car data required" is visible to the user |
| 5 | Fill car data in the profile, return and publish | The trip publishes |

## Postconditions
- A trip is published only once car data exists.

## Notes
- **Current build fails this**: the trip publishes without car data (BUG-027). Related: weak car-field validation (BUG-091) lets car data be saved empty, undermining the rule from the other side.
