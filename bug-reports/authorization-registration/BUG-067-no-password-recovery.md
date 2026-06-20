# BUG-067 — No password-recovery functionality

| Field | Value |
|---|---|
| **ID** | BUG-067 (Taiga #67) |
| **Module** | Authorization |
| **Severity** | Major |
| **Priority** | High |
| **Type** | Functional / Missing feature |
| **Platform** | Both |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-AUTH-07 |
| **Status** | Open |

## Preconditions
- A user has forgotten / cannot recall their password

## Steps to reproduce
1. Look for a way to reset or recover the password from the auth screen

## Actual result
Password recovery is not implemented.

## Expected result
The user can reset/recover their password.

## Environment
- Platform: both (device not recorded in the original report)
- App build: v1.0.8

## Notes
Combined with the missing "show password" toggle (IMP-081), a single typo can lock a user out with no recovery path.
