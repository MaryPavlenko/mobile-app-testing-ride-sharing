# BUG-095 — Profile / Suggest an idea: incorrect error on empty submit

| Field | Value |
|---|---|
| **ID** | BUG-095 (Taiga #95) |
| **Module** | Profile |
| **Severity** | Minor |
| **Priority** | Low |
| **Type** | UI / Copy |
| **Platform** | Both |
| **Build** | v1.0.8 |
| **Related requirement** | — |
| **Status** | Open |

## Preconditions
- HamSafar is open
- "Suggest an idea" screen open

## Steps to reproduce
1. Leave the idea field empty
2. Tap "Send idea"

## Actual result
The idea is not sent and the message "Describe the problem before sending" is shown — copy that belongs to the support screen, not the "Suggest an idea" screen.

## Expected result
An error matching the current screen, e.g. "Describe the idea before sending"; the idea is not sent until the required field is filled.

## Environment
- App build: v1.0.8 (iPhone 14 Pro, iOS — same session as related profile reports)

## Evidence
- `../../screenshots/BUG-095-suggest-idea-wrong-error.png`
