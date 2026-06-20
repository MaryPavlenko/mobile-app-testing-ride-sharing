# BUG-025 — Opening a push does not navigate to the message/notification

| Field | Value |
|---|---|
| **ID** | BUG-025 (Taiga #25) |
| **Module** | Notifications |
| **Severity** | Major |
| **Priority** | Medium |
| **Type** | Functional |
| **Platform** | iOS |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-NOTIF-01 |
| **Status** | Open |

## Preconditions
- User is authenticated
- The user has received a push notification

## Steps to reproduce
1. Receive a push notification
2. Tap the push notification

## Actual result
The app opens but the user is not taken to the related message/notification.

## Expected result
Tapping a push takes the user to the related message, notification, chat or screen.

## Environment
- OS: iOS 26.4.2
- App build: v1.0.8
