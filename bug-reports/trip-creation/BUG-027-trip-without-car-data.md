# BUG-027 — Trip Creation: a trip can be published without car data

| Field | Value |
|---|---|
| **ID** | BUG-027 (Taiga #27) |
| **Module** | Trip creation (Driver) |
| **Severity** | Major |
| **Priority** | High |
| **Type** | Functional / Business rule |
| **Platform** | Both |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-TRIP-01 (no car data → trip must not publish, draft kept blocked) |
| **Status** | Open |

## Preconditions
- User is signed in.
- The profile has **no car data** filled in.

## Steps to reproduce
1. Select the "I'm a driver" role.
2. Set "From" (e.g. Khujand).
3. Set "To" (e.g. Penjikent).
4. Choose a trip date.
5. Choose a departure time.
6. Choose the number of passengers.
7. Set a price per seat.
8. Leave the trip comment empty.
9. Tap "Publish trip".

## Actual result
The trip is created and published.

## Expected result
Per the defined publish rule, a trip must not be published while car data is missing. The draft should remain in a blocked/unpublishable state, must not disappear, and the user should see why publishing is blocked.

## Environment
- Device: Google Pixel 7
- OS: Android 17 Beta
- App build: v1.0.8

## Evidence
- `../../screenshots/BUG-027-vehicle-not-specified-published.png`

## Notes
- This is one of the few explicitly confirmed business rules (see app overview §4), which makes it a clear, defensible defect rather than an assumption.
