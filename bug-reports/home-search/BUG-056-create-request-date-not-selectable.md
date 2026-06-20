# BUG-056 — "Create request": tapping the date field opens a calendar with no selectable date

| Field | Value |
|---|---|
| **ID** | BUG-056 (Taiga #56) |
| **Module** | Home & Search |
| **Severity** | Major |
| **Priority** | Medium |
| **Type** | Functional |
| **Platform** | Android |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-HOME-02 |
| **Status** | Open |

## Preconditions
- Open the app
- Tap "+"
- Tap the "I'm a passenger" card

## Steps to reproduce
1. Tap the date field

## Actual result
A calendar opens but no date can be selected.

## Expected result
A calendar opens that allows selecting a date.

## Environment
- Device: POCO M3 Pro 5G, Android 13, MIUI 14.0.6
- App build: v1.0.8

## Evidence
- `../../screenshots/BUG-056-create-request-empty-calendar.png`
