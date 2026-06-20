# TC-AUTH-002 — Registration rejects out-of-range password length

| Field | Value |
|---|---|
| **Module** | Authorization / Registration |
| **Type** | Negative, boundary value analysis |
| **Priority** | High |
| **Requirement** | REQ-AUTH-02 (password 8–16 characters) |
| **Preconditions** | App installed; user unauthenticated; on the registration form; all other fields valid |

## Test data (boundaries around 8–16)
| Case | Length | Expected |
|---|---|---|
| Below min | 7 | Rejected: "Password too short. Must be 8–16 characters." |
| Min | 8 | Accepted |
| Max | 16 | Accepted |
| Above max | 17 | Rejected: "Password too long. Must be 8–16 characters." |

## Steps
| # | Action | Expected result |
|---|---|---|
| 1 | Open Profile → "Log in to account" → "Register" | Registration form shown |
| 2 | Fill all other fields with valid data | No errors |
| 3 | Enter a 7-character password and confirmation, tap "Register" | Border turns red; "Password too short. Must be 8–16 characters."; registration blocked |
| 4 | Replace with an 8-character password, tap "Register" | Accepted (proceeds to email confirmation) |
| 5 | Repeat with 16 characters | Accepted |
| 6 | Repeat with 17 characters | Border turns red; "Password too long. Must be 8–16 characters."; registration blocked |

## Postconditions
- No account is created for the rejected (7 / 17) cases.

## Notes
- Pairs with BUG-057 (a trailing space is accepted in the password): length is validated, hidden whitespace is not.
