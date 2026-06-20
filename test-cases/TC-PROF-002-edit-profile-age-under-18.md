# TC-PROF-002 — Edit profile rejects an age under 18

| Field | Value |
|---|---|
| **Module** | Profile / Edit profile |
| **Type** | Negative, validation |
| **Priority** | High |
| **Requirement** | REQ-PROF-06 |
| **Preconditions** | User authenticated; on the "Edit profile" screen |

## Steps
| # | Action | Expected result |
|---|---|---|
| 1 | Tap the "Date of birth" field | Date picker opens |
| 2 | Pick a date giving age under 18 (e.g. today's date) | — |
| 3 | Tap "Save" | Save is blocked; a validation error about the 18+ requirement is shown |
| 4 | Pick a date giving age ≥ 18, tap "Save" | Changes save successfully |

## Postconditions
- A profile cannot be saved with an under-18 date of birth.

## Notes
- **Current build fails this** (BUG-088); the same missing age rule lets a minor publish a trip (BUG-079). One age-validation fix should cover both.
