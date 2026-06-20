# BUG-068 — Inconsistent archive in/out logic for chats

| Field | Value |
|---|---|
| **ID** | BUG-068 (Taiga #68) |
| **Module** | Chat |
| **Severity** | Minor |
| **Priority** | Medium |
| **Type** | Functional |
| **Platform** | Android |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-CHAT-01 |
| **Status** | Open |

## Preconditions
- Trip chats exist

## Steps to reproduce
1. Left- and right-swipe chats to archive and delete them

## Actual result
Both the "Archive" and "Delete" swipes move a chat to the archive; in the archive, a "Delete" swipe removes the chat, but it reappears on the next entry into the archive.

## Expected result
A clear archive model (e.g. a chat for an unfinished trip cannot be archived or deleted).

## Environment
- App build: v1.0.8 (Android; device not recorded in the original report)
