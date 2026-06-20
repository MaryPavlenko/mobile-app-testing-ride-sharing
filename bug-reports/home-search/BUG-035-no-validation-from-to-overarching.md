# BUG-035 — No validation on "From"/"To" on Home and in request creation (both roles)

| Field | Value |
|---|---|
| **ID** | BUG-035 (Taiga #35) |
| **Module** | Home & Search |
| **Severity** | Major |
| **Priority** | High |
| **Type** | Validation |
| **Platform** | Android |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-HOME-02 |
| **Status** | Open |

## Preconditions
- Launch the app
- Go to Profile and log in

## Steps to reproduce
1. On Home, tap "From" and enter invalid data (non-existent city e.g. "Moscow"; digits e.g. "Moscow45"; special chars e.g. "Mosco@")
2. Repeat for "To"
3. Tap "+" → "I'm a driver" and repeat the invalid inputs on the create-trip city fields
4. Repeat for the "I'm a passenger" create-request fields

## Actual result
None of the invalid inputs (non-existent city / digits / special characters) raise a validation error across Home and the create-request flows in either role.

## Expected result
Each invalid input raises a clear validation error and blocks progression.

## Environment
- Device: POCO M3 Pro 5G, Android 13, MIUI 14.0.6
- App build: v1.0.8

## Notes
Umbrella report for the city-field validation gap; BUG-036…056 document each specific case. The whole cluster shares one root cause.
