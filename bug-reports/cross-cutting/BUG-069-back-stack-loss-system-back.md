# BUG-069 — Back-stack loss when pressing the system Back button

| Field | Value |
|---|---|
| **ID** | BUG-069 (Taiga #69) |
| **Module** | Cross-cutting |
| **Severity** | Major |
| **Priority** | Medium |
| **Type** | Functional |
| **Platform** | Android |
| **Build** | v1.0.8 |
| **Related requirement** | — |
| **Status** | Open |

## Preconditions
- User is authenticated
- On the date-selection step of trip creation (create trip / where / from already set with valid values)

## Steps to reproduce
1. Press the system Back button

## Actual result
The app minimises to background; resuming restarts the app from scratch instead of returning to the screen the user was on.

## Expected result
The user goes back to the previous screen (e.g. to change the destination).

## Environment
- Device: Xiaomi Redmi Note 10S, Android 13, MIUI 14
- App build: v1.0.8

## Notes
Reproduces on ALL screens of the app — broken Android back-navigation across the board.
