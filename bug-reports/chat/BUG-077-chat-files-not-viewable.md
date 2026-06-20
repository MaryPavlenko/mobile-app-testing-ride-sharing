# BUG-077 — Files sent in chat cannot be opened or viewed

| Field | Value |
|---|---|
| **ID** | BUG-077 (Taiga #77) |
| **Module** | Chat |
| **Severity** | Major |
| **Priority** | Medium |
| **Type** | Functional |
| **Platform** | Android |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-CHAT-01 |
| **Status** | Open |

## Preconditions
- User is authenticated
- A chat with another user exists
- Photos have been sent in the chat

## Steps to reproduce
1. Open the chat
2. Tap an attachment

## Actual result
The attachment cannot be opened, downloaded or interacted with at all.

## Expected result
An attachment opens and is available to view/download.

## Environment
- Device: Xiaomi Redmi Note 10S, Android 13, MIUI 14
- App build: v1.0.8

## Evidence
- `../../screenshots/BUG-077-chat-files-not-viewable.png`

## Notes
Reproduces for all chat roles, for both freshly added files in an active chat and files in archived chats.
