# TC-PROF-001 — Guest cannot reach privacy & security settings

| Field | Value |
|---|---|
| **Module** | Profile / access control |
| **Type** | Negative, access control |
| **Priority** | High |
| **Requirement** | REQ-PROF-01 |
| **Preconditions** | User NOT authenticated |

## Steps
| # | Action | Expected result |
|---|---|---|
| 1 | Open the app without logging in | Guest state |
| 2 | Go to the Profile tab | Profile shows the "Log in to account" entry point |
| 3 | Attempt to open "Privacy and security" | Access is blocked for a guest (item hidden or gated behind login) |

## Postconditions
- Protected settings are unreachable without authentication.

## Notes
- **Current build fails this** (BUG-017): a guest can open and edit privacy settings. Found via exploratory charter EXP-01.
