# BUG-071 — Booking: a trip whose departure time has already passed can still be booked

| Field | Value |
|---|---|
| **ID** | BUG-071 (Taiga #71) |
| **Module** | Trip details & booking |
| **Severity** | Major |
| **Priority** | High |
| **Type** | Functional |
| **Platform** | Both |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-BOOK-04 (no booking after departure time) |
| **Status** | Open |

## Preconditions
- At least one trip exists whose departure time expired no more than ~35 minutes ago.
- That trip has at least one free seat and supports instant booking.
- A passenger is authenticated and on the list of bookable trips.

## Steps to reproduce
1. Select a trip whose departure time has already passed.
2. Book a seat.

## Actual result
Booking succeeds on an already-departed trip.

## Expected result
Booking should be unavailable for a trip whose departure time has passed.

## Environment
- Device: Xiaomi Redmi Note 10S (M2101K7BG)
- OS: Android 13 (API 33), MIUI Global 14.0.11.0
- App build: HamSafar 1.0.8

## Notes
- Found via exploratory testing around trip-state edge cases (see exploratory charter EXP-02). Time-based state is a common gap in MVPs, which is why this path was probed deliberately.
