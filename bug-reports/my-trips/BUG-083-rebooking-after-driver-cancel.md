# BUG-083 — Cannot re-book a previously confirmed-then-driver-cancelled booking

| Field | Value |
|---|---|
| **ID** | BUG-083 (Taiga #83) |
| **Module** | My Trips |
| **Severity** | Major |
| **Priority** | Medium |
| **Type** | Functional |
| **Platform** | Android |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-BOOK-03 |
| **Status** | Open |

## Preconditions
- The passenger has at least one booking that was confirmed and then cancelled by the driver
- User (passenger) is authenticated
- The list of bookable trips is open

## Steps to reproduce
1. Select the trip whose booking the driver previously cancelled
2. Book a seat

## Actual result
Booking is unavailable.

## Expected result
A new request is sent to the driver for that trip.

## Environment
- Device: Xiaomi Redmi Note 10S, Android 13, MIUI 14
- App build: v1.0.8

## Evidence
- `../../screenshots/BUG-083-rebook-cancelled-trip-error.png`
