# BUG-080 — No explicit countdown to the next allowed registration attempt

| Field | Value |
|---|---|
| **ID** | BUG-080 (Taiga #80) |
| **Module** | Registration |
| **Severity** | Minor |
| **Priority** | Low |
| **Type** | UI / Copy |
| **Platform** | Android |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-AUTH-02 |
| **Status** | Open |

## Preconditions
- User not registered, several failed registration attempts already made
- Registration page open with valid values

## Steps to reproduce
1. Trigger another registration attempt after the lockout

## Actual result
"Too many attempts. Wait a bit and try again." — with no countdown timer.

## Expected result
"Too many attempts. Time until next attempt: (countdown)".

## Environment
- Device: Xiaomi Redmi Note 10S, Android 13, MIUI 14
- App build: v1.0.8

## Evidence
- `../../screenshots/BUG-080-no-countdown-next-attempt.png`

## Notes
Without a countdown the user does not know how long to wait; each new failed attempt appears to reset the wait.
