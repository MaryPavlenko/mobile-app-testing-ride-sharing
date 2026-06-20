# BUG-100 — No permission prompt on the first chat attachment

| Field | Value |
|---|---|
| **ID** | BUG-100 (Taiga #100) |
| **Module** | Chat |
| **Severity** | Minor |
| **Priority** | Low |
| **Type** | Functional |
| **Platform** | Android |
| **Build** | v1.0.8 |
| **Related requirement** | — |
| **Status** | Open |

## Preconditions
- A chat with no attachments yet is open

## Steps to reproduce
1. Tap "+" next to "Enter message"

## Actual result
The file picker opens directly.

## Expected result
A permission pop-up requesting access to add a file appears first.

## Environment
- Device: Google Pixel 7
- OS: Android 17 Beta
