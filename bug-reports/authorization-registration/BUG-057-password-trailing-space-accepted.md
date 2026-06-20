# BUG-057 — Registration succeeds with a hidden special character (trailing space) in the password

| Field | Value |
|---|---|
| **ID** | BUG-057 (Taiga #57) |
| **Module** | Registration |
| **Severity** | Major |
| **Priority** | Medium |
| **Type** | Validation |
| **Platform** | Android |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-AUTH-02 |
| **Status** | Open |

## Preconditions
- App installed and launched
- User on the registration screen
- All other fields filled with valid data

## Steps to reproduce
1. In "Password" enter a valid 8–16 char value with a trailing space, e.g. "12345 "
2. Enter the same value with a trailing space in "Confirm password"
3. Tap "Register"
4. (Optional) try to log in with the password with and without the trailing space

## Actual result
Registration succeeds with a hidden trailing space stored in the password.

## Expected result
The app restricts/normalises hidden characters; registration completes only with a clean password using allowed characters.

## Environment
- Device: Samsung Galaxy A12
- Platform: Android

## Notes
A hidden trailing space silently breaks subsequent logins, since the user is unlikely to re-type the invisible character.
