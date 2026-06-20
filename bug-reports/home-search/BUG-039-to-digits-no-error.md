# BUG-039 — Home: entering digits in "To" raises no error message

| Field | Value |
|---|---|
| **ID** | BUG-039 (Taiga #39) |
| **Module** | Home & Search |
| **Severity** | Minor |
| **Priority** | Medium |
| **Type** | Validation |
| **Platform** | Android |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-HOME-02 |
| **Status** | Open |

## Preconditions
- Open the app

## Steps to reproduce
1. Tap the "To" field
2. Enter digits, e.g. "12345"

## Actual result
No error/validation message appears.

## Expected result
A validation/error message appears.

## Environment
- Device: POCO M3 Pro 5G, Android 13, MIUI 14.0.6
- App build: v1.0.8
