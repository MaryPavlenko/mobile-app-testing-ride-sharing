# BUG-090 — Edit profile: no email validation; invalid value can be saved

| Field | Value |
|---|---|
| **ID** | BUG-090 (Taiga #90) |
| **Module** | Profile |
| **Severity** | Major |
| **Priority** | Medium |
| **Type** | Validation |
| **Platform** | iOS |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-PROF-06 |
| **Status** | Open |

## Preconditions
- HamSafar is open
- User is authenticated
- "Edit profile" screen open

## Steps to reproduce
1. Tap the "Email" field
2. Enter an invalid value (e.g. test, 12345, test@, test.com) and tap "Save"
3. Clear the field and tap "Save"

## Actual result
Any value can be entered without email-format checking; the profile saves with an invalid email, and also saves with an empty email; no validation error is shown.

## Expected result
Required and email-format validation runs on the "Email" field.

## Environment
- App build: v1.0.8 (iPhone 14 Pro, iOS — same session as related profile reports)

## Evidence
- `../../screenshots/BUG-088-edit-profile-dob-under-18.png`
