# Open Questions / Clarifications Log

Behaviour that was undefined at the time of testing. Each item was raised with the QA lead rather than guessed at, so that no test silently invented its own acceptance criteria. Keeping this log is part of the deliverable: it shows *what the team still had to decide*, and it protects the defect list from false positives.

| # | Area | Question | Why it matters for testing |
|---|---|---|---|
| 1 | Currency | How is the trip currency determined — manual driver choice, route country, or default? | Can't assert correct currency display without the rule |
| 2 | Currency | Can the driver pick the currency manually? | Affects create-trip validation |
| 3 | Currency | Is currency shown explicitly as UZS / TJS? | Affects expected results on trip card |
| 4 | Price | Can a trip be created with no price? | Determines if empty price is a defect |
| 5 | Price | What are the price field limits? (values > 1000 are silently capped at 1000) | Boundary testing of the price field |
| 6 | Price | Should price participate in search/filtering later? | Scope of search testing |
| 7 | Booking | Can a passenger cancel an *unconfirmed* request? | Determines expected cancel behaviour |
| 8 | Booking | Is the driver notified when an unconfirmed request is cancelled? | Push coverage |
| 9 | Chat | Is the chat created automatically on booking? | Expected post-booking state |
| 10 | Chat | At which stage does the chat appear? | Test sequencing |
| 11 | Chat | At which stage does the call button appear (request / confirmation / trip start)? | Call-button test conditions |
| 12 | Reviews | Can drivers leave reviews for passengers, or only passengers for drivers? | Review flow coverage |
| 13 | Reviews | Can the review form be opened manually if the banner was missed? | Edge-case coverage |
| 14 | Reviews | Is there a time limit for leaving a review? | Expiry testing |
| 15 | Notifications | What should happen to the counter above 99 ("99+")? | Counter display assertion |
| 16 | Security | Should there be a new-device login notification? | Security test expectation |
| 17 | Security | Is there a limit on active devices? | Multi-session testing |
| 18 | Trip creation | What status should a blocked draft (no car data) have? | Expected blocked-state assertion |
| 19 | Trip creation | How should the user see the reason publishing is blocked? | UX / error-message assertion |
| 20 | Price | On the Payment/Create-trip screen for the Driver role, which currency shows by default — TJS? | Default-value assertion |
| 21 | Price | Can the price be a decimal (using `.` or `,`)? | Input format validation |
