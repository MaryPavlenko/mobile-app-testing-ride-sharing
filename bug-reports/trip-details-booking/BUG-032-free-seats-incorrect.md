# BUG-032 — Incorrect number of free seats shown on the trip card

| Field | Value |
|---|---|
| **ID** | BUG-032 (Taiga #32) |
| **Module** | Trip details & booking |
| **Severity** | Major |
| **Priority** | High |
| **Type** | Data |
| **Platform** | iOS |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-BOOK-02 |
| **Status** | Open |

## Preconditions
- User is authenticated

## Steps to reproduce
1. Driver side — create a trip: Dushanbe — Khujand, today, 23:39, 200 TJS, with the condition "only 2 in the back" enabled, and all passengers confirmed
2. Launch the app → "My Trips" → tap the trip card
3. Passenger side — from another account, a trip for 3 passengers exists with "only 2 in the back" enabled and all passengers confirmed; find it via search and tap the card

## Actual result
Driver side: free seats shows 1 (should be 0). Passenger side: free seats shows 2 (should be 0).

## Expected result
Free-seat count reflects confirmed bookings and the seat conditions — 0 free seats in both cases.

## Environment
- OS: iOS 16.7.16
- App build: v1.0.8

## Evidence
- `../../screenshots/BUG-032-free-seats-incorrect.png`

## Notes
An inflated free-seat count lets a trip be over-booked, so although it is a display value it has a functional consequence.
