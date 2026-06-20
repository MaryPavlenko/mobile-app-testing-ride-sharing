# BUG-013 — My Trips (Driver): can proceed to destination without filling "From"

| Field | Value |
|---|---|
| **ID** | BUG-013 (Taiga #13) |
| **Module** | My Trips |
| **Severity** | Major |
| **Priority** | High |
| **Type** | Validation |
| **Platform** | Android |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-HOME-04 |
| **Status** | Open |

## Preconditions
- HamSafar is open
- "My Trips" tab is open
- "I'm a driver" role is selected

## Steps to reproduce
1. Leave the "From" field empty
2. Keep the "No detail" card selected
3. Tap "Continue"

## Actual result
The app navigates to destination selection ("Where to?"). No "Fill in the required field" error is shown.

## Expected result
Navigation to "Where to?" does not happen; a validation error such as "Fill in the required field" is shown.

## Environment
- Device: Xiaomi Pad 6
- OS: Android 14 (UKQ1.240624.001)