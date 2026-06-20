# TC-SEARCH-002 — City field rejects invalid input

| Field | Value |
|---|---|
| **Module** | Home & Search |
| **Type** | Negative, equivalence partitioning |
| **Priority** | Medium |
| **Requirement** | REQ-HOME-02 |
| **Preconditions** | App open on Home |

## Test data (invalid partitions for "From" / "To")
| Partition | Example |
|---|---|
| Non-existent city | "Moscow" |
| Digits | "12345" |
| Special characters | "@$#" |

## Steps
| # | Action | Expected result |
|---|---|---|
| 1 | Tap "From", enter "Moscow" | Validation error; field not accepted as a valid city |
| 2 | Enter "12345" | Validation error |
| 3 | Enter "@$#" | Validation error |
| 4 | Repeat steps 1–3 for "To" | Validation error in each case |

## Postconditions
- Search cannot proceed with an invalid city.

## Notes
- **Current build fails this** across Home and the create-request screens — no error is shown (BUG-035…055). This test case is exactly what catches that cluster.
