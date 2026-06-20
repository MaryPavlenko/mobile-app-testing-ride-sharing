# BUG-086 — Push notifications are not shown while using the app

| Field | Value |
|---|---|
| **ID** | BUG-086 (Taiga #86) |
| **Module** | Notifications |
| **Severity** | Major |
| **Priority** | Medium |
| **Type** | Functional |
| **Platform** | Android |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-NOTIF-01 |
| **Status** | Open |

## Preconditions
- User (driver) is not authenticated
- The user has at least one trip and at least one booking request awaiting confirmation

## Steps to reproduce
1. Log in
2. Trigger / await a booking request and watch for a push

## Actual result
Push notifications are not delivered while the app is in use.

## Expected result
On receiving a request, a push notification appears in the notification shade.

## Environment
- Device: Xiaomi Redmi Note 10S, Android 13, MIUI 14
- App build: v1.0.8

## Evidence
- `../../screenshots/BUG-086-push-not-shown-permissions-on.png`
