# BUG-079 — Trip Creation: app allows an under-18 (minor) driver to create a trip

| Field | Value |
|---|---|
| **ID** | BUG-079 (Taiga #79) |
| **Module** | Trip creation (Driver) |
| **Severity** | Critical |
| **Priority** | High |
| **Type** | Functional / Business rule |
| **Platform** | Both |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-PROF-06 (age ≥ 18) |
| **Status** | Open |

## Preconditions
- A user is registered with an age below 18 (test account created with age = 1 year).

## Steps to reproduce
1. Sign in as the under-age account.
2. Select the "I'm a driver" role.
3. Create a trip.

## Actual result
The trip is created. The app does not prevent an under-age user from publishing a trip as a driver.

## Expected result
A minor must not be able to create a trip as a driver. The app should block trip creation for under-18 users — ideally with driving-licence verification before a user is allowed to publish trips.

## Environment
- Device: multiple (reproduced on Android and iOS test accounts)
- App build: v1.0.8

## Notes
- Rated **Critical** despite a simple repro: a minor operating as a paid driver is a legal/safety exposure for a transport product, not a cosmetic issue.
- Closely related to validation gap **BUG-088** (profile allows saving age < 18) — same missing age rule, surfaced on a different screen. Fixing the underlying age validation should resolve both.
