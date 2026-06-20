# TC-TRIP-003 — Price field boundary and format validation

| Field | Value |
|---|---|
| **Module** | Trip creation (Driver) / Payment |
| **Type** | Negative, boundary value analysis |
| **Priority** | Medium |
| **Requirement** | REQ-TRIP-02, REQ-TRIP-05 |
| **Preconditions** | User authenticated; on the "Payment" step |

## Test data
| Case | Input | Expected |
|---|---|---|
| Below min | 0 | "Continue" disabled (invalid) |
| Min | 1 | Accepted |
| Max | 1000 | Accepted |
| Above max | 1001 | Capped at 1000 / rejected (see open question OQ-5) |
| Letters | "abc" | Not accepted |
| Decimal | "12.5" / "12,5" | Not accepted (OQ-21) |
| Special chars | "@#" | Not accepted |

## Steps
| # | Action | Expected result |
|---|---|---|
| 1 | Tap "Price per 1 passenger" | Cursor appears |
| 2 | Enter each value from the table | Behaviour matches the Expected column |
| 3 | Leave the field empty, check "Continue" | "Continue" is disabled |

## Postconditions
- Only a valid numeric price lets the flow continue.

## Notes
- Values above 1000 are silently capped at 1000 — flagged as open question OQ-5 (is 1000 really the max?). Currency is TJS-only on this screen (→ IMP-099).
