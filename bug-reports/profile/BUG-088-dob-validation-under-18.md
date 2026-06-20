# BUG-088 — Edit profile: no date-of-birth validation; age under 18 can be saved

| Field | Value |
|---|---|
| **ID** | BUG-088 (Taiga #88) |
| **Module** | Profile |
| **Severity** | Major |
| **Priority** | High |
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
1. Tap the "Date of birth" field
2. Pick a date giving an age under 18 (e.g. today's date)
3. Save the profile changes

## Actual result
A date giving age under 18 (including today's date) can be selected and saved with no validation error; "Save" stays enabled.

## Expected result
Age validation runs on "Date of birth"; a date giving age under 18 cannot be saved and an error is shown.

## Environment
- App build: v1.0.8 (iPhone 14 Pro, iOS — same session as related profile reports)

## Evidence
- `../../screenshots/BUG-088-edit-profile-dob-under-18.png` (personal data redacted)

## Notes
Same missing age rule as BUG-079 (minor can create a trip), surfaced on the profile screen. A single age-validation fix should resolve both.
