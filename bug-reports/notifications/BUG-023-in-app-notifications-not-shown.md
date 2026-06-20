# BUG-023 — In-app notifications are not displayed

| Field | Value |
|---|---|
| **ID** | BUG-023 (Taiga #23) |
| **Module** | Notifications |
| **Severity** | Major |
| **Priority** | High |
| **Type** | Functional |
| **Platform** | Both |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-NOTIF-02 |
| **Status** | Open |

## Preconditions
- User is authenticated
- Notifications are enabled for the user

## Steps to reproduce
1. Trigger an event that generates a notification for the user
2. Receive the push on the device
3. Open the app
4. Go to the notifications section

## Actual result
The push arrives on the device, but the in-app notification counter does not update and the notification is missing from the in-app list.

## Expected result
After a push is received, the counter updates and the notification appears in the in-app notifications panel.

## Environment
- OS: iOS 26.4.2 (also reproduced on Xiaomi Redmi Note 10S, Android 13)
- App build: v1.0.8

## Evidence
- `../../screenshots/BUG-023-in-app-notification-not-shown.png` (personal data redacted)
