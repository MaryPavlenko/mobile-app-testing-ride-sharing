# TC-SEARCH-001 — Search a valid route returns results

| Field | Value |
|---|---|
| **Module** | Home & Search |
| **Type** | Positive, functional |
| **Priority** | High |
| **Requirement** | REQ-HOME-02 |
| **Preconditions** | User authenticated; internet available; at least one published trip on the route |

## Test data
- From: Dushanbe · To: Khujand · Date: a future date

## Steps
| # | Action | Expected result |
|---|---|---|
| 1 | On Home, tap "From" and select Dushanbe | City selected and shown |
| 2 | Tap "To" and select Khujand | City selected and shown |
| 3 | Tap the date field and pick a future date | Date selected and shown |
| 4 | Tap "Search" | Matching trips are listed (or an empty-catalogue state if none) |
| 5 | Sort results by departure date | Results reorder correctly |

## Postconditions
- No state change to the account; opening a result shows trip details consistent with the list.
