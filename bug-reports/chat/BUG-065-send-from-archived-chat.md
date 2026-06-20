# BUG-065 — A message can be sent from a chat that is in the archive

| Field | Value |
|---|---|
| **ID** | BUG-065 (Taiga #65) |
| **Module** | Chat |
| **Severity** | Major |
| **Priority** | Medium |
| **Type** | Functional |
| **Platform** | Android |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-CHAT-01 |
| **Status** | Open |

## Preconditions
- An archived chat exists

## Steps to reproduce
1. Send a message from the archived chat

## Actual result
The message is sent.

## Expected result
Either sending from an archived chat is not possible, or sending moves the chat back from archive to active.

## Environment
- App build: v1.0.8 (Android; device not recorded in the original report)

## Evidence
- `../../screenshots/BUG-077-chat-files-not-viewable.png`
