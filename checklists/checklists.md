# Checklists

Module checklists used to drive testing of the HamSafar MVP. Each covers **positive** paths (expected behaviour) and **negative** paths (invalid input, no network, edge states), written as `check → expected result`, so they double as lightweight test cases and as a coverage record.

Several checks carry a **⚠ Found:** note linking the check to the defect it uncovered (e.g. `⚠ Found: BUG-041`), so each checklist is also an audit trail from check → bug report.

> **Why a README sits in this folder:** GitHub renders a folder's `README.md` as that folder's front page, so this file is the index and legend for the 10 checklists below — not a placeholder.

The source checklists are numbered **#3–#12** (numbering starts at #3 because Taiga tasks #1–#2 were the project kickoff and the device/version tracker, not checklists). That is 10 checklists; #12 (Smoke) lives in [`../smoke-testing/`](../smoke-testing/).

| Source # | Module | File |
|---|---|---|
| #3 | Authorization (register / log in / recover / logout / delete) | [01-authorization.md](01-authorization.md) |
| #4 | Home & search | [02-home-search.md](02-home-search.md) |
| #5 | Trip & request creation (driver + passenger) | [03-trip-and-request-creation.md](03-trip-and-request-creation.md) |
| #6 | Trip details & booking | [04-trip-details-booking.md](04-trip-details-booking.md) |
| #7 | My trips | [05-my-trips.md](05-my-trips.md) |
| #8 | Chat | [06-chat.md](06-chat.md) |
| #9 | Profile (guest / registered / reviews) | [07-profile.md](07-profile.md) |
| #10 | Push notifications | [08-push-notifications.md](08-push-notifications.md) |
| #11 | Notifications feed | [09-notifications-feed.md](09-notifications-feed.md) |
| #12 | Smoke test | [../smoke-testing/smoke-test-suite.md](../smoke-testing/smoke-test-suite.md) |
