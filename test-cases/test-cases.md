# Test Cases

Detailed, step-by-step test cases for the critical paths — the depth layer beneath the [checklists](../checklists/). Each carries preconditions, test data, an expected result per step, postconditions and notes. Negative cases dominate by design, and many are tied to a real defect they would catch (noted as **Current build fails this — BUG-NNN**).

> **Why a README sits in this folder:** GitHub renders a folder's `README.md` as its front page, so this is the index for the cases below.

| ID | Title | Module | Type |
|---|---|---|---|
| [TC-AUTH-001](TC-AUTH-001-registration-valid.md) | Successful registration with valid data | Authorization | Positive |
| [TC-AUTH-002](TC-AUTH-002-password-length-boundary.md) | Registration rejects out-of-range password length | Authorization | Negative / boundary |
| [TC-AUTH-003](TC-AUTH-003-login-valid.md) | Log in with valid credentials | Authorization | Positive |
| [TC-AUTH-004](TC-AUTH-004-login-wrong-password.md) | Login rejects a wrong password | Authorization | Negative |
| [TC-SEARCH-001](TC-SEARCH-001-valid-route.md) | Search a valid route returns results | Home & Search | Positive |
| [TC-SEARCH-002](TC-SEARCH-002-city-field-invalid-input.md) | City field rejects invalid input | Home & Search | Negative |
| [TC-TRIP-001](TC-TRIP-001-no-car-data-blocks-publish.md) | Trip cannot be published without car data | Trip creation | Negative / business rule |
| [TC-TRIP-002](TC-TRIP-002-same-origin-destination.md) | Trip rejects identical origin and destination | Trip creation | Negative / business rule |
| [TC-TRIP-003](TC-TRIP-003-price-field-boundary.md) | Price field boundary and format validation | Trip creation | Negative / boundary |
| [TC-BOOK-001](TC-BOOK-001-passenger-cancels-confirmed.md) | Passenger cancels a confirmed booking → driver push | Booking | Positive |
| [TC-BOOK-002](TC-BOOK-002-past-departure-blocked.md) | Booking is blocked on an already-departed trip | Booking | Negative / time boundary |
| [TC-PROF-001](TC-PROF-001-guest-privacy-blocked.md) | Guest cannot reach privacy & security settings | Profile | Negative / access control |
| [TC-PROF-002](TC-PROF-002-edit-profile-age-under-18.md) | Edit profile rejects an age under 18 | Profile | Negative / validation |
| [TC-REVIEW-001](TC-REVIEW-001-no-rating-blocked.md) | A review cannot be submitted without a rating | Reviews | Negative / validation |

**Coverage:** 14 cases — 3 positive, 11 negative; 8 of the negatives map to confirmed defects, so the suite doubles as a regression set for those fixes.
