# BUG-089 — Edit profile: no "Name" validation; empty or over-long value can be saved

| Field | Value |
|---|---|
| **ID** | BUG-089 (Taiga #89) |
| **Module** | Profile |
| **Severity** | Minor |
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
1. Tap the "Name" field
2. Delete the current value and tap "Save"
3. Tap "Name" again, enter a very long value (e.g. 100 characters) and tap "Save"

## Actual result
No required/length validation: the profile saves with an empty value and with a value over the allowed length; no error is shown and the field is not highlighted.

## Expected result
Required and max-length validation runs on "Name"; an empty or over-long value blocks saving and shows an error.

## Environment
- App build: v1.0.8 (iPhone 14 Pro, iOS — same session as related profile reports)

## Evidence
- `../../screenshots/BUG-089-edit-profile-name-digits.png`

## Notes
See also IMP-098: in testing the field accepted up to 5000 characters.
