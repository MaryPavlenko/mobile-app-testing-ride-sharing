# Deriving Requirements From Chaos

The most realistic part of this project: there was **no specification, no Figma, no acceptance criteria**. The only "source of truth" was a team chat — questions, partial answers, and "we'll work it out as we go." This is common in startups and is exactly the situation where a tester has to *create* the baseline rather than test against one.

This document explains the method I used and lists the testable requirements I extracted. Those requirement IDs (`REQ-*`) are referenced from checklists, test cases, defects and the [traceability matrix](../test-design/traceability-matrix.md).

## Method

1. **Read the entire communication history** and separated three kinds of statements: confirmed behaviour, undefined behaviour, and enhancement ideas.
2. **Turned confirmed behaviour into atomic, testable requirements** — each one verifiable as pass/fail.
3. **Logged everything undefined as an explicit question** rather than guessing, so testing wouldn't silently invent acceptance criteria ([open-questions.md](open-questions.md)).
4. **Routed "nice to have" ideas to a separate backlog** so they wouldn't be filed as defects ([improvements-backlog.md](improvements-backlog.md)).
5. **Validated assumptions against the running app** and against the database where access allowed, instead of trusting the chat alone.

This is the same discipline I used for a decade in UX research: when the brief is ambiguous, the job is to make the ambiguity visible and structured, not to paper over it.

## Derived requirements

Status legend: **Confirmed** = stated and/or verified · **Assumed** = strongly implied, treated as baseline · **Open** = behaviour undefined (see open questions).

### Authentication & account

| ID | Requirement | Status |
|---|---|---|
| REQ-AUTH-01 | An unauthenticated user can open Profile and see a "Log in" entry point. | Confirmed |
| REQ-AUTH-02 | Registration requires name, email, date of birth and a password of 8–16 characters; invalid input is flagged inline (red border + message). | Confirmed |
| REQ-AUTH-03 | Email must be confirmed via a code sent to the registered address before access is granted. | Confirmed |
| REQ-AUTH-04 | A registered user can be a Driver or a Passenger within one account. | Confirmed |
| REQ-AUTH-05 | Logout returns the user to the auth/home screen and removes access to chat and My Trips. | Confirmed |
| REQ-AUTH-06 | Logging in on a second device does not log the first device out; data is carried over. | Confirmed (flagged as security risk) |
| REQ-AUTH-07 | Password recovery must exist (request → email → reset → sign in with new password). | Open / missing in build |

### Home & search

| ID | Requirement | Status |
|---|---|---|
| REQ-HOME-01 | Logged-out home shows a plain greeting; logged-in home appends the user's name. | Confirmed |
| REQ-HOME-02 | "Where from" / "Where to" accept only valid cities in Uzbekistan/Tajikistan; digits, special characters and non-existent cities must raise a validation error. | Confirmed |
| REQ-HOME-03 | An unauthenticated user attempting to search must be told to authenticate (the app must "complain"), not spin indefinitely. | Confirmed |
| REQ-HOME-04 | Required origin/destination fields must be validated before the user can proceed. | Confirmed |

### Trip creation (Driver)

| ID | Requirement | Status |
|---|---|---|
| REQ-TRIP-01 | A trip cannot be published if car data is missing; the draft is preserved in a blocked state with a visible reason. | Confirmed |
| REQ-TRIP-02 | The driver sets the price; it is shown on the trip card and in details. | Confirmed |
| REQ-TRIP-03 | A published trip cannot be edited, only cancelled. | Confirmed |
| REQ-TRIP-04 | Origin and destination must differ. | Assumed |
| REQ-TRIP-05 | Price field bounds (min/max/zero/decimals) and currency source. | Open |

### Trip details & booking

| ID | Requirement | Status |
|---|---|---|
| REQ-BOOK-01 | The trip card shows driver avatar, name and rating, with tap-through to the public profile. | Confirmed |
| REQ-BOOK-02 | The trip card shows car, conditions, price, free seats, pickup and destination. | Confirmed |
| REQ-BOOK-03 | A passenger can cancel a confirmed booking; the other party receives a push. | Confirmed |
| REQ-BOOK-04 | Booking must not be possible for a trip whose departure time has already passed. | Assumed |
| REQ-BOOK-05 | Whether a passenger can cancel an unconfirmed request, and whether the driver is notified. | Open |

### My Trips

| ID | Requirement | Status |
|---|---|---|
| REQ-MYTRIPS-01 | My Trips separates requests, active trips and archive. | Confirmed |
| REQ-MYTRIPS-02 | Trip counts shown in the profile header must match the user's statistics. | Confirmed |

### Chat

| ID | Requirement | Status |
|---|---|---|
| REQ-CHAT-01 | After booking, a chat with the driver is available, containing a call button. | Confirmed |
| REQ-CHAT-02 | The phone number is not shown on the trip card; calls use the real number without masking. | Confirmed |
| REQ-CHAT-03 | Chat creation timing (automatic on booking?) and call-button availability stage. | Open |

### Profile, rating & reviews

| ID | Requirement | Status |
|---|---|---|
| REQ-PROF-01 | Privacy & security settings must be accessible only to authenticated users. | Confirmed |
| REQ-PROF-02 | Rating is computed only from reviews; cancellation does not change rating. | Confirmed |
| REQ-PROF-03 | A user with no reviews must not display a 5-star rating; show "no reviews" instead. | Confirmed (defect present) |
| REQ-PROF-04 | After a completed trip, a "Leave a review" banner appears in chat → 1–5 stars + comment. | Confirmed |
| REQ-PROF-05 | Banner: first dismiss hides it, it reappears after 6h, second dismiss hides permanently, submitting removes it permanently. | Confirmed |
| REQ-PROF-06 | Profile fields (name, email, date of birth, car) must be validated; age must be ≥ 18. | Confirmed |

### Notifications

| ID | Requirement | Status |
|---|---|---|
| REQ-NOTIF-01 | Cancelling a trip/request sends a push to the other party. | Confirmed |
| REQ-NOTIF-02 | The in-app notification counter displays, increments, and resets after viewing. | Confirmed |
| REQ-NOTIF-03 | "99+" counter behaviour under high volume. | Open (not testable without admin/DB/API) |
