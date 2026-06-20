# TC-AUTH-003 — Log in with valid credentials

| Field | Value |
|---|---|
| **Module** | Authorization / Login |
| **Type** | Positive, functional |
| **Priority** | High |
| **Requirement** | REQ-AUTH-04, REQ-HOME-01 |
| **Preconditions** | A confirmed account exists; user unauthenticated; internet available |

## Steps
| # | Action | Expected result |
|---|---|---|
| 1 | Open the app → Profile | "Log in to account" button shown |
| 2 | Tap "Log in to account" | Auth form shown |
| 3 | Enter the registered email and correct password | No validation errors |
| 4 | Tap "Log in" | User is authenticated; returned to the app |
| 5 | Open Home | Greeting includes the user's name (REQ-HOME-01) |
| 6 | Open "My Trips" and "Chat" | Both are accessible |

## Postconditions
- The session persists after an app restart (REQ-AUTH-05 inverse).
