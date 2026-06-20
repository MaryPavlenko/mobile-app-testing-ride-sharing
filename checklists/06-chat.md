# Checklist #8 — Chat

Format: `check → expected result`. **⚠ Found:** links a check to a defect.
Related requirements: REQ-CHAT-01, REQ-CHAT-02.

## General
- The dialog list is sorted by last message (newest on top).
- Left-swipe moves a chat to the archive.
- Inside a chat: text, attachments (gallery photos), system messages, a "leave a review" banner for the passenger, and a pending-booking banner (Accept / Decline) for the driver.
- Tapping the partner's avatar/name in the header → their public profile.

## 1. Chat section — unauthenticated
- "Chats" opens on the chat icon.
- Header text "Messages. Chats and important trip events" is shown.
- "Archive" icon button is shown; tapping it opens the archive (visible to a guest, but specific chats appear only after login — open question OQ).
- Search bar with placeholder "Search chats" is shown.

## 2. Chat section — authenticated
- Same header, archive button, and search bar as above, available to the authenticated user.

## 3. Archive button — no archived chats
- Centre text "Archive is empty. Chats moved to the archive are kept here."
- A back arrow (top-left) returns to "Chat".

## 4. Archive button — with archived chats
- Archived dialogs sorted by last message.
- Moving a chat to the archive by left-swipe. **⚠ Found: BUG-064** (swipe shows "Delete" but archives).
- After all chats removed, "Archive is empty" is shown.
- A chat returns from the archive on right-swipe; it then appears in the "Chat" list; tapping it opens the chat.
- Sending a message from an archived chat. **⚠ Found: BUG-065.**
- Sending a message with 1 attachment. **⚠ Found: BUG-077** (attachments not viewable).
- Sending a message with 5 attachments — open question (no multi-select available).
- Open question: allowed file size/format.

## 5. Search bar
- Typing filters the list to chats whose title matches.

## 6. Chat list states
- Centre text "No active chats yet" when there are none.
- Dialogs sorted by last message.
- Archiving via swipe shows "No active chats yet"; tapping a chat opens it.
- Open question: documentation says left-swipe archives, but right-swipe also appears to archive here.

## 7. Open chat with a driver
- Header shows the profile name; tapping the name or photo opens the driver's public profile.
- A call button (📞) is shown; tapping it shows "Calls coming soon" (open question on expected behaviour).
- Trip date and route are shown at the top of the chat.
- Info message "Dialog created. Discuss the meeting point and trip details here."
- A "+" button (attachments), a text input with placeholder "Enter message" (placeholder disappears on typing), and a send button (▶️) are shown.

## Notes / gaps
- Could not create several trips to verify multiple chats at once.
- Unclear which action makes a chat appear (opening a trip without sending a message already creates a chat).
- **⚠ Found: BUG-022** — a chat disappears entirely after logging out and back in (regardless of archive state).
