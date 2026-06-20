# BUG-022 — Chat message disappears on re-entering the chat via the "Questions?" button

| Field | Value |
|---|---|
| **ID** | BUG-022 (Taiga #22) |
| **Module** | Chat |
| **Severity** | Major |
| **Priority** | Medium |
| **Type** | Functional / Data |
| **Platform** | iOS |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-CHAT-01 |
| **Status** | Open |

## Preconditions
- User is authenticated
- A trip has been found

## Steps to reproduce
1. Open the trip card
2. Tap the "Questions? … will answer!" button
3. Send a prepared greeting message to the chat
4. Tap the back arrow (top-left)
5. Tap the "Questions? … will answer!" button again

## Actual result
After 2–3 seconds the message disappears from the chat; on re-entering, the message reappears in the input field instead of the thread.

## Expected result
The message stays in the chat thread.

## Environment
- OS: iOS 16.7.16
- App build: v1.0.8
