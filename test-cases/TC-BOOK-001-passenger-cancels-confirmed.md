# TC-BOOK-001 — Passenger cancels a confirmed booking → driver push

| Field | Value |
|---|---|
| **Module** | Trip details & booking |
| **Type** | Positive, functional (two-account) |
| **Priority** | High |
| **Requirement** | REQ-BOOK-03 |
| **Preconditions** | Driver account with a published trip; passenger account; the passenger's booking has been confirmed by the driver |

## Steps
| # | Action | Expected result |
|---|---|---|
| 1 | As the passenger, open the confirmed trip in "My Trips" → Active | Trip card shows a confirmed status |
| 2 | Tap the trip card and find "Cancel reservation" | The cancel control is available at the bottom of the card |
| 3 | Cancel the reservation | Status changes to "Cancelled" |
| 4 | On the driver account, check notifications | A push about the cancellation is received |
| 5 | On the driver trip, check seats | The freed seat returns to available |
| 6 | On the passenger account, open "My Trips" → Archive | The cancelled booking is recorded there |

## Postconditions
- Seat availability and both users' "My Trips" reflect the cancellation consistently.

## Notes
- **Current build fails this** at step 2: the passenger has no "Cancel reservation" control (BUG-061); the driver side has the mirror gap (BUG-058).
