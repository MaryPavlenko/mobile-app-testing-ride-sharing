# BUG-029 — Hard birth-year limits (1940–2010) with no user feedback

| Field | Value |
|---|---|
| **ID** | BUG-029 (Taiga #29) |
| **Module** | Registration |
| **Severity** | Minor |
| **Priority** | Low |
| **Type** | UI / Validation |
| **Platform** | Android |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-AUTH-02 |
| **Status** | Open |

## Preconditions
- App launched, user not authenticated
- Registration form open

## Steps to reproduce
1. Tap the "Date of birth" field
2. Calendar: try to scroll the year list below 1940 or above 2010
3. Manual entry: enter a year outside the range (e.g. 1939 or 2011) and continue

## Actual result
The calendar year is hard-limited to 1940–2010; out-of-range manual years are blocked silently with no explanation.

## Expected result
If an age range is a requirement, the user sees a clear message about the allowed range; valid users below/above the current bounds (e.g. passport holders under 16, users over ~86) can still register.

## Environment
- Device: Samsung Galaxy A12
- Platform: Android
