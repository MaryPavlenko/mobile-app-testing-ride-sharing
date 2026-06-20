# BUG-026 — Edit profile: keyboard does not close after phone entry and covers "Save"

| Field | Value |
|---|---|
| **ID** | BUG-026 (Taiga #26) |
| **Module** | Profile |
| **Severity** | Major |
| **Priority** | High |
| **Type** | UI |
| **Platform** | iOS |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-PROF-06 |
| **Status** | Open |

## Preconditions
- HamSafar is open
- Profile tab open
- "Edit profile" screen open

## Steps to reproduce
1. Tap the "Phone" field
2. Enter a valid number, e.g. +998 123456789
3. Try to dismiss the keyboard by tapping outside the field or using the keyboard confirm key

## Actual result
The keyboard does not close on tap-outside or confirm, it covers the "Save" button so changes cannot be saved, and the entered number is additionally shown under the user icon.

## Expected result
The keyboard closes, "Save" is reachable, the number appears only in the "Phone" field, and valid profile changes save successfully.

## Environment
- Device: iPhone 14 Pro
- OS: iOS 26.5
- App build: v1.0.8 (TestFlight build 10)

## Evidence
- `../../screenshots/BUG-026-keyboard-covers-save-phone.png`
