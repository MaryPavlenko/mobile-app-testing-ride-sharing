# BUG-058 — Driver cannot cancel a trip

| Field | Value |
|---|---|
| **ID** | BUG-058 (Taiga #58) |
| **Module** | My Trips |
| **Severity** | Critical |
| **Priority** | High |
| **Type** | Functional |
| **Platform** | Both |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-BOOK-03 |
| **Status** | Open |

## Preconditions
- User is authenticated
- A trip has been created as a driver

## Steps to reproduce
1. Go to "My Trips"
2. Tap the trip card

## Actual result
There is no "Cancel trip" button at the bottom of the trip card.

## Expected result
A "Cancel trip" button is available at the bottom of the trip card.

## Environment
- OS: iOS 16.7.16 (also reproduced on Xiaomi Redmi Note 10S, Android 13)
- App build: v1.0.8

## Notes
Critical: a driver has no way to cancel a published trip, which breaks the core trip-management flow and leaves passengers booked on uncancellable trips.
