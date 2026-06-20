# TC-REVIEW-001 — A review cannot be submitted without a rating

| Field | Value |
|---|---|
| **Module** | Profile / Reviews |
| **Type** | Negative, validation |
| **Priority** | Medium |
| **Requirement** | REQ-PROF-04 |
| **Preconditions** | Trip completed; passenger took part; a chat with the driver exists; the "Leave a review" banner is shown |

## Steps
| # | Action | Expected result |
|---|---|---|
| 1 | Tap the "Leave a review" banner in the chat | The review form opens |
| 2 | Leave the rating unset, enter a comment only | — |
| 3 | Tap "Submit" | Submission is blocked; an error indicates a rating is required |
| 4 | Select a rating (1–5), tap "Submit" | The review submits with a success message |
| 5 | Re-open the form and submit again | The new review overwrites the old one (1 passenger — 1 review per trip); no duplicate is created |

## Postconditions
- Exactly one review exists for the passenger on that trip; it appears on the driver's public profile (author, rating, comment, date).

## Notes
- Boundary checks for the banner timer (first dismiss → reappears after 6h; second dismiss → gone for good) are covered in checklist #9.
