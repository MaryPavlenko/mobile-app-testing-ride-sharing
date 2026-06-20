# BUG-064 — Left-swipe on a chat shows "Delete chat?" but archives it

| Field | Value |
|---|---|
| **ID** | BUG-064 (Taiga #64) |
| **Module** | Chat |
| **Severity** | Minor |
| **Priority** | Low |
| **Type** | UI / Functional |
| **Platform** | Android |
| **Build** | v1.0.8 |
| **Related requirement** | — |
| **Status** | Open |

## Preconditions
- User is authenticated
- At least one chat exists

## Steps to reproduce
1. Open the Chat list
2. Left-swipe a chat
3. Tap "Delete"

## Actual result
The swipe shows "Delete"; the chat is moved to the archive.

## Expected result
The swipe shows "Archive" and the chat is moved to the archive — label and action should match.

## Environment
- App build: v1.0.8 (Android; device not recorded in the original report)
