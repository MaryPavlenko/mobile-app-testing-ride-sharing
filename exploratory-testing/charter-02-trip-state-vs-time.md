# Charter EXP-02 — Trip state vs. the real clock

| Field | Value |
|---|---|
| **Mission** | Find places where a trip's state and the real clock disagree — booking after departure, premature or auto completion, and driver/passenger desync. |
| **Areas** | Booking, My Trips statuses, trip completion, create-trip time selection |
| **Time box** | 60 minutes |
| **Build** | v1.0.8 (Xiaomi Redmi Note 10S, Android 13; cross-checked across a driver and a passenger account) |
| **Technique** | Session-based exploratory testing; a "follow the clock" approach — trips set with start times just before and just after `now` |

## Why this charter
MVPs routinely under-handle time. The create-trip flow already lets a driver pick today's date and even an already-passed time with "Continue" still active (see checklist #5). That is a strong signal that downstream trip state may not be time-aware either, so the whole life-cycle around `departureTime` was worth probing deliberately.

## Notes from the session
- Booking stayed possible on a trip whose departure had already passed (within ~35 minutes). → **BUG-071**.
- A trip completed for the driver but stayed active for the passenger — the two sides were out of sync. → **BUG-096**.
- A trip auto-completed for the driver at the start time, rather than at the actual end of the trip. → **BUG-097**.
- The create-trip "What time?" screen accepts an already-passed time for today with "Continue" active — a validation gap feeding the issues above.

## Outcome
- 3 defects (BUG-071, BUG-096, BUG-097) plus one create-trip time-validation candidate.
- Follow-up: a scripted negative suite for time boundaries (departure exactly `now`, just past, far past) was recommended and folded into the booking checklist.
