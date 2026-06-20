# BUG-014 — My Trips (Driver): chosen date cannot be changed (date field inactive)

| Field | Value |
|---|---|
| **ID** | BUG-014 (Taiga #14) |
| **Module** | My Trips |
| **Severity** | Minor |
| **Priority** | Medium |
| **Type** | UI |
| **Platform** | Android |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-TRIP-03 |
| **Status** | Open |

## Preconditions
- HamSafar is open
- "My Trips" tab open, "I'm a driver" role
- Origin chosen (e.g. Dushanbe)
- Destination chosen (e.g. Khujand)

## Steps to reproduce
1. In the calendar pick a valid date, e.g. 20.05.2026
2. Tap the date field to change the date

## Actual result
The date field is inactive and does not respond to taps; the date can only be changed by going back.

## Expected result
The date field is active and lets the user change the trip date directly.

## Environment
- Device: Xiaomi Pad 6
- OS: Android 14 (UKQ1.240624.001)

## Notes
Also logged as a usability improvement: it is not intuitive that the user must go back to change a selected date.
