# BUG-066 — Registration "Name" field accepts digits with no validation error

| Field | Value |
|---|---|
| **ID** | BUG-066 (Taiga #66) |
| **Module** | Registration |
| **Severity** | Minor |
| **Priority** | Medium |
| **Type** | Validation |
| **Platform** | Android |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-AUTH-02 |
| **Status** | Open |

## Preconditions
- App open, on the registration screen

## Steps to reproduce
1. Tap the "Name" field
2. Enter digits, e.g. "12345"
3. Tap register

## Actual result
The field accepts digits and registration completes.

## Expected result
A validation error such as "Invalid name format" / "Name must contain letters only".

## Environment
- Device: Samsung Galaxy A12
- Platform: Android

## Evidence
- `../../screenshots/BUG-066-registration-name-digits.png`
