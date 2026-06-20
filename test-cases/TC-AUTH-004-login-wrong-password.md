# TC-AUTH-004 — Login rejects a wrong password

| Field | Value |
|---|---|
| **Module** | Authorization / Login |
| **Type** | Negative, functional |
| **Priority** | High |
| **Requirement** | REQ-AUTH-04 |
| **Preconditions** | A confirmed account exists; user unauthenticated |

## Steps
| # | Action | Expected result |
|---|---|---|
| 1 | Open Profile → "Log in to account" | Auth form shown |
| 2 | Enter the registered email and a wrong password | No inline error yet |
| 3 | Tap "Log in" | Alert "Incorrect email or password"; user stays unauthenticated |
| 4 | Enter an unregistered email and any password, tap "Log in" | Alert "No user is registered with this email" |
| 5 | Enter an email without "@", tap "Log in" | Inline error "Invalid email"; request not sent |

## Postconditions
- No session is created; the form keeps the entered email.

## Notes
- Related gap: there is no password-recovery path (BUG-067) and no "show password" toggle (IMP-081), so a mistyped password cannot be self-corrected.
