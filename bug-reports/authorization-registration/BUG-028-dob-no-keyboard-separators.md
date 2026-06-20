# BUG-028 — No separators on the keyboard for manual date-of-birth entry

| Field | Value |
|---|---|
| **ID** | BUG-028 (Taiga #28) |
| **Module** | Registration |
| **Severity** | Minor |
| **Priority** | Medium |
| **Type** | UI / Validation |
| **Platform** | Android |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-AUTH-02 |
| **Status** | Open |

## Preconditions
- App open
- Registration form open

## Steps to reproduce
1. Go to Profile → "Log in to account" → "Register"
2. Tap the "Date of birth" field
3. Choose manual (keyboard) entry
4. Try to enter a valid date, e.g. 12091990 for 12 September 1990

## Actual result
The numeric keyboard has no separator keys (/ or .), so a date cannot be entered in dd/mm/yyyy form.

## Expected result
Either the keyboard exposes separators, or the app auto-formats the input, or the field accepts a plain number (12091990) and parses it correctly.

## Environment
- Device: Samsung Galaxy A12
- Platform: Android
