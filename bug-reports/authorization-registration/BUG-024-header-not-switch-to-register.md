# BUG-024 — Header "Log in" does not change to "Register" when switching to registration

| Field | Value |
|---|---|
| **ID** | BUG-024 (Taiga #24) |
| **Module** | Authorization |
| **Severity** | Minor |
| **Priority** | Low |
| **Type** | UI |
| **Platform** | iOS |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-AUTH-01 |
| **Status** | Open |

## Preconditions
- User is not authenticated

## Steps to reproduce
1. Go to Profile
2. Tap "Log in to account"
3. Tap "Register"

## Actual result
The header still reads "Log in".

## Expected result
The header changes from "Log in" to "Register".

## Environment
- OS: iOS 16.7.16
- App build: v1.0.8

## Evidence
- `../../screenshots/BUG-024-header-not-switch-signup.png` (personal data redacted)
