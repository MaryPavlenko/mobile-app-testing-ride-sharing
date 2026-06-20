# BUG-045 — No validation on empty required "From"/"To" when creating a request

| Field | Value |
|---|---|
| **ID** | BUG-045 (Taiga #45) |
| **Module** | Home & Search |
| **Severity** | Major |
| **Priority** | Medium |
| **Type** | Validation |
| **Platform** | Android |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-HOME-04 |
| **Status** | Open |

## Preconditions
- Launch the app
- Log in
- Tap "+"

## Steps to reproduce
1. Driver: leave "From" empty, keep "No detail" selected, tap "Continue"; leave "To" empty, tap "Continue"
2. Passenger: leave "From" and "To" empty, tap "Create request"

## Actual result
Driver: "Continue" is clickable and each tap advances to the next step. Passenger: "Create request" is clickable.

## Expected result
Driver: "Continue" is disabled and does not advance. Passenger: "Create request" is disabled and shows "Fill in the required fields".

## Environment
- Device: POCO M3 Pro 5G, Android 13, MIUI 14.0.6
- App build: v1.0.8

## Evidence
- `../../screenshots/BUG-045-empty-from-continue-active.png`
- `../../screenshots/BUG-045-request-published-empty-to.png`
