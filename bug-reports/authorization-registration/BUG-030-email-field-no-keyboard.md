# BUG-030 — During registration, tapping the Email field does not open the keyboard

| Field | Value |
|---|---|
| **ID** | BUG-030 (Taiga #30) |
| **Module** | Registration |
| **Severity** | Major |
| **Priority** | High |
| **Type** | Functional |
| **Platform** | Android |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-AUTH-02 |
| **Status** | Open |

## Preconditions
- Not logged in

## Steps to reproduce
1. Tap "Profile" → "Log in to account" → "Register"
2. Enter a name
3. Pick a date of birth
4. Tap the "Email" field

## Actual result
No keyboard appears for the Email field.

## Expected result
A keyboard appears for input.

## Environment
- Platform: Android (device not recorded in the original report)

## Notes
Intermittent (floating) defect; a workaround is that tapping the "Password" field opens a keyboard that can then be used for the email.
