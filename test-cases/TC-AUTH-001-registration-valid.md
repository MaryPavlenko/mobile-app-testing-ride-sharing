# TC-AUTH-001 — Successful registration with valid data

| Field | Value |
|---|---|
| **Module** | Authorization / Registration |
| **Type** | Positive, functional |
| **Priority** | High |
| **Requirement** | REQ-AUTH-02, REQ-AUTH-03 |
| **Preconditions** | App installed; user unauthenticated; internet available; an email inbox the tester can access |

## Test data
| Field | Value |
|---|---|
| Name | Latin/Cyrillic letters only, e.g. "Test User" |
| Email | a real, unused address |
| Date of birth | a date giving age ≥ 18 |
| Password | 8–16 chars, e.g. `Qa!2026xx` |
| Confirm password | same as password |

## Steps

| # | Action | Expected result |
|---|---|---|
| 1 | Open the app → Profile | "Log in to account" button is shown |
| 2 | Tap "Log in to account" → "Register" | Registration form is shown |
| 3 | Enter the valid test data in all fields | No validation errors appear |
| 4 | Tap "Register" | User is registered; an email-confirmation alert appears with a code input |
| 5 | Open the inbox, copy the confirmation code | Code received |
| 6 | Enter the valid code | "Email confirmed. Welcome, <name>"; user is authenticated |

## Postconditions
- The account exists and is confirmed.
- Home screen greeting now includes the user's name (REQ-HOME-01).

## Notes
- Known defects observed on this path during execution: date-of-birth keyboard separators (BUG-028) and auth instability on certain builds — re-verify against the current build before treating a failure as new.
