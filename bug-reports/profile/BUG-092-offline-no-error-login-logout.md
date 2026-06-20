# BUG-092 — Profile / login & logout: no error message when offline

| Field | Value |
|---|---|
| **ID** | BUG-092 (Taiga #92) |
| **Module** | Profile |
| **Severity** | Minor |
| **Priority** | Medium |
| **Type** | Network |
| **Platform** | Both |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-AUTH-05 |
| **Status** | Open |

## Preconditions
- HamSafar is open
- Device has no internet connection

## Steps to reproduce
1. Scenario 1 (login): disable internet, open Profile, tap "Log in to account", try to log in
2. Scenario 2 (logout): log in, disable internet, open Profile, tap "Log out"

## Actual result
On login without internet an infinite loading state is shown; no clear error message; the user cannot tell the action failed due to connectivity.

## Expected result
A clear "No internet connection" message is shown for both login and logout.

## Environment
- App build: v1.0.8 (device not recorded in the original report)
