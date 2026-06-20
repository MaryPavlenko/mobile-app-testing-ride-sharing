# BUG-019 — Booking: "Send request" button hidden after focusing the message field

| Field | Value |
|---|---|
| **ID** | BUG-019 (Taiga #19) |
| **Module** | Trip details & booking |
| **Severity** | Critical |
| **Priority** | High |
| **Type** | Functional / UI |
| **Platform** | iOS |
| **Build** | v1.0.6, v1.0.8 |
| **Related requirement** | REQ-BOOK-03 (passenger can complete a booking) |
| **Status** | Open |

## Preconditions
- User is authenticated.
- A bookable trip is open.

## Steps to reproduce
1. Open the trip booking screen.
2. Go to the booking-details screen.
3. Tap the "message to driver" field.
4. Type a message.

## Actual result
Once the message field is focused, the "Send request" button stops being displayed. The user cannot dismiss the keyboard or reach the button, so the request — with a message — cannot be sent.

## Expected result
After typing a message the user should be able to dismiss the keyboard, see the "Send request" button, and successfully send the request together with the message to the driver.

## Environment
- OS: iOS 26.4.2
- App build: v1.0.6 and v1.0.8 (reproduced on both)

## Notes
- **Critical**: blocks completion of the core booking journey for any passenger who adds a message. Still present across two builds, which raises its priority.
