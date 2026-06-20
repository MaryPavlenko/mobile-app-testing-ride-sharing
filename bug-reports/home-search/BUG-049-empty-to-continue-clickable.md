# BUG-049 — "Where to?": with an empty "To" field the "Continue" button is clickable

| Field | Value |
|---|---|
| **ID** | BUG-049 (Taiga #49) |
| **Module** | Home & Search |
| **Severity** | Major |
| **Priority** | Medium |
| **Type** | Validation |
| **Platform** | Android |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-HOME-04 |
| **Status** | Open |

## Preconditions
- Open the app
- Tap "+"
- Tap the "I'm a driver" card

## Steps to reproduce
1. Leave "To" empty
2. Tap "Continue"

## Actual result
"Continue" is clickable and advances to the next step (the "When?" calendar).

## Expected result
"Continue" is disabled.

## Environment
- Device: POCO M3 Pro 5G, Android 13, MIUI 14.0.6
- App build: v1.0.8

## Evidence
- `../../screenshots/BUG-049-empty-to-continue-active.png`
- `../../screenshots/BUG-049-empty-to-continue-active-dark.png`