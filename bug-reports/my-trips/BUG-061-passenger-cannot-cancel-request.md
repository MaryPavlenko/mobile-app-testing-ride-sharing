# BUG-061 — Passenger cannot cancel their trip request

| Field | Value |
|---|---|
| **ID** | BUG-061 (Taiga #61) |
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
- A trip request has been submitted

## Steps to reproduce
1. Go to "My Trips"
2. Tap the trip card

## Actual result
There is no "Cancel reservation" button on the trip card.

## Expected result
A "Cancel reservation" button is available at the bottom of the trip card.

## Environment
- OS: iOS 16.7.16 (reproduced on all test devices, incl. Xiaomi Redmi Note 10S, Android 13)
- App build: v1.0.8

## Notes
Critical and the mirror of BUG-058 on the passenger side: a passenger cannot withdraw a request, leaving stale reservations.
