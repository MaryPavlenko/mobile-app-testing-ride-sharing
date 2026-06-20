# TC-TRIP-002 — Trip rejects identical origin and destination

| Field | Value |
|---|---|
| **Module** | Trip creation (Driver) |
| **Type** | Negative, business rule |
| **Priority** | Medium |
| **Requirement** | REQ-TRIP-04 |
| **Preconditions** | User authenticated; car data filled |

## Steps
| # | Action | Expected result |
|---|---|---|
| 1 | Start trip creation as a driver | Flow starts |
| 2 | Set "From" and "To" to the same city (and same meeting/arrival detail) | — |
| 3 | Complete date, time, seats, price | Steps accept input |
| 4 | Tap "Publish trip" | Publishing is blocked; message "Origin and destination cannot be the same" |

## Postconditions
- No trip with identical origin and destination is published.

## Notes
- **Current build fails this** (BUG-076): the trip publishes and even shows a computed travel time. The app is for intercity trips, so this is a rule violation.
